---
title: Цветовая маркировка синтаксиса в языковой службе прежних версий | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- syntax coloring
- language services, syntax coloring
ms.assetid: f65ff67e-8c20-497a-bebf-5e2a5b5b012f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c3b1e96a850cfde1af6ad3aac2df4310a3875f49
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63429966"
---
# <a name="syntax-coloring-in-a-legacy-language-service"></a>Цветовая маркировка синтаксиса в языковой службе прежних версий

Visual Studio использует службу выделение цветом для определения элементов языка и вывода их указанными цветами в редакторе.

## <a name="colorizer-model"></a>Модель палитры
 Служба реализует языка <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> интерфейс, который затем используется редакторами. Эта реализация представляет собой отдельный объект в службе языка, как показано на следующем рисунке:

 ![График SVC Colorizer](../../extensibility/internals/media/figlgsvccolorizer.gif)

> [!NOTE]
> Синтаксических конструкций службы отличается от общего механизма Visual Studio для выделения текста цветом. Дополнительные сведения об общей [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] механизм поддержки выделения цветом, см. в разделе [использование шрифтов и цветов](../../extensibility/using-fonts-and-colors.md).

 Помимо палитры языковая служба может предоставлять пользовательских цветных элементов, используемые редактором, рекламы, что он передает пользовательских цветных элементов. Это можно сделать, реализовав <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> тот же объект, реализующий интерфейс <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> интерфейс. Возвращает количество пользовательских цветных элементов, когда вызывает редактор <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> метод и он возвращает отдельные настраиваемого цветного элемента, когда вызывает редактор <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> метод.

 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> Метод возвращает объект, реализующий <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> интерфейс. Если служба языка поддерживает значения цвета 24-разрядный или высокого уровня, он должен реализовать <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> интерфейса на один и тот же объект как <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> интерфейс.

## <a name="how-a-vspackage-uses-a-language-service-colorizer"></a>Как VSPackage использует палитру языковой службы

1. Пакет VSPackage должен получить службу языка, которая требуется служба языка VSPackage осуществлять следующее:

    1. Использовать объект, реализующий интерфейс <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> интерфейс для получения текста для выделения цветом.

         Текст обычно отображается с использованием объекта, реализующего <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> интерфейс.

    2. Языковая служба получите путем запроса поставщика услуг пакета VSPackage для GUID языковой службы. Языковые службы определяются в реестре по расширению файла.

    3. Связать службы языка с <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> путем вызова его <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> метод.

2. VSPackage теперь можно получить и использовать объект палитры следующим образом:

    > [!NOTE]
    > Пакеты VSPackage, использующих базовый редактор не нужно явным образом получить объекты палитры службы языка. Как только экземпляр базового редактора Получает службу языка, он выполняет все задачи Раскраска, показано ниже.

    1. Получить объект палитру языковой службы, который реализует <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>, и <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> интерфейсы, путем вызова <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> метод на языковой службе <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> объекта.

    2. Вызовите <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> метод для получения сведений палитры для определенного диапазона текста.

         <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> Возвращает массив значений, по одному для каждого символа в диапазон текста выделение цветом. Значения — это индексы в списке цветного элемента по умолчанию, поддерживаемом базовым редактором или настраиваемого цветного элемента списка, поддерживаемых службой языка, сам список цветного элемента.

    3. Использовать цветовое выделение сведения, возвращаемые функцией <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> метод для отображения выделенного текста.

> [!NOTE]
> Помимо использования палитру языковой службы, пакет VSPackage можно также использовать универсальный механизм цветовой подсветки текста Visual Studio. Дополнительные сведения о механизме см. в разделе [использование шрифтов и цветов](../../extensibility/using-fonts-and-colors.md).

## <a name="in-this-section"></a>В этом разделе
- [Реализация цветовой маркировки синтаксиса](../../extensibility/internals/implementing-syntax-coloring.md)

 Описывает, как редактор получает доступ к языковой службы выделения синтаксиса цветом и его языковой службы необходимо реализовать поддержку синтаксиса выделение цветом.

- [Практическое руководство. Использование встроенных цветных элементов](../../extensibility/internals/how-to-use-built-in-colorable-items.md)

 В этой статье демонстрируется использование встроенных цветных элементов от языковой службы.

- [Настраиваемые цветные элементы](../../extensibility/internals/custom-colorable-items.md)

 В этой статье описывается использование пользовательских цветных элементов.

## <a name="see-also"></a>См. также

- [Использование шрифтов и цветов](../../extensibility/using-fonts-and-colors.md)