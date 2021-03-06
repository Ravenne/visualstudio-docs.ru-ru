---
title: Работа с несколькими учетными записями пользователя
ms.date: 12/10/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 371cdc85648b8b058267540b305162adf371c4f6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62581903"
---
# <a name="work-with-multiple-user-accounts"></a>Работа с несколькими учетными записями пользователя

Если у вас несколько учетных записей Майкрософт и рабочих учетных записей, их все можно добавить в Visual Studio, чтобы ресурсы всех учетных записей были доступны из любой учетной записи, с помощью которой выполнен вход. Службы Azure, Application Insights, Azure DevOps и Office 365 поддерживают упрощенную процедуру входа в систему.

Учетные записи, добавленные на одном компьютере, перемещаются вместе с вами, когда вход в Visual Studio выполняется с другого компьютера.

> [!NOTE]
> Но учетные данные не перемещаются вместе с именами учетных записей. При первом использовании ресурсов на новом компьютере вам будет предложено ввести учетные данные для этих учетных записей.

В этой статье показано, как добавить в Visual Studio несколько учетных записей. Также вы узнаете, как просмотреть ресурсы, доступные из этих учетных записей в таких расположениях, как диалоговое окно **Добавить подключенную службу**, **Обозреватель сервера** и **Team Explorer**.

## <a name="sign-in-to-visual-studio"></a>Выполните вход в Visual Studio

Выполните вход в Visual Studio с помощью учетной записи Майкрософт или учетной записи организации. В правом верхнем углу окна должно отображаться ваше имя приблизительно так:

![Текущий пользователь](../ide/media/vs2015_username.png)

### <a name="access-your-azure-account-in-server-explorer"></a>Доступ к учетной записи Azure в обозревателе сервера

Нажмите клавиши **CTRL**+**ALT**+**S**, чтобы открыть **обозреватель сервера**. Разверните узел **Azure** и убедитесь, что он содержит все ресурсы, доступные в учетной записи Azure, связанной с учетной записью, которая использовалась для входа в Visual Studio. Это выглядит примерно так:

![Обозреватель сервера с развернутым узлом Azure](../ide/media/work-with-multiple-user-accounts/server-explorer.png)

При первом использовании Visual Studio на каком-либо конкретном устройстве в диалоговом окне будут отображаться только подписки, зарегистрированные под учетной записью, с которой выполнен вход. Доступ к ресурсам всех других учетных записей осуществляется непосредственно из **обозревателя серверов**, где вы можете щелкнуть узел **Azure** правой кнопкой мыши, выбрать **Управление подписками и их фильтрация** и добавить нужные учетные записи из средства выбора учетной записи. Затем при необходимости можно выбрать другую учетную запись, щелкнув стрелку вниз и выбрав ее в списке учетных записей. После выбора учетной записи можно настроить, какие подписки под этой учетной записью будут отображаться в **обозревателе серверов**.

![Диалоговое окно «Управление подписками Azure»](../ide/media/vs2015_manage_subs.png)

Ресурсы этой подписки отобразятся при следующем открытии **обозревателя серверов**.

### <a name="access-your-azure-account-via-add-connected-service-dialog"></a>Доступ к учетной записи Azure в диалоговом окне "Добавление подключенной службы"

1. Откройте существующий проект или создайте новый проект.

1. Щелкните правой кнопкой мыши узел проекта в **обозревателе решений** и выберите **Добавить** > **Подключенная служба**.

   Откроется мастер **добавления подключенной службы** со списком служб в учетной записи Azure, связанной с персонализированной учетной записью Visual Studio. Вам не нужно выполнять отдельный вход в Azure. Но необходимо войти в другие учетные записи при первой попытке доступа к их ресурсам с определенного компьютера.

### <a name="access-azure-active-directory-in-a-web-project"></a>Доступ к Azure Active Directory в веб-проекте

Azure Active Directory (AAD) поддерживает единый вход в веб-приложения ASP.NET MVC или аутентификацию AD в службах веб-API. Аутентификация домена отличается от аутентификации отдельной учетной записи пользователя. Пользователи, имеющие доступ к домену Active Directory, могут подключаться к веб-приложениям с помощью существующих учетных записей AAD. Приложения Office 365 также могут использовать проверку подлинности домена.

Чтобы увидеть это в действии, создайте проект **Веб-приложение ASP.NET**. В диалоговом окне **Новый проект ASP.NET** выберите **Изменить проверку подлинности**. Откроется мастер проверки подлинности для выбора типа проверки подлинности, который будет использоваться в приложении.

![Изменение диалогового окна проверки подлинности для ASP.NET](../ide/media/vs2015_change_authentication.png)

Дополнительные сведения о разных видах аутентификации в ASP.NET вы найдете в статье [Создание веб-проектов ASP.NET в Visual Studio 2013](/aspnet/visual-studio/overview/2013/creating-web-projects-in-visual-studio#authentication-methods).

### <a name="access-your-azure-devops-organization"></a>Доступ к организации Azure DevOps

В главном меню выберите **Команда** > **Управление соединениями**, чтобы открыть окно **Team Explorer — подключение**. Выберите **Управление подключениями** > **Подключение к проекту**. В диалоговом окне **Подключение к проекту** выберите из списка нужный проект (или выберите команду **Добавить сервер TFS** и введите URL-адрес сервера). Если вы введете URL-адрес, вход в систему будет выполнен без повторного ввода учетных данных.

Дополнительные сведения см. в статье [Подключение к проектам в Team Explorer](connect-team-project.md).

## <a name="add-an-additional-account-to-visual-studio"></a>Добавление учетной записи в Visual Studio

Чтобы добавить учетную запись в Visual Studio, сделайте следующее:

1. Выберите **Файл** > **Параметры учетной записи**.

1. В разделе **Все учетные записи** выберите **Добавить учетную запись**.

1. На странице **Вход в учетную запись** выберите нужную учетную запись или щелкните **Использовать другую учетную запись**. Выполните запросы, чтобы ввести учетные данные новой учетной записи.

(Необязательно) Теперь вы можете открыть **обозреватель серверов** и просмотреть службы Azure, связанные с добавленной учетной записью. В окне **обозревателя серверов** щелкните правой кнопкой мыши узел **Azure** и выберите **Управление подписками и их фильтрация**. Выберите новую учетную запись, щелкнув стрелку раскрывающегося списка рядом с текущей учетной записью, а затем выберите подписки, которые нужно отобразить в **обозревателе серверов**. Будут выведены все службы, связанные с указанной подпиской. Даже не выполняя вход в Visual Studio со второй учетной записью, вы будете подключены ко всем службам и ресурсам этой учетной записи. То же самое верно при выборе **Проект** > **Добавить подключенную службу** и **Команда** > **Подключиться к Team Foundation Server**.

### <a name="add-an-account-using-device-code-flow"></a>Добавление учетной записи с использованием потока кода устройства

В некоторых случаях вход или добавление учетной записи нельзя выполнить обычным образом. Такое может случиться, если Internet Explorer по любой причине заблокирован или сеть находится за брандмауэром. Чтобы обойти эту проблему, вы можете включить *поток кода устройства* и добавить учетную запись или повторно выполнить аутентификацию учетной записи. Поток кода устройства позволяет входить из другого браузера или с другого устройства (физического компьютера или виртуальной машины).

Чтобы выполнить вход с помощью потока кода устройства, сделайте следующее:

1. Откройте страницу [**Учетные записи**](reference/accounts-environment-options-dialog-box.md), выбрав **Средства** > **Параметры** > **Среда**, и щелкните **Включить поток кода устройства при добавлении учетной записи или повторной проверке подлинности учетной записи**. Нажмите кнопку **ОК**, чтобы закрыть страницы свойств.

1. Выберите **Файл** > **Параметры учетной записи**, чтобы открыть страницу управления учетной записью.

1. Выберите **Добавить учетную запись** в разделе **Все учетные записи**.

   В диалоговом окне отобразится URL-адрес и код, который следует вставить в веб-браузер.

   ![URL-адрес и код для потока кода устройства](media/work-with-multiple-user-accounts/device-login-code.png)

1. Нажмите клавиш**CTRL**+**C**, чтобы скопировать текст диалогового окна, а затем закройте его кнопкой **ОК**. Вставьте скопированный текст в текстовый редактор, например в Блокнот. Так будет проще скопировать этот код на следующем шаге.

1. Откройте URL-адрес входа на том компьютере или в том браузере, который вы намерены использовать для входа в Visual Studio, и вставьте или введите скопированный ранее код в поле с текстом **Код**.

   Ниже на той же странице появится имя приложения **Visual Studio**.

1. В разделе **Visual Studio** выберите **Продолжить**.

   ![device-login-page.png](media/work-with-multiple-user-accounts/device-login-page.png)

1. Следуйте инструкциям, чтобы ввести учетные данные учетной записи.

   Появится страница с сообщением о том, что вы вошли в Visual Studio на этом устройстве. Теперь можно закрыть окно браузера.

   ![Завершение входа в Visual Studio через браузер](media/work-with-multiple-user-accounts/sign-in-browser-complete.png)

1. Вернитесь на страницу управления учетной записью в Visual Studio. Здесь вы увидите только что добавленную учетную запись в списке **Все учетные записи**. Нажмите кнопку **Закрыть**.

## <a name="see-also"></a>См. также

- [Вход в Visual Studio](signing-in-to-visual-studio.md)
- [Вход в Visual Studio для Mac](/visualstudio/mac/signing-in)
