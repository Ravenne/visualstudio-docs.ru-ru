---
title: -Clean (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- builds [Team System], cleaning files
- Clean Devenv switch
- /Clean Devenv switch
- Devenv, /Clean switch
ms.assetid: 79929dfd-22c9-4cec-a0d0-a16f15b8f7e4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 810f05b0838f27004bee983dc0acf7a3009e22a0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62573096"
---
# <a name="clean-devenvexe"></a>/Clean (devenv.exe)

Удаляет все промежуточные файлы и выходные каталоги.

## <a name="syntax"></a>Синтаксис

```shell
devenv SolutionName /Clean [Config [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>Аргументы

- *SolutionName*

  Обязательный. Полный путь и имя для файла решения.

- *Config*

  Необязательный параметр. Конфигурация (например, `Debug` или `Release`) для удаления промежуточных файлов из решения с именем, указанным в *SolutionName*. Если доступно несколько платформ решений, необходимо также указать платформу (например, `Debug|Win32`). Если этот аргумент не определен или является пустой строкой (`""`), используется действующая конфигурация решения.

- `/Project` *ProjName*

  Необязательный параметр. Путь и имя для файла проекта в решении. Можно ввести отображаемое имя проекта или относительный путь из папки *SolutionName* к файлу проекта. Можно также ввести полный путь и имя файла проекта.

- `/ProjectConfig` *ProjConfigName*

  Необязательный параметр. Имя конфигурации сборки проекта, например `Debug` или `Release`, для использования при очистке указанного проекта `/Project`. Если доступно несколько платформ решений, необходимо также указать платформу (например, `Debug|Win32`). Если этот параметр задан, он переопределяет аргумент *Config*.

- `/Out` *OutputFilename*

  Необязательный параметр. Имя файла, в который вы хотите отправить выходные данные средства. Если файл уже существует, средство добавляет в его конец выходные данные.

## <a name="remarks"></a>Примечания

Этот параметр выполняет ту же функцию, что и команда меню **Очистить решение** в интегрированной среде разработки.

Строки с пробелами заключаются в двойные кавычки.

Сводные данные по очистке и сборке, включая ошибки, можно вывести в окне **Команда** или файле журнала, указанном параметром [/Out](out-devenv-exe.md).

Если параметр `/Project` не задан, операция очистки выполняется для всех проектов в решении, даже при выборе *FileName* в качестве файла проекта.

## <a name="example"></a>Пример

Первый пример очищает решение `MySolution` с использованием конфигурации по умолчанию, указанной в файле решения.

Второй пример очищает проект `CSharpWinApp` с использованием конфигурации сборки проекта `Debug` в решении `MySolution`.

```shell
devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /Clean

devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /Clean "Debug" /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig "Debug"
```

## <a name="see-also"></a>См. также

- [Параметры командной строки для devenv](../../ide/reference/devenv-command-line-switches.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)