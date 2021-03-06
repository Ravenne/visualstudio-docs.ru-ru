---
title: Параметры командной строки для команды devenv
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- switches, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: db9aaeb48095b058abb0deefa342598eefeed1b9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62970231"
---
# <a name="devenv-command-line-switches"></a>Параметры командной строки для Devenv

Devenv позволяет устанавливать различные параметры для интегрированной среды разработки, выполнять сборку, отладку и развертывание проектов из командной строки. Используйте эти параметры для запуска интегрированной среды разработки из файла скрипта или из BAT-файла (например, скрипта сборки программы в ночное время), либо для запуска среды в особой конфигурации.

> [!NOTE]
> Для задач, связанных со сборкой, вместо devenv рекомендуется использовать MSBuild. Дополнительные сведения см. в [справочнике по командной строке MSBuild](../../msbuild/msbuild-command-line-reference.md).

См. дополнительные сведения о [параметрах командной строки devenv для разработки VSPackage](../../extensibility/devenv-command-line-switches-for-vspackage-development.md).

## <a name="devenv-switch-syntax"></a>Синтаксис параметров команды devenv

Команды, начинающиеся с `devenv`, обрабатываются служебной программой `devenv.com`, которая обеспечивает доставку выходных данных с помощью стандартных системных потоков, таких как `stdout` и `stderr`. Программа определяет правильную переадресацию ввода-вывода при захвате выходных данных, например в TXT-файл.

Кроме того, для команд, начинающихся с `devenv.exe`, можно использовать те же параметры, но они будут обходить служебную программу `devenv.com`. Использование `devenv.exe` напрямую запрещает отображение выходных данных на консоли.

Синтаксис для параметров `devenv` похож на правила для других служебных программ командной строки DOS. Приведенные ниже правила синтаксиса действуют для всех параметров `devenv` и их аргументов.

- Команды начинаются с `devenv`.

- Параметры обрабатываются без учета регистра.

- Параметр можно указать с помощью дефиса (-) или косой черты (/).

- При указании решения или проекта первым аргументом будет имя файла решения или файла проекта, включающее путь к файлу.

- Если первый аргумент — это файл, который не является решением или проектом, этот файл откроется в соответствующем редакторе в новом экземпляре интегрированной среды разработки.

- Если вместо имени файла решения указать имя файла проекта, команда `devenv` выполняет поиск файла решения с этим именем в родительской папке файла проекта. Например, команда `devenv myproject1.vbproj /build` ищет родительский каталог для файла решения с именем `myproject1.sln`.

  > [!NOTE]
  > В этой родительской папке должен находиться только один файл решения, ссылающийся на проект. Если в родительской папке отсутствует файл решения, который ссылается на проект, или если в ней два или более файлов решения, ссылающихся на проект, создается временный файл решения.

- Пути к файлам и имена файлов, содержащие пробелы, должны заключаться в кавычки (""). Например, `"c:\project a\"`.

- Разделяйте параметры и аргументы в одной строке одиночными пробелами. Например, команда `devenv /log output.txt` открывает интегрированную среду разработки и выводит все данные журнала для текущего сеанса в файл output.txt.

- В командах `devenv` нельзя использовать синтаксис сопоставления шаблонов.

## <a name="devenv-switches"></a>Параметры команды devenv

Перечисленные ниже параметры командной строки отображают интегрированную среду разработки и выполняют описанные задачи.

|Параметр командной строки|Описание|
| - |-----------------|
|[/Command](command-devenv-exe.md)|Запускает среду IDE и выполняет указанную команду.<br /><br /> `devenv /command "nav https://docs.microsoft.com/"`|
|[/DebugExe](debugexe-devenv-exe.md)|Загружает исполняемый файл C++ под управлением отладчика. Этот параметр недоступен для исполняемых файлов Visual Basic или C#. Дополнительные сведения см. в разделе [Автоматический запуск процесса в отладчике](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger).<br /><br /> `devenv /debugexe mysln.exe`|
|[/Diff](diff.md)|Сравнение двух файлов. Принимает четыре параметра: *SourceFile*, *TargetFile*, *SourceDisplayName* (не обязательный) и *TargetDisplayName* (не обязательный).<br /><br /> `devenv /diff File1 File2 Alias1 Alias2`|
|[/DoNotLoadProjects](donotloadprojects-devenv-exe.md)|Открывает указанное решение без загрузки каких-либо проектов.<br /><br /> `devenv /donotloadprojects mysln.sln`|
|[/Edit](edit-devenv-exe.md)|Открывает указанные файлы в запущенном экземпляре этого приложения. Если нет запущенных экземпляров, то запускается новый экземпляр с упрощенной структурой окна.<br /><br /> `devenv /edit File1 File2`|
|[/LCID или /L](lcid-devenv-exe.md)|Задает язык по умолчанию для среды IDE. Если указанный язык не включен в пакет установки Visual Studio, этот параметр игнорируется.<br /><br /> `devenv /l 1033`|
|[/Log](log-devenv-exe.md)|Запускает Visual Studio и записывает все действия в файл журнала.<br /><br /> `devenv /log mylogfile.xml`|
|[/NoSplash](nosplash-devenv-exe.md)|Открывает интегрированную среду разработки без отображения экрана-заставки.<br /><br /> `devenv /nosplash File1 File2`|
|[/Run или /R](run-devenv-exe.md)|Компилирует и запускает указанное решение.<br /><br /> `devenv /run mysln.sln`|
|[/RunExit](runexit-devenv-exe.md)|Компилирует и выполняет указанное решение, свертывая окно IDE при выполнении решения и закрывая IDE после завершения выполнения.<br /><br /> `devenv /runexit mysln.sln`|
|[/SafeMode](safemode-devenv-exe.md)|Запускает Visual Studio в безопасном режиме. Этот параметр загружает только среду и службы по умолчанию, а также прилагаемые версии сторонних пакетов.<br /><br /> У этого параметра нет аргументов.|
|[/UseEnv](useenv-devenv-exe.md)|Инициирует использование в интегрированной среде разработки переменных среды PATH, INCLUDE, LIBPATH и LIB для компиляции на C++. Параметр устанавливается с рабочей нагрузкой **Разработка классических приложений на C++**. Дополнительные сведения см. в статье [Установка переменных пути и среды при построении из командной строки](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds).|

Следующие параметры командной строки не отображают интегрированную среду разработки.

|Параметр командной строки|Описание|
| - |-----------------|
|[/?](q-devenv-exe.md)|Отображает справку по параметрам `devenv` в **окне командной строки**.<br /><br /> У этого параметра нет аргументов.|
|[/Build](build-devenv-exe.md)|Выполняет сборку указанного решения или проекта согласно конфигурации заданного решения.<br /><br /> `devenv mysln.sln /build`|
|[/Clean](clean-devenv-exe.md)|Удаляет все файлы, созданные командой сборки, не затрагивая исходные файлы.<br /><br /> `devenv mysln.sln /clean`|
|[/Deploy](deploy-devenv-exe.md)|Выполняет сборку решения, а также файлов, необходимых для развертывания, согласно конфигурации решений.<br /><br /> `devenv mysln.sln /deploy`|
|[/Out](out-devenv-exe.md)|Позволяет указать файл для приема ошибок во время сборки.<br /><br /> `devenv mysln.sln /build Debug /out log.txt`|
|[/Project](project-devenv-exe.md)|Проект, который требуется собрать, очистить или развернуть. Этот параметр можно использовать, только если был указан параметр `/Build`, `/Rebuild`, `/Clean` или `/Deploy`.<br /><br /> `devenv mysln.sln /build Debug /project proj1`|
|[/ProjectConfig](projectconfig-devenv-exe.md)|Задает конфигурацию проекта, которую требуется собрать или развернуть. Этот параметр можно использовать, только если был указан параметр `/Project`.<br /><br /> `devenv mysln.sln /build Release /project proj1 /projectconfig Release`|
|[/Rebuild](rebuild-devenv-exe.md)|Выполняет очистку, а затем сборку указанного решения или проекта согласно конфигурации заданного решения.<br /><br /> `devenv mysln.sln /rebuild`|
|[/ResetSettings](resetsettings-devenv-exe.md)|Восстанавливает параметры Visual Studio по умолчанию. При необходимости выполняет сброс параметров в соответствии с указанным файлом `.vssettings`.<br /><br /> `devenv /resetsettings mysettings.vssettings`|
|[/Upgrade](upgrade-devenv-exe.md)|Обновляет указанный файл решения и все его файлы проектов либо указанный файл проекта до текущих форматов Visual Studio для этих файлов.<br /><br /> `devenv mysln.sln /upgrade`|

## <a name="see-also"></a>См. также

- [Страница "Общие", папка "Среда", диалоговое окно "Параметры"](general-environment-options-dialog-box.md)
- [Параметры командной строки Devenv для разработки VSPackage](../../extensibility/devenv-command-line-switches-for-vspackage-development.md)
