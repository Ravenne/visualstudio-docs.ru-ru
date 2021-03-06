---
title: Создание решений рабочих процессов SharePoint | Документация Майкрософт
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VSTO.NewSharePointWorkflowWizard.Page3
- VS.SharePointTools.Workflow.WorkflowName
- VSTO.NewSharePointWorkflowWizard.Page2
- VSTO.NewSharePointWorkflowWizard.Page1
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d78d82a51f88bfaf076b56692629e801689e103e
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443526"
---
# <a name="create-sharepoint-workflow-solutions"></a>Создание решений рабочих процессов SharePoint

[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] предоставляет средства для создания настраиваемых рабочих процессов, которые управляют жизненным циклом документов и элементов списка в SharePoint веб-сайта. Предоставляется конструктор, набор элементов управления действием и ссылки на необходимые сборки. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] также включает в себя **мастер настройки SharePoint**, чтобы упростить создание и настройка рабочих процессов.

Дополнительные сведения о SharePoint, см. в разделе [Microsoft продуктов и технологий SharePoint](http://go.microsoft.com/fwlink/?LinkId=178470).

## <a name="workflows-in-sharepoint"></a>Рабочие процессы в SharePoint
 При добавлении рабочего процесса в библиотеку SharePoint или список, можно принудительно применить бизнес-процесс для всех элементов в библиотеке или списке. Рабочий процесс описывает действия, которые система или пользователь должен выполнять для каждого элемента, например, отправку элемента можно редактировать и затем проверить. Эти действия, известные как *действия*, являются стандартными блоками рабочего процесса.

 Можно создать рабочие процессы SharePoint в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] и развертывать их на сайт SharePoint. После развертывания рабочего процесса в SharePoint, связывается с библиотекой или списком. Он затем запускается автоматически, с помощью процесса, или вручную пользователем. Дополнительные сведения об операции рабочего процесса, см. в разделе [рабочих процессов для разработки SharePoint с помощью Visual Studio](https://docs.microsoft.com/sharepoint/dev/general-development/develop-sharepoint-workflows-using-visual-studio).

## <a name="create-custom-sharepoint-workflows"></a>Создание настраиваемых рабочих процессов SharePoint
 Два проекта рабочих процессов SharePoint доступны вам в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]: **Последовательный рабочий процесс** и **состояния рабочего процесса конечного автомата**.

 Объект *последовательный рабочий процесс* представляет ряд шагов. Действия выполняются друг за другом, пока завершится последнее действие. Последовательные рабочие процессы всегда являются строго последовательны в своем выполнении. Поскольку они могут получать внешние сигналы и включать параллельные логические ветки, точный порядок выполнения может отличаться. Ниже показан пример последовательного рабочего процесса.

 ![Последовательный рабочий процесс](../sharepoint/media/sp-sequential.png "последовательного рабочего процесса")

 Объект *конечного автомата* представляет набор состояний, переходов и действий. Действия, описанные в конечного автомата выполняются асинхронно. Это означает, что они не обязательно выполняются один за другим, но вместо инициируются действия и состояния. Одно состояние задается как начальное состояние, а затем на основе события, переходе в другое состояние. Конечный автомат может иметь конечное состояние, которое определяет конец рабочего процесса. В примере ниже показан пример конечного автомата.

 ![Состояние рабочего процесса конечного автомата](../sharepoint/media/sp-state.png "состояния рабочего процесса конечного автомата")

 Дополнительные сведения о типах рабочих процессов см. в разделе [типы рабочих процессов](http://go.microsoft.com/fwlink/?LinkId=178995).

### <a name="use-the-wizard"></a>С помощью мастера
 При создании проекта рабочего процесса SharePoint в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], сначала необходимо указать его параметры в **мастер настройки SharePoint**. Мастер использует эти параметры для создания проекта в **обозревателе решений**. Этот проект содержит файл кода, несколько файлов, которые используются для развертывания рабочего процесса, и ссылки на сборки, необходимые для создания настраиваемого рабочего процесса SharePoint.

 После создания рабочего процесса, можно изменить его свойства в окне «Свойства». Несмотря на то, что многие свойства можно изменить непосредственно в окне свойств, некоторые потребуется нажать кнопку с многоточием (![эллипс конструктора ASP.NET Mobile](../sharepoint/media/mwellipsis.gif "эллипс конструктора ASP.NET Mobile")) для Измените их значения. Эта кнопка перезапускает **мастер настройки SharePoint**. После внесения значения свойств, выберите **Готово** кнопку, чтобы подтвердить их.

> [!NOTE]
> **Типа рабочего процесса** свойство только для чтения и не может быть изменено. Если вы хотите изменить тип рабочего процесса, необходимо создать другой рабочий процесс.

## <a name="design-a-sharepoint-workflow"></a>Разработать рабочий процесс SharePoint
 Определив все действия бизнес-процесса, используйте [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] конструктора рабочих процессов для разработки рабочего процесса SharePoint. Чтобы открыть конструктор, дважды щелкните Workflow1.cs или Workflow1.vb в **обозревателе решений**, или откройте контекстное меню для любого из этих файлов и выберите пункт **откройте**.

### <a name="activities"></a>Действия
 Чтобы разработать рабочий процесс, добавьте действия из **элементов** для *расписания рабочего процесса* в конструкторе. Расписания рабочего процесса содержит последовательность действий, в том порядке, что они должны выполняться.

 Существует два типа действий:

- *Простые действия* выполняют одну единицу работы, такие как «задержаться на один день» или «запуск веб-службы».

- *Составные действия* содержать другие действия; например, условное действие может содержать две ветви.

  Оба типа действий доступны в **элементов**.

  Действия могут иметь свойства, методы и события. Используйте **свойства** окно для задания свойств действия.

  Также можно создать настраиваемое действие. Дополнительные сведения см. в разделе [Пошаговое руководство: Создание пользовательского рабочего процесса действия сайта](../sharepoint/walkthrough-create-a-custom-site-workflow-activity.md).

  Стандартные действия сгруппированы в следующие вкладки в **элементов**:

- **Рабочий процесс SharePoint**

- **Windows Workflow v3.0**

- **Рабочий процесс Windows версии 3.5**

  SharePoint поддерживает не все базовые операции рабочего процесса. Дополнительные сведения см. в разделе [рабочих процессов для Windows SharePoint Services Общие сведения о действиях](http://go.microsoft.com/fwlink/?LinkID=156094).

#### <a name="sharepoint-workflow-activities"></a>Действия рабочих процессов SharePoint
 **Рабочего процесса SharePoint** содержатся специальные действия для использования в [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]. Эти действия упростить и оптимизировать разработку рабочих процессов жизненного цикла документа. Дополнительные сведения о действиях, перечисленных в **рабочего процесса SharePoint** вкладке, см. в разделе [рабочих процессов для Windows SharePoint Services Общие сведения о действиях](http://go.microsoft.com/fwlink/?LinkID=156094).

#### <a name="windows-workflow-activities"></a>Действия рабочих процессов Windows
 **Рабочего процесса Windows** содержатся действия, предоставляемые [!INCLUDE[TLA#tla_workflow](../sharepoint/includes/tlasharptla-workflow-md.md)]. Эти действия можно использовать для создания расписаний рабочих процессов для любых приложений рабочего процесса Windows.

 Дополнительные сведения о действиях, перечисленных в **рабочих процессов Windows** вкладке, см. в разделе [действия Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=156096). Дополнительные сведения о Windows Workflow Foundation, см. в разделе [Обзор Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=128632).

### <a name="work-with-activities-in-the-designer"></a>Работать с действиями в конструкторе
 Расписания рабочего процесса может содержать сочетание действий рабочего процесса Windows и действий рабочих процессов SharePoint.

 Конструктор отображает визуальные подсказки, помогающие расположить и правильно настроить действия. При перетаскивании или копировании действия из расписания рабочего процесса конструктор показывает зеленые значки плюс (+), которые показывают верные расположения для этого действия в рабочем процессе. Не удается разместить действие в расположении, где не было бы допустимым. Например нельзя поместить действие Send в качестве первого действия в ветви действия Listen. Дополнительные сведения см. в разделе [центр разработки SharePoint Designer](http://go.microsoft.com/fwlink/?LinkId=178476).

## <a name="collect-information-during-the-workflow"></a>Сбор сведений во время рабочего процесса
 Вы можете получать информацию от пользователей в заранее в рабочем процессе. С помощью форм или свойств элементов можно собирать сведения.

### <a name="forms"></a>Формы
 Формы — это диалоговые окна, которые содержат вопросы и обеспечивают для пользователей для предоставления ответов.

 Существует четыре типа форм, которые могут использоваться в рабочем процессе.

- Ассоциация

- Запуска

- Изменение

- Задача

  Из этих функций [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] имеются шаблоны элементов для формы ассоциации и инициации. Пример *форма сопоставления* один администратор установки рабочего процесса в этом случае введите параметры, связанные с рабочим процессом, например, предельная сумма для рабочего процесса о расходах. Пример *форму инициации* , которое позволяет пользователю рабочего процесса о расходах ввести сумму в рабочий процесс. Дополнительные сведения об этих типах форм см. в разделе [SharePoint проект и проект шаблоны элементов](../sharepoint/sharepoint-project-and-project-item-templates.md).

### <a name="item-properties"></a>Свойства элемента
 Можно также собирать сведения от пользователей с помощью свойств элемента в библиотеке SharePoint или списке. Основной файл кода (Workflow1.cs или Workflow1.vb) объявляет экземпляр с именем класса Microsoft.SharePoint.Workflow.SPWorkflowActivationProperties.WorkflowProperties `workflowProperties`. Используйте `workflowProperties` объекта для доступа к свойствам библиотеки или списка в коде. Пример см. в разделе [Пошаговое руководство. Создание и отладка решения рабочих процессов SharePoint](../sharepoint/walkthrough-creating-and-debugging-a-sharepoint-workflow-solution.md).

## <a name="debug-a-sharepoint-workflow-template"></a>Отладка рабочих процессов SharePoint
 Вы отладка проекта рабочего процесса SharePoint выполняется аналогично отладке других [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] веб-проектов. При запуске [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] отладчик, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] использует параметры, указываемые в **мастер настройки SharePoint** для открытия соответствующего веб-сайт SharePoint и автоматическое связывание шаблона рабочего процесса с помощью соответствующую библиотеку или список. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Кроме того, присоединяет [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] отладчик [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] процесс так называемого *w3wp.exe*.

 Чтобы протестировать рабочий процесс, необходимо запустить ее вручную. Дополнительные сведения см. раздел «Отладка рабочих процессах» в [отладка решений SharePoint](../sharepoint/debugging-sharepoint-solutions.md). Дополнительные сведения о [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] отладке веб-приложений, см. в разделе [отладка веб-приложений](../debugger/how-to-enable-debugging-for-aspnet-applications.md).

## <a name="deploy-a-sharepoint-workflow-template"></a>Развертывание шаблона рабочего процесса SharePoint
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Развертывание проектов рабочих процессов SharePoint так же, как и другие [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] проектов SharePoint. Дополнительные сведения см. в разделе [пакета и развертывание SharePoint решения](../sharepoint/packaging-and-deploying-sharepoint-solutions.md).

## <a name="import-globally-reusable-workflows"></a>Импортировать глобальные рабочие процессы
 В дополнение к созданию отдельных сайтов многократно используемых рабочих процессов, SharePoint Designer позволяет создавать *глобальные рабочие процессы*, которые являются рабочие процессы, которые могут быть использованы на любом сайте SharePoint. Проект Импорт повторно используемого рабочего процесса в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] в настоящее время не импортирует глобальные рабочие процессы. Тем не менее можно использовать SharePoint Designer для преобразования глобального рабочего процесса в повторно используемый рабочий процесс, или Импорт рабочего процесса в качестве непреобразованных декларативного рабочего процесса. Дополнительные сведения см. в разделе [Импорт элементов из существующего сайта SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md).

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Пошаговое руководство: Создание и отладка решения рабочих процессов SharePoint](../sharepoint/walkthrough-creating-and-debugging-a-sharepoint-workflow-solution.md)|Пошаговые инструкции по созданию и отладке простого [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] рабочего процесса.|
|[Пошаговое руководство: Создание рабочего процесса с формами связывания и запуска](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)|Шаг за шагом приводит к созданию более полнофункциональное [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] рабочего процесса с формами связывания и запуска.|
|[Пошаговое руководство: Добавление страницы приложения в рабочий процесс](../sharepoint/walkthrough-add-an-application-page-to-a-workflow.md)|Основана на разделе [Пошаговое руководство: Создание рабочего процесса с формами связывания и запуска](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) , добавив дополнительный *.aspx* страницу приложения, которая сообщает о данных, указанные в рабочем процессе.|
|[Пошаговое руководство: Создание пользовательского рабочего процесса действия сайта](../sharepoint/walkthrough-create-a-custom-site-workflow-activity.md)|Демонстрирует, как выполнять две основные задачи: Создание рабочего процесса уровня веб-сайта и Создание настраиваемого рабочего процесса действия.|
|[Пошаговое руководство: Импорт рабочего процесса для повторного использования SharePoint Designer в Visual Studio](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)|Демонстрирует импорт многократно используемых декларативные рабочие процессы, созданные в SharePoint Designer 2010 в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] проекта SharePoint.|

## <a name="see-also"></a>См. также

- [Разработка решений SharePoint](../sharepoint/developing-sharepoint-solutions.md)
- [Сборка и отладка решений SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)
- [Создание страниц приложений для SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)