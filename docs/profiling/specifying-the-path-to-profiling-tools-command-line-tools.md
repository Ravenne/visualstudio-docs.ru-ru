---
title: Указание пути к программам командной строки Средств профилирования | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 48ac65ef8fb7a67783a3c9c5a9652accf86821fc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979839"
---
# <a name="specify-the-path-to-profiling-tools-command-line-tools"></a>Указание пути к программам командной строки средств профилирования

Путь средств профилирования командной строки [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] не добавляется в переменную среды PATH. На 32-разрядных компьютерах эти средства находятся в одном каталоге. Существуют 64- и 32-разрядные версии средств профилирования для 64-разрядных компьютеров.

## <a name="32-bit-computers"></a>32-разрядные компьютеры
::: moniker range=">=vs-2019"
 Для машинного кода интерфейсы API профилировщика Visual Studio находятся в файле *VSPerf.dll*. Файл заголовка *VSPerf.h* и библиотека импорта *VSPerf.lib* расположены в каталоге *Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK*.
::: moniker-end
::: moniker range="vs-2017"
 Для машинного кода интерфейсы API профилировщика Visual Studio находятся в файле *VSPerf.dll*. Файл заголовка *VSPerf.h* и библиотека импорта *VSPerf.lib* расположены в каталоге *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK*.
::: moniker-end

 Для управляемого кода интерфейсы API находятся в файле *Microsoft.VisualStudio.Profiler.dll*. Эта библиотека DLL находится в каталоге *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*.

## <a name="64-bit-computers"></a>64-разрядные компьютеры

На 64-разрядных компьютерах укажите путь в соответствии с целевой платформой профилируемого приложения.

::: moniker range=">=vs-2019"
- Для 32-разрядных приложений каталог средств профилирования по умолчанию:

     (машинный код) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK* (управляемый код) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

- Для 64-разрядных приложений каталог средств профилирования по умолчанию:

     (машинный код) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\x64\PerfSDK* (управляемый код) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end

::: moniker range="vs-2017"
- Для 32-разрядных приложений каталог средств профилирования по умолчанию:

     (машинный код) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK* (управляемый код) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

- Для 64-разрядных приложений каталог средств профилирования по умолчанию:

     (машинный код) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\x64\PerfSDK* (управляемый код) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end