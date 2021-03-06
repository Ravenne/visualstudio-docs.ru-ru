---
title: Создание приложений ClickOnce для других пользователей для развертывания | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- preserved branding information
- useManifestForTrust element
- customer deployments [ClickOnce]
- multiple ClickOnce deployment and branding
- ClickOnce applications, previous .NET Framework versions
- application manifests [ClickOnce]
- <useManifestForTrust> element
- manifests [ClickOnce]
- trust applications, ClickOnce
- ClickOnce applications, deployed by others
- ClickOnce applications, previous .NET Framework
ms.assetid: d20766c7-4ef3-45ab-8aa0-3f15b61eccaa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 01e85c0257d372fa9b27ec5f031aae61132f7edc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62928906"
---
# <a name="create-clickonce-applications-for-others-to-deploy"></a>Создание приложений ClickOnce для развертывания другими пользователями
Не все разработчики, создающие развертывания ClickOnce планируете развертывать приложения сами. Многие из них достаточно упаковать свои приложения с помощью ClickOnce, который затем передается файлы клиенту, например большой корпорации. Клиент становится ответственным за размещение приложения в своей сети. В этом разделе рассматриваются некоторые из проблем, возникающих в таких развертываний в версиях .NET Framework, предшествовавших версии 3.5. Затем он описывает новое решение, предоставляемое с помощью новой функции «использовать манифест для доверия» в .NET Framework 3.5. В заключение приводятся рекомендуемые стратегии создания развертываний ClickOnce для клиентов, которые все еще используете более ранние версии платформы .NET Framework.

## <a name="issues-involved-in-creating-deployments-for-customers"></a>Проблемы, связанные с созданием развертываний для клиентов
 При планировании поставки развертывания клиенту возникает несколько вопросов. Первый вопрос касается подписывания кода. Для развертывания по сети, манифест развертывания и манифест приложения для развертывания ClickOnce необходимо оба быть подписан цифровым сертификатом. Это возникает вопрос, следует ли использовать сертификат разработчика или сертификат клиента при подписи манифестов.

 На вопрос, какой сертификат использовать крайне важен, так как удостоверение приложения ClickOnce основано на цифровой подписи манифеста развертывания. Если разработчик подписывает манифест развертывания, он может привести к конфликту, если клиент — это Крупная корпорация, а более одного отдела компании развернет настраиваемой версии приложения.

 Например предположим, что компания Adventure Works имеет финансовый отдел и отдел кадров. Оба отдела лицензируют приложение ClickOnce из корпорации Майкрософт, которая создает отчеты из данных, хранящихся в базе данных SQL. Корпорация Майкрософт предоставляет каждого отдела с версией приложения, который настроен для своих данных. Если приложения подписаны тем же сертификатом Authenticode, пользователь, который пытается использовать оба приложения столкнется с ошибкой, как ClickOnce будет считать второе приложение идентичен первому. В этом случае клиент может испытывать непредсказуемыми и нежелательные побочные эффекты, которые включают потерю все данные, хранящиеся локально, для приложения.

 Дополнительную проблему, связанную с подписанием кода является `deploymentProvider` элемента в манифесте развертывания, который сообщает ClickOnce, где искать обновления приложения. Этот элемент необходимо добавить в манифест развертывания до его подписания. Если этот элемент добавляется после этого, необходимо заново подписать манифест развертывания.

### <a name="require-the-customer-to-sign-the-deployment-manifest"></a>Клиенту требуется подписать манифест развертывания
 Одно из решений этой проблемы неуникальных развертываний — разработчик подписывал манифест приложения, а клиент подписать манифест развертывания. Хотя этот подход работает, он вызывает другие проблемы. Так как сертификат Authenticode должен оставаться защищенного ресурса, клиент не может просто дать сертификат можно подписать развертывание. Хотя клиент смог подписать манифест развертывания самостоятельно с помощью средств, которые можно бесплатно с помощью пакета SDK для .NET Framework, для этого может потребоваться больше технических знаний, чем клиента, чтобы предоставить. В таком случае разработчик обычно создает приложение, веб-сайт или другой механизм, через который клиент может передать свою версию приложения для подписания.

### <a name="the-impact-of-customer-signing-on-clickonce-application-security"></a>Влияние подписания клиентом на безопасность приложений ClickOnce
 Даже если разработчик и клиент согласны, что клиент должен подписать манифест приложения, это вызывает другие проблемы, относящиеся удостоверения приложения, особенно в том случае, когда он применяется к развертывание надежных приложений. (Дополнительные сведения об этой функции см. в разделе [Общие сведения о развертывании доверенных приложений](../deployment/trusted-application-deployment-overview.md).) Предположим, что Adventure Works хочет настроить свои клиентские компьютеры, так что любое приложение, предоставляемое корпорацией Майкрософт выполняется с полным доверием. Если Adventure Works подписывает манифест развертывания, ClickOnce будет использовать подпись безопасности рабочих Adventure определить уровень доверия приложения.

## <a name="create-customer-deployments-by-using-application-manifest-for-trust"></a>Создание клиентских развертываний с помощью манифеста приложения для управления безопасностью
 Технология ClickOnce в .NET Framework 3.5 содержит новый компонент, который предоставляет разработчикам и клиентам новое решение для сценария как манифесты должны быть подписаны. Манифест приложения ClickOnce поддерживает новый элемент с именем `<useManifestForTrust>` , позволяет разработчику Показать, что цифровая подпись манифеста приложения будет использован для принятия решений о доверии. Разработчик использует средства упаковки ClickOnce — например *Mage.exe*, *MageUI.exe*и Visual Studio — для включения этого элемента в манифесте приложения, а также для внедрения имени издателя и Имя приложения в манифесте.

 При использовании `<useManifestForTrust>`, манифест развертывания не обязательно должны подписываться с помощью сертификата Authenticode, выданный центром сертификации. Вместо этого он может быть подписана с помощью так называемого самозаверяющий сертификат. Самозаверяющий сертификат создается клиентом или разработчиком, с помощью стандартных средств пакета SDK для .NET Framework и затем применяются к манифесту развертывания с помощью стандартных средств развертывания ClickOnce. Дополнительные сведения см. в разделе [MakeCert](/windows/desktop/SecCrypto/makecert).

 С помощью самозаверяющего сертификата для манифеста развертывания представляет несколько преимуществ. Устраняя необходимость для клиента получить или создать свой собственный сертификат Authenticode `<useManifestForTrust>` упрощает развертывание для клиента, что позволяет разработчику сохранять свой фирменный в приложении. Результат — это набор подписанных развертываний, которые являются более безопасными и имеют уникальные удостоверения приложений. Это устраняет потенциальный конфликт, который может возникнуть при развертывании одного приложения для нескольких клиентов.

 Пошаговые инструкции по созданию развертывания ClickOnce с `<useManifestForTrust>` включен, см. в разделе [Пошаговое руководство: Развертывание вручную приложения ClickOnce, которая не требует повторной подписи и сохраняет фирменную символику](../deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required.md).

### <a name="how-application-manifest-for-trust-works-at-runtime"></a>Как работает манифест приложения для управления безопасностью во время выполнения
 Чтобы лучше понять, как с помощью манифеста приложения для управления безопасностью работает во время выполнения, рассмотрим следующий пример. Приложения ClickOnce, ориентированном на .NET Framework 3.5 разрабатывается корпорацией Майкрософт. Манифест приложения использует `<useManifestForTrust>` элемент и подписано корпорацией Майкрософт. Adventure Works подписывает манифест развертывания с помощью самозаверяющего сертификата. Adventure Works, клиенты настроены на доверие любое приложение, подписанное корпорацией Майкрософт.

 Когда пользователь щелкает ссылку на манифест развертывания, ClickOnce устанавливает приложение на компьютере пользователя. Эта информация сертификата и развертывания идентифицировать уникальным образом приложения ClickOnce на клиентском компьютере. Если пользователь пытается установить то же приложение повторно в другом расположении, это удостоверение можно использовать ClickOnce для определения того, что приложение уже существует на стороне клиента.

 Далее ClickOnce проверяет сертификат Authenticode, используемый для подписания манифеста приложения, который определяет уровень доверия, предоставляемый службой ClickOnce. Поскольку Adventure Works настроил его клиенты могли доверять любое приложение, подписанное корпорацией Майкрософт, данное приложение ClickOnce предоставляется полное доверие. Для получения дополнительной информации см. раздел [Общие сведения о развертывании доверенных приложений](../deployment/trusted-application-deployment-overview.md).

## <a name="create-customer-deployments-for-earlier-versions"></a>Создание клиентских развертываний для более ранних версий
 Что делать, если разработчик выполняет развертывание приложений ClickOnce для клиентов, использующих более старые версии .NET Framework? В следующих разделах приведены рекомендуемые решения, а также преимущества и недостатки каждого из них.

### <a name="sign-deployments-on-behalf-of-customer"></a>Подписание развертываний от имени клиента
 Одна возможная стратегия развертывания предназначена для разработчиков создать механизм для подписи развертываний от имени своих клиентов с помощью закрытого ключа клиента. Благодаря этому разработчику нужно заботиться об управлении закрытые ключи или несколько пакетов развертывания. Разработчик просто предоставляет одного развертывания для каждого клиента. Он зависит от клиента в процессе настройки среды с помощью службы подписей.

 Недостатком этого метода является время и деньги, которые необходимы для его реализации. Хотя такая служба может быть построен с помощью средств, предоставляемых .NET Framework SDK, это увеличит больше времени разработки жизненного цикла продукта.

 Как отмечалось ранее в этом разделе, другим недостатком является то, что версии каждого клиента приложения один идентификатор приложения, что может привести к конфликту. Если это представляет собой проблему, разработчик может изменить имя поля, используемый при создании манифеста развертывания для предоставления уникального имени для каждого приложения. Это будет создавать отдельные удостоверения для каждой версии приложения и устранения потенциальных конфликтов идентификаторов. Это поле соответствует `-Name` аргумент для Mage.exe и **имя** на **имя** вкладку в MageUI.exe.

 Например предположим, что разработчик создал приложение с именем Application1. Вместо создания одного развертывания с полем имени, значение Application1, разработчик может создать несколько развертываний вариация заказчиком на это имя, например клиента а Application1, Application1-КлиентБ и так далее.

### <a name="deploy-using-a-setup-package"></a>Развертывание с помощью пакета установки
 Вторая возможная стратегия является создание проекта установки Microsoft для выполнения первоначального развертывания приложения ClickOnce. Его можно указать в одном из нескольких разных форматах: как MSI-развертывание, как исполняемый файл установки (. EXE-файла), или в виде CAB-файла вместе с пакетный скрипт.

 При использовании этого метода разработчик предоставляет клиенту развертывание, которое содержит файлы приложения, манифест приложения и манифест развертывания, который служит в качестве шаблона. Клиента необходимо запустить программу установки, который запрашивает URL-адрес развертывания (сервер или расположение, из которого пользователи будут устанавливать приложение ClickOnce в общую папку), а также цифровым сертификатом. Программа установки также можно запрашивать дополнительные параметры конфигурации ClickOnce, например интервал проверки обновлений. После сбора этой информации, программа установки создать реальный манифест развертывания, подписать его и опубликовать приложение ClickOnce в указанное местоположение на сервере.

 Существует три способа, что клиент смог подписать манифест развертывания в этой ситуации:

1. Клиент может использовать действительный сертификат, выпущенный центром сертификации (ЦС).

2. В качестве варианта этого подхода клиент можете подписать их манифест развертывания с использованием самозаверяющего сертификата. Недостатком это является то, что это вызовет приложение для отображения слова «Неизвестный издатель», когда у пользователя запрашивается необходимость установки. Тем не менее преимущество заключается в предотвращении небольших клиентов от необходимости тратить время и деньги на сертификат, выданный центром сертификации.

3. Наконец разработчик может включить свой собственный самозаверяющий сертификат в пакет установки. Это приводит к потенциальных проблем с удостоверением приложения, см. выше в этом разделе.

   Недостатком метод настройки развертывания проекта является время и затраты, необходимые для создания настраиваемого приложения развертывания.

### <a name="have-customer-generate-deployment-manifest"></a>Ни создать манифест развертывания клиента
 Третья стратегия развертывания состоит в передаче только приложение из файлов и манифеста приложения для клиента. В этом случае клиент несет ответственность за использование пакета SDK для .NET Framework для создания и подписания манифеста развертывания.

 Недостатком этого метода является необходимость клиента для установки инструментов пакета SDK для .NET Framework и разработчик или системный администратор, опытный мастер с их помощью. Некоторые клиенты могут запросить решение, которое требует почти никаких технических усилий с их стороны.

## <a name="see-also"></a>См. также
- [Развертывание приложений ClickOnce для тестирования и рабочих серверов без повторного подписывания](../deployment/deploying-clickonce-applications-for-testing-and-production-without-resigning.md)
- [Пошаговое руководство: Развертывание вручную приложения ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)
- [Пошаговое руководство: развертывание вручную приложения ClickOnce, которое не нуждается в повторном подписывании и сохраняет фирменную символику](../deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required.md)