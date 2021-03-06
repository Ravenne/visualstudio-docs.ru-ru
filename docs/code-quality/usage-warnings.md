---
title: предупреждения использования
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.usagerules
helpviewer_keywords:
- warnings, usage
- managed code analysis warnings, usage warnings
- usage warnings
ms.assetid: fe7dc2a3-289d-4bf7-a1e4-0947a81287c4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b8f2deaa728a2bcd71bcd2264fcd110aee7982e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62825257"
---
# <a name="usage-warnings"></a>предупреждения использования
Предупреждения использования поддерживают правильное использование платформы .NET Framework.

## <a name="in-this-section"></a>В этом разделе

|Правило|Описание|
|----------|-----------------|
|[CA1801: Проверьте неиспользуемые параметры](../code-quality/ca1801-review-unused-parameters.md)|Сигнатура метода включает параметр, не использующийся в основной части метода.|
|[CA1806: Не игнорируйте результаты метода](../code-quality/ca1806-do-not-ignore-method-results.md)|Создается, но никогда не используется новый объект, либо вызывается метод, который создает и возвращает новую строку, и такая новая строка никогда не используется, либо метод COM или P/Invoke возвращает HRESULT или код ошибки, который никогда не используется.|
|[CA1816: Вызовите GC. SuppressFinalize правильно](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Метод, являющийся реализацией Dispose, не вызывает сборщик Мусора. SuppressFinalize; или метод, не являющийся реализацией Dispose вызывает сборщик Мусора. SuppressFinalize; или вызовы методов сборки Мусора. SuppressFinalize и передает что-то другое (Me в Visual Basic).|
|[CA2200: Исключение для сохранения сведений о стеке](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|Исключение выдается заново, и явным образом задается исключение в операторе throw. Если исключение повторно создается заданием исключения в операторе throw, список вызовов метода между исходным методом, создавшим исключение и текущим методом будет утерян.|
|[CA2201: Не вызывайте зарезервированные типы исключений](../code-quality/ca2201-do-not-raise-reserved-exception-types.md)|В результате исходную ошибку трудно обнаружить и устранить.|
|[CA2202: Не удаляйте объекты несколько раз](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|Реализация метода содержит пути кода, которые могли стать причиной многократного вызова метода System.IDisposable.Dispose или эквивалентного метода Dispose (например, метода Close() для некоторых типов) для одного и того же объекта.|
|[CA2204: Литералы должны иметь правильное правописание](../code-quality/ca2204-literals-should-be-spelled-correctly.md)|Литеральная строка в теле метода содержит одно или несколько слов, не распознаваемых библиотекой системы проверки орфографии Майкрософт.|
|[CA2205: Используйте управляемые эквиваленты Win32 API](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|Неуправляемого определен метод, и существует метод с эквивалентной функциональностью в библиотеке классов .NET Framework.|
|[CA2207: Инициализируйте статические поля типа значений встроенными средствами](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|Тип значения объявляет явный статический конструктор. Чтобы устранить нарушение данного правила, выполните инициализацию всех статических данных при их объявлении и удалите статический конструктор.|
|[CA2208: Правильно создавайте экземпляры аргументов исключений](../code-quality/ca2208-instantiate-argument-exceptions-correctly.md)|Вызывается конструктор по умолчанию (без параметров), принадлежащий к типу исключения ArgumentException или унаследованный от него, или неправильный аргумент строки передается параметризованному конструктору, принадлежащему к типу исключения ArgumentException или унаследованному от него.|
|[CA2211: Неконстантные поля не должны быть видимыми](../code-quality/ca2211-non-constant-fields-should-not-be-visible.md)|Для статических полей, которые не являются константными и доступными только для чтения, невозможно обеспечить потокобезопасность. Доступ к подобным полям должен тщательно контролироваться и требуются дополнительные методы программирования для синхронизации доступа к объекту класса.|
|[CA2212: Не следует помечать обслуживаемые компоненты атрибутом WebMethod](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|Метод, в типе, унаследованном от System.EnterpriseServices.ServicedComponent, помечен атрибутом System.Web.Services.WebMethodAttribute. Так как атрибут WebMethodAttribute и метод ServicedComponent имеют разное поведение и предъявляют конфликтующие требования к контексту и потоку транзакций, в некоторых сценариях поведение метода будет неправильным.|
|[CA2213: следует высвобождать высвобождаемые поля](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Тип, реализующий System.IDisposable, объявляет поля, принадлежащие к типам, которые также реализуют IDisposable. Метод Dispose поля не вызывается методом Dispose объявляющего типа.|
|[CA2214: Не вызывайте переопределяемые методы в конструкторах](../code-quality/ca2214-do-not-call-overridable-methods-in-constructors.md)|Когда конструктор вызывает виртуальный метод, вполне возможно, что конструктор экземпляра, который вызывает метод не выполнен.|
|[CA2215: Методы Dispose должны вызывать метод dispose базового класса](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)|Если тип наследуется от удаляемого типа, он должен вызвать метод Dispose базового типа из собственного метода Dispose.|
|[CA2216: Высвобождаемые типы должны объявлять метод завершения](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|Тип, который реализует System.IDisposable и имеет поля, предусматривающие использование неуправляемых ресурсов, не реализует метод завершения, как описано в Object.Finalize.|
|[CA2217: Не следует помечать перечисления атрибутом FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)|Видимый для внешнего кода перечисление помечено атрибутом FlagsAttribute и имеет одно или несколько значений, которые не являются степенью двойки или сочетание других определенных значений в перечислении.|
|[CA2218: Переопределяйте GetHashCode при переопределении Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)|GetHashCode возвращает значение на основе текущего экземпляра, используемое для алгоритмов хэширования и структур данных, таких как хэш-таблица. Два равных объекта, принадлежащие к одному и тому же типу, должны возвращать один и тот же хэш-код.|
|[CA2219: Не вызывайте исключения в предложениях исключений](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)|Если исключение создается в предложении finally или fault, новое исключение скрывает активное исключение. Если исключение создается в предложении filter, среда выполнения перехватывает исключение без оповещения. В результате исходную ошибку трудно обнаружить и устранить.|
|[CA2220: Методы завершения должны вызывать метод завершения базового класса](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|Финализация должна распространятся посредством иерархии наследования. Для этого типы должны вызывать свой метод Finalize базового класса из собственного метода Finalize.|
|[CA2221: Методы завершения должны быть защищены](../code-quality/ca2221-finalizers-should-be-protected.md)|В методах завершения должен использоваться модификатор доступа из семейства.|
|[CA2222: Не уменьшайте видимость унаследованных членов](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|Не следует изменять модификатор доступа для унаследованных членов. Если сделать унаследованный член закрытым, то доступ вызывающих объектов к реализации метода базового класса все равно не будет запрещен.|
|[CA2223: Члены должны различаться не только возвращаемым типом](../code-quality/ca2223-members-should-differ-by-more-than-return-type.md)|Среда CLR позволяет использовать возвращаемые типы для различения совпадающих в остальном членов, однако эта функция не входит в спецификацию CLS и поддерживается не всеми языками программирования .NET.|
|[CA2224: Переопределяйте равенство при перегрузке оператора равенства](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|Открытый тип реализует оператор равенства, но не переопределяет Object.Equals.|
|[CA2225: Оператор дополнения с именами](../code-quality/ca2225-operator-overloads-have-named-alternates.md)|Обнаружена перегрузка оператора, однако не найден ожидаемый именованный альтернативный метод. Именованный альтернативный член предоставляет доступ к ту же функциональность, что оператор и предоставляется для разработчиков, которые программируют на языках, которые не поддерживает перегруженные операторы.|
|[CA2226: Операторы должны быть симметричны](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|Тип реализует оператор равенства или неравенства и не реализует противоположный оператор.|
|[CA2227: Свойства коллекции должны быть только для чтения](../code-quality/ca2227-collection-properties-should-be-read-only.md)|Свойство коллекции, допускающее запись, позволяет пользователю заменять одну коллекцию другой. Свойство только для чтения предотвращает замену коллекции, но по-прежнему допускает установку, настройку отдельных членов.|
|[CA2228: Не следует поставлять невыпущенные форматы ресурсов](../code-quality/ca2228-do-not-ship-unreleased-resource-formats.md)|Файлы ресурсов, которые были созданы с помощью предварительных версий платформы .NET Framework может стать недоступной в поддерживаемых версиях платформы .NET Framework.|
|[CA2229: реализуйте конструкторы сериализации](../code-quality/ca2229-implement-serialization-constructors.md)|Чтобы устранить нарушение этого правила, реализуйте конструктор сериализации. Для запечатанного класса конструктор должен быть закрытым, а в иных случаях — защищенным.|
|[CA2230: Используйте параметры для аргументов переменной](../code-quality/ca2230-use-params-for-variable-arguments.md)|Открытый или защищенный тип содержит открытый или защищенный метод, который использует соглашение о вызовах VarArgs вместо ключевого слова params.|
|[CA2231: перегрузите оператор равенства на переопределяющем типе ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Тип значения переопределяет Object.Equals, но не реализует оператор равенства.|
|[CA2232: Точки входа Марк Windows Forms меткой STAThread](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|Атрибут STAThreadAttribute указывает, что потоковой моделью COM для приложения является однопотоковое подразделение. Данный атрибут должен находиться в точке входа любого приложения, использующего Windows Forms; если он отсутствует, компоненты Windows могут работать неправильно.|
|[CA2233: Операции не должно быть переполнений](../code-quality/ca2233-operations-should-not-overflow.md)|Не следует выполнять арифметические операции без предварительной проверки операндов, чтобы убедиться в том, что результат операции не находится за пределами диапазона возможных значений для используемых типов данных.|
|[CA2234: Передавайте объекты System.Uri вместо строк](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)|Вызывается метод, имеющий параметр строки, имя которого содержит uri, URI, urn, URN, url или URL.  Объявляющий тип метода содержит соответствующую перегрузку метода, которая имеет параметр System.Uri.|
|[CA2235. Пометьте все несериализуемые поля](../code-quality/ca2235-mark-all-non-serializable-fields.md)|Экземпляр поля несериализуемого типа объявлен в сериализуемом типе.|
|[CA2236: Вызывайте методы базового класса для типов ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|Чтобы устранить нарушение этого правила, вызовите метод базового типа GetObjectData или конструктор сериализации из соответствующего метода производного типа или конструктора.|
|[CA2237. Пометьте типы ISerializable атрибутом SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|Распознаваемых среда CLR как сериализуемый, типы должны быть помечены атрибутом SerializableAttribute даже если тип использует пользовательскую процедуру сериализации посредством реализации интерфейса ISerializable.|
|[CA2238: Правильно реализовывать методы сериализации](../code-quality/ca2238-implement-serialization-methods-correctly.md)|Метод, обрабатывающий событие сериализации, не имеет правильной сигнатуры, типа возвращаемого значения или отображения.|
|[CA2239: Предоставляйте методы десериализации для необязательных полей](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|Тип имеет поле, помеченное атрибутом System.Runtime.Serialization.OptionalFieldAttribute, и тип не предоставляет методы обработки событий десериализации.|
|[CA2240: Правильно реализуйте ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)|Чтобы устранить нарушение этого правила, сделайте метод GetObjectData и переопределяемым и убедитесь, что все поля экземпляра включены в процессе сериализации или явно помечены атрибутом NonSerializedAttribute.|
|[CA2241: Предоставьте правильные аргументы методам форматирования](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|Аргумент формата, переданный методу System.String.Format не содержит элемент форматирования, соответствующий каждому аргументу объекта, или наоборот.|
|[CA2242: Правильно выполняйте проверку NaN](../code-quality/ca2242-test-for-nan-correctly.md)|Это выражение проверяет значение на соответствие Single.Nan или Double.Nan. Используйте Single.IsNan(Single) или Double.IsNan(Double) для проверки значения.|
|[CA2243: Синтаксический анализ строковых литералов атрибута должен правильно](../code-quality/ca2243-attribute-string-literals-should-parse-correctly.md)|Строкового литерала атрибута неверно интерпретирует для URL-адрес, идентификатор GUID или версии.|