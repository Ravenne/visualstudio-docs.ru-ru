---
title: C# IntelliSense
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- C#, IntelliSense
- IntelliSense [C#]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ef4f8974f448ad9e2e81d4f1ba98aa02ed9da354
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62581972"
---
# <a name="c-intellisense"></a>C# IntelliSense

Возможности C# IntelliSense доступны при написании кода в редакторе и его отладке в командном окне [Режим интерпретации](../ide/reference/immediate-window.md).

## <a name="completion-lists"></a>Списки завершения

Списки завершения IntelliSense в C# содержат маркеры из операций составления списков членов, завершения слов и других. Они обеспечивают быстрый доступ к следующим элементам:

- члены типа или пространства имен;

- имена переменных, команд и функций;

- Фрагменты кода

- Ключевые слова языка

- Методы расширения

Список завершения в C# обладает достаточно широкими возможностями по фильтрации несоответствующих токенов и предварительному выбору токена в зависимости от контекста. Дополнительные сведения см. в разделе [Фильтрованные списки завершения](#filtered-completion-lists).

### <a name="code-snippets-in-completion-lists"></a>Фрагменты кода в списках завершения

В C# списки завершения содержат фрагменты кода, позволяющие легко вставлять предварительно определенные тела кода в программу. Фрагменты кода отображаются в списке завершения в виде [текста ярлыка](../ide/code-snippets-schema-reference.md#shortcut-element) фрагмента. Дополнительные сведения о фрагментах кода, доступных в C# по умолчанию, см. в описании [фрагментов кода C#](../ide/visual-csharp-code-snippets.md).

### <a name="language-keywords-in-completion-lists"></a>Ключевые слова языка в списках завершения

Список завершения в C# также содержит ключевые слова языка. Дополнительные сведения о ключевых словах языка C# см. в разделе [Ключевые слова C#](/dotnet/csharp/language-reference/keywords/index).

### <a name="extension-methods-in-completion-lists"></a>Методы расширения в списках завершения

Список завершения в C# содержит методы расширения, которые находятся в области действия.

> [!NOTE]
> В списке завершения отображаются не все методы расширения для объектов <xref:System.String>.

В методах расширения используется не такой значок, как в методах экземпляра. Справочник по значкам списка вы найдете в статье [Значки представления классов и обозревателя объектов](../ide/class-view-and-object-browser-icons.md). Если метод экземпляра и метод расширения с одинаковыми именами находятся в одной области, в списке завершения отображается значок метода расширения.

### <a name="filtered-completion-lists"></a>Фильтрованные списки завершения

IntelliSense удаляет ненужные элементы из списка завершения с помощью фильтров. C# фильтрует списки завершения по следующим элементам:

- **Интерфейсы и базовые классы**. IntelliSense автоматически удаляет элементы из списков завершения интерфейсов и базовых классов, как в базе объявлений класса, так и в списках интерфейса и ограничений. Например, перечисления не отображаются в списке завершения для базовых классов, поскольку перечисления не могут использоваться для базовых классов. Список завершения для базовых классов содержит только интерфейсы и пространства имен. Если выбрать элемент в списке и ввести запятую, IntelliSense удалит базовые классы из списка завершения, так как C# не поддерживает множественное наследование. Аналогичная логика используется и для предложений ограничения.

- **Атрибуты**. При применении атрибута к типу список завершения фильтруется таким образом, что в нем остаются только типы, которые получены из пространств имен, содержащих эти типы, например <xref:System.Attribute>.

- **Предложения CATCH**.

- **Инициализаторы объектов**. В списке завершения будут отображаться только те элементы, которые могут быть инициализированы.

- **Ключевое слово NEW**. При вводе `new` и нажатии клавиши **ПРОБЕЛ** появляется список завершения. Элемент в списке выбирается автоматически в зависимости от контекста в коде. Например, в списке завершения автоматически выбираются элементы для объявлений и операторов возврата в методах.

- **Ключевое слово ENUM**. При нажатии клавиши **ПРОБЕЛ** после ввода знака равенства для назначения перечисления появляется список завершения. Элемент в списке выбирается автоматически в зависимости от контекста в коде. Например, в списке завершения автоматически выбираются элементы после ввода ключевого слова "return" и при объявлении.

- **Операторы AS и IS**. Фильтрованный список завершения отображается автоматически при нажатии клавиши **ПРОБЕЛ** после ввода ключевого слова `as` или `is`.

- **События**. При вводе ключевого слова `event` список завершения содержит только типы делегатов.

- **Справочная система по параметрам** автоматически сортируется по первой перегрузке метода, соответствующей параметрам, по мере их ввода. Если существует несколько перегрузок метода, можно использовать кнопки со стрелками вверх и вниз для перехода к следующей возможной перегрузке в списке.

### <a name="most-recently-used-members"></a>Недавно использовавшиеся члены

IntelliSense запоминает последние элементы, выбранные во всплывающем окне [Список членов](../ide/using-intellisense.md) для автоматического завершения имени объекта. Когда вы откроете **список членов** в следующий раз, сверху будут отображаться элементы, которые недавно использовались. Журнал наиболее часто используемых членов списка очищается после завершения каждого сеанса Visual Studio.

### <a name="override"></a>override

Если ввести [override](/dotnet/csharp/language-reference/keywords/override), а затем нажать клавишу **ПРОБЕЛ**, IntelliSense покажет во всплывающем списке все допустимые элементы базового класса, которые можно переопределить. Если после приглашения `override` ввести тип возвращаемого значения метода, IntelliSense отобразит только методы, возвращающие этот тип. Если IntelliSense не сможет найти совпадения, будут показаны все члены базового класса.

### <a name="ai-enhanced-intellisense"></a>IntelliSense с возможностями искусственного интеллекта

Вы можете установить экспериментальное [расширение IntelliCode](/visualstudio/intellicode/intellicode-visual-studio) для Visual Studio, которое предоставляет списки завершения IntelliSense с использованием искусственного интеллекта. Это расширение предсказывает, какой API будет наиболее подходящим, а не просто возвращает список членов в алфавитном порядке. Оно формирует список динамически на основе текущего контекста вашего кода.

## <a name="automatic-code-generation"></a>Автоматическое генерирование кода

### <a name="add-using"></a>Добавить директиву using

Операция IntelliSense **Добавить директиву using** автоматически добавляет требуемую директиву `using` в файл кода. Это позволяет сосредоточить внимание на коде, который вы пишете, и не отвлекаться на другую часть кода.

Чтобы инициировать операцию **Добавить директиву using**, поместите курсор на ссылку на тип, которую не удается разрешить. Например, при создании консольного приложения и добавлении `XmlReader` в тело метода `Main` в соответствующей строке появляется подчеркивание красной волнистой линией, так как ссылку на тип не удается разрешить. После этого можно вызвать операцию **Добавить директиву using**, выбрав **быстрое действие**. **Быстрые действия** отображаются, только если курсор находится в несвязанном типе.

![Развернутое быстрое действие "Добавить директиву using"](../ide/media/addusing-quickaction.png)

Щелкните значок лампочки с ошибкой и выберите пункт **using System.Xml;**, чтобы автоматически добавить директиву using.

### <a name="remove-and-sort-usings"></a>Удаление и сортировка директив using

Параметр **Удалить и сортировать директивы using** позволяет сортировать и удалять объявления `using` и `extern`, не меняя поведение исходного кода. Со временем исходные файлы могут стать перегруженными, и их станет трудно читать по причине ненужных и неорганизованных директив `using`. Параметр **Удалить и сортировать директивы using** сжимает исходный код, удаляя неиспользуемые директивы `using` и улучшая читаемость путем их сортировки. В меню **Правка** выберите **IntelliSense**, а затем **Упорядочить директивы Using**.

### <a name="implement-interface"></a>Реализация интерфейса

Технология IntelliSense может облегчить реализацию [интерфейса](/dotnet/csharp/language-reference/keywords/interface) при работе в редакторе кода. Обычно для правильной реализации интерфейса нужно создать объявление метода для каждого члена интерфейса в классе. При использовании IntelliSense после ввода имени интерфейса в объявлении класса появляется значок **быстрых действий** в виде лампочки. Он позволяет выбрать вариант автоматической реализации интерфейса с помощью явного или неявного именования. При явном именовании объявления метода содержат имя интерфейса. В случае неявного именования объявления метода не указывают, к какому интерфейсу они принадлежат. Доступ к явно именованному методу интерфейса может осуществляться только через экземпляр интерфейса, а не через экземпляр класса. Дополнительные сведения см. в разделе [Явная реализация интерфейса](/dotnet/csharp/programming-guide/interfaces/explicit-interface-implementation).

Реализация интерфейса создает минимально необходимый для работы интерфейса набор заглушек методов. Если базовый класс уже реализует часть интерфейса, заглушки не восстанавливаются.

### <a name="implement-abstract-base-class"></a>Реализация абстрактного базового класса

IntelliSense предоставляет возможность автоматической реализации членов абстрактного базового класса при работе в редакторе кода. В обычном режиме для реализации членов абстрактного базового класса для каждого метода абстрактного базового класса в производном классе необходимо создать новое определение метода. При использовании IntelliSense после ввода имени абстрактного базового класса в объявлении класса появляется значок **быстрых действий** в виде лампочки. Он дает возможность автоматической реализации методов базового класса.

Заглушки метода, создаваемые функцией **Реализовать абстрактный базовый класс**, моделируются фрагментом кода, определенным в файле *MethodStub.snippet*. Фрагменты кода можно изменять. Дополнительные сведения см. в разделе [Пошаговое руководство: создание фрагмента кода](../ide/walkthrough-creating-a-code-snippet.md).

### <a name="generate-from-usage"></a>Создание в результате использования

Возможность **Создание в результате использования** позволяет использовать классы и элементы до того, как они будут определены. Для любого класса, конструктора, метода, свойства, поля или перечисления, которое вы хотите использовать, но еще не определили, можно создать заглушку. Новые типы и члены можно создавать, не покидая текущего расположения в коде. Это сводит до минимума нарушения в рабочем процессе.

Каждый неопределенный идентификатор подчеркивается красной волнистой линией. При перемещении указателя мыши на такой идентификатор в подсказке появляется сообщение об ошибке. Для отображения нужных параметров можно выполнить одну из следующих процедур:

- Щелкните неопределенный идентификатор. Под идентификатором появляется значок **быстрых действий** в виде лампочки с ошибкой. Щелкните лампочку с ошибкой.

- Щелкните неопределенный идентификатор и нажмите клавиши **CTRL**+**.** (**CTRL**+точка).

- Щелкните неопределенный идентификатор правой кнопкой мыши и выберите пункт **Быстрые действия и рефакторинг**.

В число появившихся параметров могут входить следующие:

- **Сформировать свойство**

- **Сформировать поле**

- **Сформировать метод**

- **Сформировать класс**

- **Сформировать новый тип** (для класса, структуры, интерфейса или перечисления)

## <a name="generate-event-handlers"></a>Сформировать обработчики событий

В редакторе кода IntelliSense упрощает подключение методов (обработчиков событий) к полям событий.

Если ввести оператор `+=` после поля события в файле *CS*, IntelliSense предложит нажать клавишу **TAB**. В результате будет вставлен новый экземпляр делегата, который указывает на метод, обрабатывающий событие.

![Автопривязка кнопки](../ide/media/vxautohookup.gif)

При нажатии клавиши **TAB** IntelliSense автоматически завершает оператор и отображает ссылку на обработчик событий в виде выделенного текста в редакторе кода. Для завершения автоматического подключения события IntelliSense предлагает снова нажать клавишу **TAB** или создать пустую заглушку для обработчика событий.

![Генерация обработчика событий](../ide/media/vxgenerateeventhandler.gif)

> [!NOTE]
> Если новый делегат, созданный IntelliSense, ссылается на существующий обработчик событий, IntelliSense выводит эти сведения во всплывающей подсказке. Эту ссылку можно изменить — соответствующий текст уже выделен в редакторе кода. В противном случае автоматическое подключение события завершается на этом этапе.

При нажатии клавиши **TAB** IntelliSense заглушает метод с корректной сигнатурой и размещает указатель в теле обработчика событий.

> [!NOTE]
> Для возврата к оператору привязки к событию используйте команду **Назад** в меню **Вид** (**CTRL**+**-**).

## <a name="see-also"></a>См. также

- [Использование IntelliSense](../ide/using-intellisense.md)
- [Интегрированная среда разработки Visual Studio](../get-started/visual-studio-ide.md)