---
title: Создание доменного языка на основе Windows Forms
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eb5f395952b17b6937dc264f8bec8021e6627d45
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438171"
---
# <a name="creating-a-windows-forms-based-domain-specific-language"></a>Создание доменного языка на основе Windows Forms
Windows Forms можно использовать для отображения состояния модели доменного языка (DSL), вместо использования на схеме DSL. В этом разделе рассматривается привязка формы Windows к DSL, используя пакет SDK моделирования и визуализации Visual Studio.

 ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png) экземпляра DSL, показывая пользовательский Интерфейс формы Windows и обозреватель моделей.

## <a name="creating-a-windows-forms-dsl"></a>Создание форм Windows DSL
 **Минимальный конструктор WinForm** шаблон DSL создает минимальный DSL, который можно изменить в соответствии с вашими требованиями.

#### <a name="to-create-a-minimal-winforms-dsl"></a>Чтобы создать минимальный DSL WinForms

1. Создайте DSL из **минимальный конструктор WinForm** шаблона.

    В этом пошаговом руководстве рассматриваются следующие имена:

   | | |
   |-|-|
   | Имя решения и DSL | FarmApp |
   | Пространство имен | Company.FarmApp |

2. Поэкспериментируйте с начальной пример, в котором шаблон предоставляет:

   1. Преобразуйте все шаблоны.

   2. Построение и запуск образца (**CTRL + F5**).

   3. В экспериментальном экземпляре Visual Studio, откройте `Sample` файл отладки проекта.

        Обратите внимание на то, что он отображается в элементе управления Windows Forms.

        Также вы увидите элементы модели, отображаемое в обозревателе.

        Добавьте некоторые элементы в форме или обозревателя и обратите внимание на то, что они отображаются в других отображается.

   В основной экземпляр Visual Studio Обратите внимание на следующие аспекты в решение DSL:

- `DslDefinition.dsl` не содержит схемы элементов. Это обусловлено схем DSL не будет использовать для просмотра моделей, экземпляр данного DSL. Вместо этого форму Windows будет привязан к модели и элементы в форме будет отображаться модели.

- В дополнение к `Dsl` и `DslPackage` проекты, решение содержит третий проект с именем `UI.` **пользовательского интерфейса** проект содержит определение элемента управления Windows Forms. `DslPackage` зависит от `UI`, и `UI` зависит от `Dsl`.

- В `DslPackage` проекта, `UI\DocView.cs` содержит код, который отображает элемент управления Windows Forms, который определен в `UI` проекта.

- `UI` Проект содержит рабочий образец элемента управления формы, привязанный к линии DSL. Тем не менее он не будут работать при изменении определения DSL. `UI` Проект содержит:

    - Класс Windows Forms с именем `ModelViewControl`.

    - Файл с именем `DataBinding.cs` , содержащий дополнительные частичное определение `ModelViewControl`. Чтобы просмотреть его содержимое в **обозревателе решений**, откройте контекстное меню для файла и выберите **Просмотр кода**.

### <a name="about-the-ui-project"></a>О проекте пользовательского интерфейса
 При обновлении в файл определения DSL, для определения собственного DSL, необходимо будет обновить элемент управления в `UI` проекта для отображения в DSL. В отличие от `Dsl` и `DslPackage` проектов, образец `UI` проект не был создан из `DslDefinitionl.dsl`. Можно добавить файлы для создания кода, если требуется, несмотря на то, что в этом пошаговом руководстве, не рассматривается.

## <a name="updating-the-dsl-definition"></a>Обновление определения DSL
 Следующие определения DSL используется в этом пошаговом руководстве.

 ![DSL&#45;Wpf&#45;1](../modeling/media/dsl-wpf-1.png)

#### <a name="to-update-the-dsl-definition"></a>Для обновления определения доменного языка

1. Откройте файл DslDefinition.dsl в конструкторе DSL.

2. Удалить **ExampleElement**

3. Переименуйте **ExampleModel** доменного класса `Farm`.

     Присвойте ему свойства домена с именем `Size` типа **Int32**, и `IsOrganic` типа **логическое**.

    > [!NOTE]
    > Если вы удалите корневой класс домена, а затем создать новый корневой элемент, необходимо сбросить свойство корневой класс редактора. В **обозреватель DSL**выберите **редактор**. Затем в окне «Свойства» задайте **корневой класс** для `Farm`.

4. Используйте **именованный класс домена** средство для создания следующих классов домена:

    - `Field` — Присвойте это свойство домена с именем `Size`.

    - `Animal` -В окне «Свойства» задайте **модификатор наследования** для **абстрактный**.

5. Используйте **доменного класса** средство для создания следующих классов:

    - `Sheep`

    - `Goat`

6. Используйте **наследования** инструмент для упрощения `Goat` и `Sheep` наследовать от `Animal`.

7. Используйте **внедрения** средство для внедрения `Field` и `Animal` под `Farm`.

8. Может потребоваться очистка на схеме. Чтобы уменьшить число повторяющихся элементов, используйте **перенести сюда поддерево** команду в контекстном меню конечных элементов.

9. **Преобразовать все шаблоны** на панели инструментов в обозревателе решений.

10. Построение **Dsl** проекта.

    > [!NOTE]
    > На этом этапе других проектов будет построен без ошибок. Тем не менее мы хотим построить проект Dsl, чтобы его сборки доступен мастер источников данных.

## <a name="updating-the-ui-project"></a>Обновление проекта пользовательского интерфейса
 Теперь вы можете создать новый пользовательский элемент управления, который будет отображать данные, хранящиеся в модели DSL. Самый простой способ подключения пользовательского элемента управления к модели — через привязки данных. Привязка с именем типа адаптера данных **ModelingBindingSource** разработан специально для подключения к интерфейсам не VMSDK DSL.

#### <a name="to-define-your-dsl-model-as-a-data-source"></a>Для определения модели DSL в качестве источника данных

1. На **данных** меню, выберите **Показать источники данных**.

     Открывается окно **Источники данных**.

     Выберите **добавить новый источник данных**. Открывается **мастер настройки источника данных**.

2. Выберите **объект**, **Далее**.

     Разверните **Dsl**, **Company.FarmApp**и выберите **фермы**, который является корневой класс модели. Нажмите кнопку **Готово**.

     В обозревателе решений щелкните **пользовательского интерфейса** проекта теперь содержит **Properties\DataSources\Farm.datasource**

     Свойства и отношения класса модели отображаются в окне источников данных.

     ![DslWpf&#45;3](../modeling/media/dslwpf-3.png)

#### <a name="to-connect-your-model-to-a-form"></a>Для подключения к модели в форму

1. В **пользовательского интерфейса** проектов, удалите все существующие файлы .cs.

2. Добавьте новый **пользовательский элемент управления** файл с именем `FarmControl` для **пользовательского интерфейса** проекта.

3. В **источников данных** окно, в раскрывающемся меню **фермы**, выберите **сведения**.

    Оставьте настройки по умолчанию для других свойств.

4. Откройте FarmControl.cs в режиме конструктора.

    Перетащите **фермы** из окна источников данных на FarmControl.

    Набор элементов управления отображается, одной для каждого свойства. Свойства связи не создают элементы управления.

5. Удалить **farmBindingNavigator**. Этот элемент также автоматически создается в `FarmControl` конструктор, но он не является полезным для этого приложения.

6. С помощью панели элементов, создайте два экземпляра **DataGridView**и присвойте им имена `AnimalGridView` и `FieldGridView`.

   > [!NOTE]
   > Альтернативные делом возможность перетаскивать элементы животных и поля из окна источников данных в элементе управления. Это действие автоматически создает сетки данных и привязки между представлении в виде сетки и источником данных. Тем не менее эта привязка не работает правильно для доменных языков. Поэтому лучше создавать сетки данных и привязки вручную.

7. Если панель не содержит **ModelingBindingSource** инструмент, добавьте его. В контекстном меню **данных** вкладке, выберите **Выбор элементов**. В **Выбор элементов панели элементов** диалоговом окне выберите **ModelingBindingSource** из **вкладке .NET Framework**.

8. С помощью панели элементов, создайте два экземпляра **ModelingBindingSource**и присвойте им имена `AnimalBinding` и `FieldBinding`.

9. Задайте **DataSource** свойства каждого **ModelingBindingSource** для **farmBindingSource**.

     Задайте **DataMember** свойства **животных** или **поля**.

10. Задайте **DataSource** свойства `AnimalGridView` для `AnimalBinding`и `FieldGridView` для `FieldBinding`.

11. Измените макет элемента управления фермы на свой вкус.

    **ModelingBindingSource** — это адаптер, который выполняет несколько функций, которые относятся к DSL:

- Поиск обновлений в транзакции Store VMSDK.

   Например когда пользователь удаляет строку из сетки данных, представления, регулярные привязки приведет исключение.

- Это гарантирует, что, когда пользователь выбирает строку, в окне свойств отображаются свойства соответствующего элемента модели, а не строку сетки данных.

  ![DslWpf4](../modeling/media/dslwpf4.png) схему связей между источниками данных и представления.

#### <a name="to-complete-the-bindings-to-the-dsl"></a>Для выполнения привязки к линии DSL

1. Добавьте следующий код в отдельном файле кода в **пользовательского интерфейса** проекта:

    ```csharp
    using System.ComponentModel;
    using Microsoft.VisualStudio.Modeling;
    using Microsoft.VisualStudio.Modeling.Design;

    namespace Company.FarmApp
    {
      partial class FarmControl
      {
        public IContainer Components { get { return components; } }

        /// <summary>Binds the WinForms data source to the DSL model.
        /// </summary>
        /// <param name="nodelRoot">The root element of the model.</param>
        public void DataBind(ModelElement modelRoot)
        {
          WinFormsDataBindingHelper.PreInitializeDataSources(this);
          this.farmBindingSource.DataSource = modelRoot;
          WinFormsDataBindingHelper.InitializeDataSources(this);
        }
      }
    }
    ```

2. В **DslPackage** проекта, изменение **DslPackage\DocView.tt** обновить следующее определение переменной:

    ```csharp
    string viewControlTypeName = "FarmControl";
    ```

## <a name="testing-the-dsl"></a>Тестирование DSL
 В решение DSL теперь можно собрать и запустить "," Несмотря на то, что может потребоваться добавить дополнительные улучшения позже.

#### <a name="to-test-the-dsl"></a>Чтобы проверить DSL

1. Постройте и запустите это решение.

2. В экспериментальном экземпляре Visual Studio, откройте **пример** файл.

3. В **FarmApp Explorer**, откройте контекстное меню на **фермы** корневой узел и выберите **добавить новый Goat**.

     `Goat1` отображается в **животных** представления.

    > [!WARNING]
    > Необходимо использовать контекстное меню на **фермы** узел, не **животных** узла.

4. Выберите **фермы** корневой узел и просмотрите его свойства.

     В представлении формы, измените **имя** или **размер** фермы.

     При переходе от каждого поля в форме, соответствующие изменения свойства в окне «Свойства».

## <a name="enhancing-the-dsl"></a>Улучшение DSL

#### <a name="to-make-the-properties-update-immediately"></a>Чтобы немедленно обновить свойства

1. В режиме конструктора FarmControl.cs выберите простой поля, например имя, размер или IsOrganic.

2. В окне «Свойства» разверните **DataBindings** и откройте **(Дополнительно)**.

     В **форматирование и дополнительная привязка** диалогового окна в разделе **режим обновления источника данных**, выберите **OnPropertyChanged**.

3. Постройте и запустите это решение.

     Убедитесь, что при изменении содержимого поля, соответствующего свойства немедленно изменения модели фермы.

#### <a name="to-provide-add-buttons"></a>Чтобы добавить кнопки

1. В режиме конструктора FarmControl.cs следует используйте панели элементов для создания кнопки на форме.

    Изменить имя и текст кнопки, например для `New Sheep`.

2. Откройте код программной части кнопки (например, дважды щелкнув его).

    Измените его следующим образом:

   ```csharp
   private void NewSheepButton_Click(object sender, EventArgs e)
   {
     using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
     {
       elementOperations.MergeElementGroup(farm,
         new ElementGroup(new Sheep(farm.Partition)));
       t.Commit();
     }
   }

   // The following code is shared with other add buttons:
   private ElementOperations operationsCache = null;
   private ElementOperations elementOperations
   {
     get
     {
       if (operationsCache == null)
       {
         operationsCache = new ElementOperations(farm.Store, farm.Partition);
       }
       return operationsCache;
     }
   }
   private Farm farm
   {
     get { return this.farmBindingSource.DataSource as Farm; }
   }
   ```

    Также необходимо будет вставить следующую директиву:

   ```csharp

   using Microsoft.VisualStudio.Modeling;
   ```

3. Добавьте кнопки аналогично для Goats и полей.

4. Постройте и запустите это решение.

5. Убедитесь, что новая кнопка добавляет элемент. Новый элемент должен появляться в обозревателе FarmApp и в представлении в виде сетки соответствующие данные.

    Вы сможете изменить имя элемента в представлении в виде сетки данных. Можно также удалить его оттуда.

   ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png)

### <a name="about-the-code-to-add-an-element"></a>Сведения о коде, чтобы добавить элемент
 Для новых кнопок элемент следующий альтернативный код немного проще.

```csharp
private void NewSheepButton_Click(object sender, EventArgs e)
{
  using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
  {
    farm.Animals.Add(new Sheep(farm.Partition)); ;
    t.Commit();
  }
}
```

 Тем не менее этот код не задано имя по умолчанию для нового элемента. Она не может быть выполнена любые настраиваемые слияния, которые определены в **директивы слияния элементов** доменного языка, и он не выполняет любой код пользовательское слияние, который был определен.

 Поэтому мы рекомендуем использовать <xref:Microsoft.VisualStudio.Modeling.ElementOperations> для создания новых элементов. Дополнительные сведения см. в разделе [Настройка создания и перемещения элементов](../modeling/customizing-element-creation-and-movement.md).

## <a name="see-also"></a>См. также

- [Определение доменного языка](../modeling/how-to-define-a-domain-specific-language.md)
- [Написание кода для настройки доменного языка](../modeling/writing-code-to-customise-a-domain-specific-language.md)
- [SDK моделирования для Visual Studio — доменные языки](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)