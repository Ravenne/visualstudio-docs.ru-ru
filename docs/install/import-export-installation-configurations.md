---
title: Импорт или экспорт конфигураций установки
titleSuffix: ''
description: Из этой статьи вы узнаете, как использовать функцию конфигурации импорта и экспорта в Visual Studio
ms.date: 04/19/2019
ms.topic: conceptual
f1_keywords:
- vs.about
helpviewer_keywords:
- import installation configuration
- export installation configuration
- install Visual Studio
- Visual Studio installer
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: facbbf5903d683ea3a13bdd875dfe2b6c63b6367
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786403"
---
# <a name="import-or-export-installation-configurations"></a>Импорт или экспорт конфигураций установки

Вы можете настроить Visual Studio в своей организации с помощью файла конфигурации установки. Для этого просто экспортируйте сведения о рабочей нагрузке и компоненте в файл .vsconfig с помощью установщика Visual Studio. Затем вы сможете импортировать конфигурацию в новые или существующие установки.

Ниже описывается порядок действий.

::: moniker range="vs-2017"

> [!NOTE]
> Эта возможность доступна только в Visual Studio 2017, начиная с версии 15.9.

::: moniker-end

## <a name="export-a-configuration"></a>Экспорт конфигурации

Вы можете экспортировать файл конфигурации установки из уже установленного или устанавливаемого сейчас экземпляра Visual Studio.

1. Запустите Visual Studio Installer.

1. На карте продукта нажмите кнопку **Дополнительно** и выберите **Экспортировать конфигурацию**.

   ![Экспорт конфигурации с карты продукта в установщике Visual Studio](../install/media/vs-2019/vs-installer-export-config.png)

1. Найдите или введите расположение, в котором нужно сохранить файл .vconfig, и выберите **Просмотреть сведения**.

   ![Экспорт конфигурации из установщика Visual Studio](../install/media/vs-2019/export-configuration-confirmation.png)

1. Убедитесь, что выбраны нужные рабочие нагрузки и компоненты, и нажмите кнопку **Экспортировать**.

## <a name="import-a-configuration"></a>Импорт конфигурации

Когда вы будете готовы импортировать файл конфигурации установки, выполните следующие шаги.

1. Запустите Visual Studio Installer.

1. На карте продукта нажмите кнопку **Дополнительно** и выберите **Импортировать конфигурацию**.

1. Найдите файл .vconfig для импорта и выберите **Просмотреть сведения**.

1. Убедитесь, что выбраны нужные рабочие нагрузки и компоненты, и нажмите кнопку **Закрыть**.

::: moniker range="vs-2019"

## <a name="automatically-install-missing-components"></a>Автоматическая установка недостающих компонентов

**Новые возможности Visual Studio 2019:** Если вы сохранили файл .vsconfig в корневом каталоге решения, при открытии решения Visual Studio автоматически определит недостающие компоненты и предложит установить их.

![Обозреватель решений предлагает дополнительные компоненты](../install/media/vs-2019/solution-explorer-config-file.png)

Вы также можете создать файл .vsconfig непосредственно в обозревателе решений.

1. Щелкните правой кнопкой мыши файл решения.

1. Выберите **Добавить** > **Файл конфигурации установки**.

1. Подтвердите расположение, в котором нужно сохранить файл .vsconfig, и выберите **Просмотреть сведения**.

1. Убедитесь, что выбраны нужные рабочие нагрузки и компоненты, и нажмите кнопку **Экспортировать**.

::: moniker-end

> [!NOTE]
> См. подробнее о [настройке Visual Studio в организации с помощью .vsconfig](https://devblogs.microsoft.com/setup/configure-visual-studio-across-your-organization-with-vsconfig/).

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>См. также

* [Создание сетевой установки Visual Studio](create-a-network-installation-of-visual-studio.md)
* [Обновление сетевой установки Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Управление обновлением развертываний Visual Studio](controlling-updates-to-visual-studio-deployments.md)
* [Настройка параметров по умолчанию для корпоративного развертывания](set-defaults-for-enterprise-deployments.md)
