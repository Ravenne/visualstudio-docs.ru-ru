---
title: Пошаговое руководство. Сложная привязка данных в проекте надстройки VSTO
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding [Office development in Visual Studio], Excel
- data [Office development in Visual Studio], binding data
- complex data [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0cb4fc7b43ab3ae48f83f4497fe6fd0042d0c51a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62981637"
---
# <a name="walkthrough-complex-data-binding-in-vsto-add-in-project"></a>Пошаговое руководство. Сложная привязка данных в проекте надстройки VSTO
  В проектах надстроек VSTO можно привязывать данные к элементам управления ведущего приложения и элементам управления Windows Forms. В этом пошаговом руководстве демонстрируется добавление элементов управления на лист Microsoft Office Excel и привязка элементов управления к данным во время выполнения.

 [!INCLUDE[appliesto_xlallapp](../vsto/includes/appliesto-xlallapp-md.md)]

 В данном пошаговом руководстве рассмотрены следующие задачи:

- Добавление <xref:Microsoft.Office.Tools.Excel.ListObject> элемента управления в лист во время выполнения.

- создание объекта <xref:System.Windows.Forms.BindingSource> , соединяющего элемент управления с экземпляром набора данных.

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Предварительные требования
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

- [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] или [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].

- Доступ к запущенному экземпляру SQL Server 2005 или SQL Server 2005 Express с подключенной учебной базой данных `AdventureWorksLT` . Вы можете скачать `AdventureWorksLT` из базы данных [веб-сайте CodePlex](http://go.microsoft.com/fwlink/?LinkId=115611). Дополнительные сведения о подключении базы данных см. в следующих разделах:

    - Присоединение базы данных с помощью SQL Server Management Studio или SQL Server Management Studio Express, см. в разделе [как: Присоединение базы данных (SQL Server Management Studio)](/sql/relational-databases/databases/attach-a-database).

    - Присоединение базы данных с помощью командной строки, см. в разделе [как: Добавить файл базы данных для SQL Server Express](/previous-versions/sql/).

## <a name="create-a-new-project"></a>Создание нового проекта
 Первым шагом является создание проекта надстройки VSTO для Excel.

### <a name="to-create-a-new-project"></a>Создание нового проекта

1. Создайте проект надстройки VSTO для Excel с именем **Заполнение листов из базы данных**в Visual Basic или C#.

     Дополнительные сведения см. в разделе [Как Создание проектов Office в Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).

     В Visual Studio откроется файл `ThisAddIn.vb` или `ThisAddIn.cs` и будет добавлен проект **Заполнение листов из базы данных** в **обозреватель решений**.

## <a name="create-a-data-source"></a>Создание источника данных
 С помощью окна **Источники данных** добавьте типизированный набор данных в свой проект.

### <a name="to-add-a-typed-dataset-to-the-project"></a>Добавление типизированного набора данных в проект

1. Если **источников данных** окно не отображается, откройте его в строке меню выберите **представление** > **Other Windows**  >   **Источники данных**.

2. Выберите команду **Добавить новый источник данных** , чтобы запустить **Мастер настройки источника данных**.

3. Щелкните **База данных**и нажмите кнопку **Далее**.

4. Если подключение к базе данных `AdventureWorksLT` существует, выберите его и нажмите кнопку **Далее**.

    В противном случае нажмите **Создать подключение**и в диалоговом окне **Добавление подключения** создайте новое подключение. Дополнительные сведения см. в разделе [Добавление новых подключений](../data-tools/add-new-connections.md).

5. На странице **Сохранение подключения в файле конфигурации приложения** нажмите кнопку **Далее**.

6. На странице **Выбор объектов базы данных** разверните узел **Таблицы** и выберите таблицу **Address (SalesLT)**.

7. Нажмите кнопку **Готово**.

    *AdventureWorksLTDataSet.xsd* добавляется файл **обозревателе решений**. В этом файле определены следующие элементы:

   - Типизированный набор данных с именем `AdventureWorksLTDataSet`. Этот набор данных представляет содержимое таблицы **Address (SalesLT)** в базе данных AdventureWorksLT.

   - Адаптер таблицы с именем `AddressTableAdapter`. Этот адаптер таблицы можно использовать для чтения и записи данных `AdventureWorksLTDataSet`. Дополнительные сведения см. в разделе [TableAdapter overview](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).

     Далее в пошаговом руководстве используются оба эти объекта.

## <a name="create-controls-and-bind-controls-to-data"></a>Создание элементов управления и привязка элементов управления к данным
 В этом пошаговом руководстве элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> отображает все выбранные данные из таблицы сразу после того, как пользователь открывает книгу. Объект списка использует <xref:System.Windows.Forms.BindingSource> для подключения элемента управления к базе данных.

 Дополнительные сведения о привязке элементов управления к данным см. в разделе [привязки данных к элементам управления в решениях Office](../vsto/binding-data-to-controls-in-office-solutions.md).

### <a name="to-add-the-list-object-dataset-and-table-adapter"></a>Добавление объекта списка, набора данных и адаптера таблиц

1. В классе `ThisAddIn` объявите приведенные ниже элементы управления для отображения таблицы `Address` из набора данных `AdventureWorksLTDataSet` .

     [!code-csharp[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#1)]

2. В метод `ThisAddIn_Startup` добавьте приведенный ниже код для инициализации набора данных и его заполнения сведениями из набора данных `AdventureWorksLTDataSet` .

     [!code-csharp[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#2)]
     [!code-vb[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#2)]

3. Добавьте следующий код в метод `ThisAddIn_Startup` . Этот код создает ведущий элемент, расширяющий лист. Дополнительные сведения см. в разделе [документов расширения Word и книг Excel в надстройках VSTO во время выполнения](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

     [!code-csharp[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#3)]
     [!code-vb[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#3)]

4. Создайте диапазон и добавьте элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> .

     [!code-csharp[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#4)]
     [!code-vb[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#4)]

5. Свяжите объект списка с `AdventureWorksLTDataSet` , используя объект <xref:System.Windows.Forms.BindingSource>. Передайте имена столбцов, которые следует привязать к объекту списка.

     [!code-csharp[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#5)]
     [!code-vb[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#5)]

## <a name="test-the-add-in"></a>Тестирование надстройки
 После запуска Excel элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> отображает данные из таблицы `Address` набора данных `AdventureWorksLTDataSet` .

### <a name="to-test-the-vsto-add-in"></a>Тестирование надстройки VSTO

- Нажмите клавишу **F5**.

     Элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> с именем `addressListObject` создается на листе. Одновременно в проект добавляется объект набора данных `adventureWorksLTDataSet` и объект <xref:System.Windows.Forms.BindingSource> с именем `addressBindingSource` . Объект <xref:Microsoft.Office.Tools.Excel.ListObject> привязан к объекту <xref:System.Windows.Forms.BindingSource>, который в свою очередь привязан к объекту набора данных.

## <a name="see-also"></a>См. также

- [Данные в решениях Office](../vsto/data-in-office-solutions.md)
- [Привязка данных к элементам управления в решениях Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Практическое руководство. Заполнение листов данными из базы данных](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)
- [Практическое руководство. Заполнение документов данными из базы данных](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [Практическое руководство. Заполнение документов данными из служб](../vsto/how-to-populate-documents-with-data-from-services.md)
- [Практическое руководство. Заполнение документов данными из объектов](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [Практическое руководство. Прокрутить записи базы данных на листе](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)
- [Практическое руководство. Обновить источник данных с данными из элемента управления ведущего приложения](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Пошаговое руководство: Простая привязка данных в проекте уровня документа](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)
- [Пошаговое руководство: Сложная привязка данных в проекте уровня документа](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)
- [Использовать файлы локальной базы данных в общие сведения о решений Office](../vsto/using-local-database-files-in-office-solutions-overview.md)
- [Добавление новых источников данных](../data-tools/add-new-data-sources.md)
- [Привязка элементов управления Windows Forms к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Использовать файлы локальной базы данных в общие сведения о решений Office](../vsto/using-local-database-files-in-office-solutions-overview.md)
- [Общие сведения о компоненте BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview)