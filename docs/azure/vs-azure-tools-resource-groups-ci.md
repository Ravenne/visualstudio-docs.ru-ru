---
title: Непрерывная интеграция в Azure DevOps Services с использованием проектов группы ресурсов Azure | Документация Майкрософт
description: Здесь описывается, как настроить непрерывную интеграцию в Azure DevOps Services с использованием проектов развертывания группы ресурсов Azure в Visual Studio.
author: mlearned
manager: jillfra
ms.assetid: b81c172a-be87-4adc-861e-d20b94be9e38
ms.topic: article
ms.workload: azure-vs
ms.date: 08/01/2016
ms.author: mlearned
ms.openlocfilehash: 1d3904c488186dbbde326619420dd55e71c3af04
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62568916"
---
# <a name="continuous-integration-in-azure-devops-services-using-azure-resource-group-deployment-projects"></a>Непрерывная интеграция в Azure DevOps Services с использованием проектов развертывания группы ресурсов Azure

Чтобы развернуть шаблон Azure, вы выполняете задачи на разных этапах: сборка, тестирование, копирование в Azure (также называется "промежуточный процесс") и развертывание шаблона. Существует два разных способа развертывания шаблонов в Azure DevOps Services. Оба метода обеспечивают одинаковые результаты, поэтому выберите самый оптимальный для своего рабочего процесса.

1. Добавьте один шаг в конвейер сборки, который запускает сценарий PowerShell, содержащийся в проекте развертывания группы ресурсов Azure (Deploy-AzureResourceGroup.ps1). Этот сценарий копирует артефакты и развертывает шаблон.
2. Добавьте несколько шагов сборки Azure DevOps Services, на каждом из которых выполняется одна задача этапа.

В этой статье показаны оба варианта. Преимущество первого варианта заключается в запуске того же сценария, который использовался разработчиками в Visual Studio. Это обеспечивает согласованность на протяжении всего жизненного цикла. Второй вариант предлагает удобную альтернативу в виде встроенного сценария. Обе процедуры предполагают, что проект развертывания Visual Studio записан после изменения в Azure DevOps Services.

## <a name="copy-artifacts-to-azure"></a>Копирование артефактов в Azure
Независимо от сценария при наличии артефактов, требуемых для развертывания шаблона, необходимо предоставить Azure Resource Manager доступ к ним. Эти артефакты могут включить такие файлы:

* вложенные шаблоны;
* сценарии конфигурации и DSC;
* двоичные файлы приложения.

### <a name="nested-templates-and-configuration-scripts"></a>Вложенные шаблоны и сценарии конфигурации
При использовании шаблонов, предоставляемых Visual Studio (или созданных с помощью фрагментов кода Visual Studio), сценарий PowerShell не только размещает артефакты, но и параметризует URI ресурсов для различных развертываний. Затем сценарий копирует артефакты в безопасный контейнер в Azure, создает соответствующий маркер SaS и передает эти сведения развертыванию шаблона. Дополнительные сведения о вложенных шаблонах см. в статье [Create a template deployment](https://msdn.microsoft.com/library/azure/dn790564.aspx) (Создание шаблона-развертывания).  При использовании задач в Azure DevOps Services необходимо выбрать соответствующие задачи для развертывания шаблона и, если это необходимо, передавать значения параметров из промежуточного шага в процесс развертывания шаблона.

## <a name="set-up-continuous-deployment-in-azure-pipelines"></a>Настройка непрерывного развертывания в Azure Pipelines
Чтобы вызвать сценарий PowerShell в Azure Pipelines, необходимо обновить конвейер сборки. Вкратце, нужно выполнить следующее:

1. Изменить конвейер сборки.
2. Настроить авторизацию Azure в Azure Pipelines.
3. Добавить этап сборки Azure PowerShell, который ссылается на сценарий PowerShell в проекте развертывания группы ресурсов Azure.
4. Задать значение параметра *-ArtifactsStagingDirectory* для работы с проектом, созданным в Azure Pipelines.

### <a name="detailed-walkthrough-for-option-1"></a>Подробное пошаговое руководство для варианта 1
Ниже приведены шаги, необходимые для настройки непрерывного развертывания в Azure DevOps Services с помощью отдельной задачи, которая выполняет сценарий PowerShell в вашем проекте.

1. Измените конвейер сборки Azure DevOps Services и добавьте этап сборки Azure PowerShell. В категории **Конвейеры сборки** выберите конвейер сборки, а затем щелкните ссылку **Изменить**.

   ![Изменение конвейера сборки](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough1.png)
2. Добавьте новый этап сборки **Azure PowerShell** в конвейер сборки, а затем нажмите кнопку **Add build step…** (Добавить шаг сборки…). .

   ![Добавление шага сборки](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough2.png)
3. Выберите категорию задачи **Развертывание**, а затем выберите задачу **Azure PowerShell** и нажмите рядом с ней кнопку **Добавить**.

   ![Добавление задач](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough3.png)
4. Выберите этап сборки **Azure PowerShell** и укажите соответствующие значения.

   1. Если в Azure DevOps Services уже добавлена конечная точка службы, в раскрывающемся списке **Подписка Azure** выберите подписку, а затем перейдите к следующему разделу.

      Если в Azure DevOps Services нет конечной точки службы Azure, ее необходимо добавить. В этом подразделе описывается этот процесс. Если учетная запись Azure использует учетную запись Майкрософт (например, Hotmail), необходимо выполнить действия ниже, чтобы обеспечить аутентификацию субъекта-службы.

   2. Рядом с раскрывающимся списком **Подписка Azure** щелкните ссылку **Управление**.

      ![Управление подписками Azure](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough4.png)
   3. В раскрывающемся списке **Создать конечную точку службы** выберите пункт **Azure**.

      ![Новая конечная точка службы](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough5.png)
   4. В диалоговом окне **Добавление подписки Azure** выберите **Субъект-служба**.

      ![Параметр субъекта-службы](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough6.png)
   5. В диалоговом окне **Добавление подписки Azure** добавьте сведения о подписке Azure. Требуется указать следующие элементы:

      * идентификатор подписки;
      * Название подписки
      * идентификатор субъекта-службы;
      * ключ субъекта-службы;
      * Идентификатор клиента
   6. В поле имени **Подписка** укажите выбранное имя. Это значение в дальнейшем будет отображаться в раскрывающемся списке **Подписка Azure** в Azure DevOps Services.

   7. Если вы не знаете свой идентификатор подписки Azure, его можно получить, выполнив одну из следующих команд.

      Для сценариев Azure PowerShell:

      `Get-AzureRmSubscription`

      Для интерфейса командной строки Azure:

      `azure account show`
   8. Чтобы получить идентификатор субъекта-службы, ключ субъекта-службы и идентификатор клиента, выполните действия, описанные в статье [Создание приложения Active Directory и субъекта-службы с доступом к ресурсам с помощью портала](/azure/azure-resource-manager/resource-group-create-service-principal-portal) или [Использование Azure PowerShell для создания субъекта-службы и доступа к ресурсам](/azure/azure-resource-manager/resource-group-authenticate-service-principal).
   9. В диалоговом окне **Добавление подписки Azure** укажите идентификатор субъекта-службы, ключ субъекта-службы и идентификатор клиента и нажмите кнопку **ОК**.

      Теперь у вас есть допустимый субъект-служба для выполнения сценария Azure PowerShell.
5. Измените конвейер сборки и выберите шаг сборки **Azure PowerShell**. В раскрывающемся списке **Подписка Azure** выберите подписку. (Если подписка не отображается, щелкните кнопку **Обновить** рядом с ссылкой **Управление**.)

   ![Настройка задачи сборки Azure PowerShell](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough9.png)
6. Укажите путь к сценарию PowerShell Deploy-AzureResourceGroup.ps1. Для этого возле поля **Путь к скрипту** нажмите кнопку с многоточием (...), перейдите к сценарию PowerShell Deploy-AzureResourceGroup.ps1 (в проектной папке **Скрипты**), выберите его и нажмите кнопку **ОК**.

   ![Выбор пути к сценарию](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough10.png)
7. Выбрав сценарий, обновите путь к нему, чтобы он выполнялся из каталога Build.StagingDirectory (тот же каталог, который настроен для *ArtifactsLocation* ). Для этого добавьте $(Build.StagingDirectory)/ в начале пути к сценарию.

    ![Изменение пути к сценарию](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough11b.png)
8. В поле **Аргументы сценария** введите приведенные ниже параметры (в одной строке). При выполнении сценария в Visual Studio можно увидеть, как VS использует параметры в окне **Вывод** . С этого можно начать установку значений параметров на этапе сборки.

   | Параметр | ОПИСАНИЕ |
   | --- | --- |
   | -ResourceGroupLocation |Значение географического расположения, в котором находится группа ресурсов, например **eastus** или **'East US'**. (Добавьте одинарные кавычки, если в имени есть пробел.) Дополнительные сведения см. в статье о [регионах Azure](https://azure.microsoft.com/regions/). |
   | -ResourceGroupName |Имя группы ресурсов, используемой для этого развертывания. |
   | -UploadArtifacts |Этот параметр (если он присутствует) указывает, что артефакты следует отправлять в Azure из локальной системы. Этот параметр нужно задать, только если шаблон развертывания требует дополнительных артефактов, которые нужно разместить с помощью сценария PowerShell (например, сценарии настройки или вложенные шаблоны). |
   | -StorageAccountName |Имя учетной записи хранения, используемой для размещения артефактов при этом развертывании. Этот параметр используется только в том случае, если применяется промежуточное хранение артефактов для развертывания. Когда этот параметр передан, то учетная запись хранения создается в том случае, если сценарий не создал ее во время предыдущего развертывания. Если этот параметр указан, то учетная запись хранения должна уже существовать. |
   | -StorageAccountResourceGroupName |Имя группы ресурсов, связанной с учетной записью хранения. Этот параметр является обязательным только в том случае, если указано значение параметра StorageAccountName. |
   | -TemplateFile |Путь к файлу шаблона в проекте развертывания группы ресурсов Azure. Для большей гибкости укажите для этого параметра путь, который соотносится с расположением сценария PowerShell, а не абсолютный путь. |
   | -TemplateParametersFile |Путь к файлу параметров в проекте развертывания группы ресурсов Azure. Для большей гибкости укажите для этого параметра путь, который соотносится с расположением сценария PowerShell, а не абсолютный путь. |
   | -ArtifactStagingDirectory |Этот параметр позволяет сценарию PowerShell определить папку, из которой нужно скопировать двоичные файлы проекта. Это значение переопределяет значение по умолчанию, используемое сценарием PowerShell. Для Azure DevOps Services задайте значение ArtifactStagingDirectory $(Build.StagingDirectory). |

   Ниже приведен пример аргументов сценария (разрывы строк — для удобства чтения):

   ```
   -ResourceGroupName 'MyGroup' -ResourceGroupLocation 'eastus' -TemplateFile '..\templates\azuredeploy.json'
   -TemplateParametersFile '..\templates\azuredeploy.parameters.json' -UploadArtifacts -StorageAccountName 'mystorageacct'
   –StorageAccountResourceGroupName 'Default-Storage-EastUS' -ArtifactStagingDirectory '$(Build.StagingDirectory)'
   ```

   После завершения работы поле **Аргументы сценария** должно иметь вид следующего списка.

   ![Аргументы сценария](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough12.png)
9. Добавив все необходимые элементы на этапе сборки Azure PowerShell, нажмите кнопку **Очередь** , чтобы создать проект. На экране **Сборка** отобразится вывод сценария PowerShell.

### <a name="detailed-walkthrough-for-option-2"></a>Подробное пошаговое руководство для варианта 2
Ниже приведены шаги, необходимые для настройки непрерывного развертывания в Azure DevOps Services с помощью встроенных задач.

1. Измените конвейер сборки Azure DevOps Services для добавления двух новых шагов сборки. В категории **Определения сборок** выберите конвейер сборки, а затем щелкните ссылку **Изменить**.

   ![Изменение определения сборок](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough13.png)
2. Добавьте новые шаги в конвейер сборки с помощью кнопки **Add build step…** (Добавить шаг сборки…). .

   ![Добавление шага сборки](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough14.png)
3. Выберите категорию задачи **Развертывание**, а затем выберите задачу **Копирование файлов Azure** и нажмите рядом с ней кнопку **Добавить**.

   ![Добавление задачи копирования файлов Azure](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough15.png)
4. Выберите задачу **Развертывание группы ресурсов Azure**, нажмите ее кнопку **Добавить**, после чего нажмите кнопку **Закрыть** для **каталога задач**.

   ![Добавление задачи развертывания группы ресурсов Azure](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough16.png)
5. Выберите задачу **Копирование файлов Azure** и введите значения для нее.

   Если в Azure DevOps Services уже добавлена конечная точка службы, то выберите подписку из раскрывающегося списка **Подписка Azure**. Если у вас нет подписки, ознакомьтесь с [вариантом 1](#detailed-walkthrough-for-option-1), чтобы получить инструкции по ее настройке в Azure DevOps Services.

   * "Источник": введите **$(Build.StagingDirectory)**.
   * "Тип подключения Azure": выберите **Azure Resource Manager**.
   * "Подписка на AzureRM": из раскрывающегося списка **Подписка Azure** выберите подписку для учетной записи хранения, которую вы хотите использовать. (Если подписка не отображается, щелкните кнопку **Обновить** рядом с ссылкой **Управление**.)
   * "Тип назначения": выберите **BLOB-объект Azure**.
   * "Учетная запись хранения Диспетчера ресурсов": выберите учетную запись хранения для промежуточного хранения артефактов.
   * "Имя контейнера": введите имя контейнера, который вы хотите использовать для промежуточного хранения. Это может быть любое допустимое имя контейнера, но нужно использовать один выделенный контейнер для этого конвейера сборки.

   Значения выходных данных:

   * "Код URI контейнера хранилища": введите **artifactsLocation**.
   * "Токен SAS контейнера хранилища": введите **artifactsLocationSasToken**.

   ![Настройка задачи копирования файлов Azure](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough17.png)
6. Выберите шаг сборки **Развертывание группы ресурсов Azure** и укажите соответствующие значения.

   * "Тип подключения Azure": выберите **Azure Resource Manager**.
   * "Подписка на AzureRM": из раскрывающегося списка **Подписка Azure** выберите подписку для развертывания. Обычно это та же подписка, которая была указана на предыдущем шаге.
   * "Действие": выберите **Create or Update Resource Group** (Создание или изменение группы ресурсов).
   * "Группа ресурсов": выберите группу ресурсов или введите имя новой группы ресурсов для развертывания.
   * "Расположение": выберите расположение группы ресурсов.
   * "Шаблон": введите путь и имя шаблона для развертывания, добавив перед ними **$(Build.StagingDirectory)**, например: **$(Build.StagingDirectory/DSC-CI/azuredeploy.json)**.
   * "Параметры шаблона": введите путь и имя используемого файла параметров, добавив перед ними **$(Build.StagingDirectory)**, например: **$(Build.StagingDirectory/DSC-CI/azuredeploy.parameters.json)**.
   * "Переопределить параметры шаблона": наберите или скопируйте и вставьте следующий код.

     ```
     -_artifactsLocation $(artifactsLocation) -_artifactsLocationSasToken (ConvertTo-SecureString -String "$(artifactsLocationSasToken)" -AsPlainText -Force)
     ```

     ![Настройка задачи развертывания группы ресурсов Azure](media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough18.png)
7. Добавив все необходимые элементы, сохраните конвейер сборки и выберите **Поставить новую сборку в очередь** вверху.

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения об Azure Resource Manager и группах ресурсов Azure см. в [обзоре Azure Resource Manager](/azure/azure-resource-manager/resource-group-overview).