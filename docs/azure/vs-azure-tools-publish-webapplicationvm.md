---
title: Publish-WebApplicationVM | Документация Майкрософт
description: Узнайте, как развернуть веб-приложение на виртуальной машине. Этот сценарий создает необходимые ресурсы в подписке Azure, если они еще не созданы.
services: visual-studio-online
author: ghogen
manager: douge
assetId: de4cec95-f73f-44d9-babd-9f47f2633cdb
ms.prod: visual-studio-dev15
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
origin.date: 11/11/2016
ms.date: 09/10/2018
ms.author: v-junlch
ms.openlocfilehash: 8b4b7a05de87ab8b70046b51fe9f256f05d3aee5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62572289"
---
# <a name="publish-webapplicationvm-windows-powershell-script"></a>Publish-WebApplicationVM (сценарий Windows PowerShell)
Развертывание веб-приложения на виртуальной машине. и создает необходимые ресурсы в подписке Azure, если они еще не созданы.

```
Publish-WebApplicationVM
-Configuration <configuration>
-SubscriptionName <subscriptionName>
-WebDeployPackage <packageName>
-VMPassword @{Name = "name"; Password = "password")
-DatabaseServerPassword @{Name = "name"; Password = "password"}
-SendHostMessagesToOutput
-Verbose
```

### <a name="configuration"></a>Параметр Configuration
Путь к файлу конфигурации JSON, содержащему подробные сведения о развертывании.

| Псевдонимы | Нет |
| --- | --- |
| Обязательный? |true |
| Положение |именованная |
| Значение по умолчанию |Нет |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

### <a name="subscriptionname"></a>Параметр SubscriptionName
Имя подписки Azure, в которой необходимо создать виртуальную машину.

| Псевдонимы | Нет |
| --- | --- |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |Используется первая подписка в файле подписок |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

### <a name="webdeploypackage"></a>Параметр WebDeployPackage
Путь к пакету веб-развертывания для публикации на виртуальной машине. Этот пакет можно создать с помощью мастера «Публикация веб-сайта» в Visual Studio. См. практическое руководство по [ созданию пакета веб-развертывания в Visual Studio](https://msdn.microsoft.com/library/dd465323.aspx).

| Псевдонимы | Нет |
| --- | --- |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |Нет |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

### <a name="allowuntrusted"></a>AllowUntrusted
Значение true позволяет использовать сертификаты, не подписанные надежным корневым центром сертификации.

| Псевдонимы | Нет |
| --- | --- |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |False |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

### <a name="vmpassword"></a>VMPassword
Данные учетной записи виртуальной машины. Пример: -VMPassword @{Name = admin; Password = password}

| Псевдонимы | Нет |
| --- | --- |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |Нет |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

### <a name="databaseserverpassword"></a>Параметр DatabaseServerPassword
Учетные данные для базы данных SQL в Azure. Пример: -DatabaseServerPassword @{Name = admin; Password = password}

| Псевдонимы | Нет |
| --- | --- |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |Нет |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

### <a name="sendhostmessagestooutput"></a>Параметр SendHostMessagesToOutput
Если установлено значение true, оправляет сообщения из сценария в поток вывода.

| Псевдонимы | Нет |
| --- | --- |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |False |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

## <a name="remarks"></a>Примечания
Подробное описание того, как использовать сценарий для создания сред разработки и тестирования, см. в статье [Использование скриптов Windows PowerShell для публикации в среды разработки и тестирования](vs-azure-tools-publishing-using-powershell-scripts.md).

В файле конфигурации JSON указаны данные объектов, которые необходимо развернуть. Он содержит сведения, указанные при создании проекта, например имя, группу сходства, образ виртуального жесткого диска и размер виртуальной машины. Он также включает конечные точки виртуальной машины, подготавливаемые базы данных (если они есть) и параметры веб-развертывания. В следующем коде показан пример файла конфигурации JSON.

```
{
    "environmentSettings": {
        "cloudService": {
            "name": "myvmname",
            "affinityGroup": "",
            "location": "China North",
            "virtualNetwork": "",
            "subnet": "",
            "availabilitySet": "",
            "virtualMachine": {
                "name": "myvmname",
                "vhdImage": "a699494373c04fc0bc8f2bb1389d6106__Windows-Server-2012-R2-201404.01-en.us-127GB.vhd",
                "size": "Small",
                "user": "vmuser1",
                "password": "",
                "enableWebDeployExtension": true,
                "endpoints": [
                    {
                        "name": "Http",
                        "protocol": "TCP",
                        "publicPort": "80",
                        "privatePort": "80"
                    },
                    {
                        "name": "Https",
                        "protocol": "TCP",
                        "publicPort": "443",
                        "privatePort": "443"
                    },
                    {
                        "name": "WebDeploy",
                        "protocol": "TCP",
                        "publicPort": "8172",
                        "privatePort": "8172"
                    },
                    {
                        "name": "Remote Desktop",
                        "protocol": "TCP",
                        "publicPort": "3389",
                        "privatePort": "3389"
                    },
                    {
                        "name": "Powershell",
                        "protocol": "TCP",
                        "publicPort": "5986",
                        "privatePort": "5986"
                    }
                ]
            }
        },
        "databases": [
            {
                "connectionStringName": "",
                "databaseName": "",
                "serverName": "",
                "user": "",
                "password": ""
            }
        ],
        "webDeployParameters": {
            "iisWebApplicationName": "Default Web Site"
        }
    }
}
```

В файле конфигурации JSON можно изменить объекты, которые подлежат подготовке. Виртуальная машина и облачная служба необходимы, но раздел баз данных является необязательным.


<!-- Update_Description: update metedata properties -->