---
title: Создание пользовательских представлений данных в отладчике | Документация Майкрософт
ms.date: 01/09/2019
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], inspecting programs
- debugger, viewing data
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 32b3fddd13bd16ac2c846f02f54596ec846374b9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62929995"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger-c-visual-basic-c"></a>Создание пользовательских представлений данных в отладчике Visual Studio (C#, Visual Basic, C++)

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Отладчик предоставляет множество средств для проверки и изменения состояния программы. Большинство этих средств функционируют только в режиме приостановки.

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>Создание пользовательских представлений данных в окнах переменных и подсказки по данным

 Многие из [окна отладчика](../debugger/debugger-windows.md), такие как **"Видимые"** и **Watch** windows, позволяют проверять значения переменных. Можно настроить как C++ типов управляемых объектов и собственных типов отображаются в окнах переменных отладчика, а также в [подсказок по данным](../debugger/view-data-values-in-data-tips-in-the-code-editor.md). Дополнительные сведения см. в разделе [Создание пользовательских представлений C++ объектов](../debugger/create-custom-views-of-native-objects.md) и [Создание настраиваемых представлений объектов](../debugger/create-custom-views-of-dot-managed-objects.md).

## <a name="create-custom-visualizers"></a>Создание настраиваемых визуализаторов

 Визуализаторы позволяют просмотреть содержимое объекта или переменной более удобным образом. В отладчике Visual Studio визуализатор ссылается на разных окнах, которые можно открыть с помощью увеличительное стекло ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "значок визуализатор") значок. Например HTML-визуализатор показывает, как строка HTML будет интерпретируются и отображаются в браузере. Можно получить доступ к визуализаторам из подсказок, **Watch** окне **"Видимые"** окно и **"Локальные"** окна. **"Быстрая проверка"** диалоговое окно также предоставляет визуализатора. Дополнительные сведения см. в статье [Создание настраиваемых визуализаторов](../debugger/create-custom-visualizers-of-data.md).

## <a name="see-also"></a>См. также

- [Первое знакомство с отладчиком](../debugger/debugger-feature-tour.md)
- [Командное окно](../ide/reference/command-window.md)
- [Безопасность отладчика](../debugger/debugger-security.md)