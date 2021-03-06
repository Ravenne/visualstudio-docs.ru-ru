---
title: Отладка элемента управления ActiveX с привязкой к данным | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data-bound controls, ActiveX
- ActiveX controls, debugging
- controls [Visual Studio], ActiveX
ms.assetid: 9f6e1f00-e25b-48a9-8484-7e67a1232461
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b5b3d5a58c87988c950328a8b0136986b3a149f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62852421"
---
# <a name="debugging-a-data-bound-activex-control"></a>Отладка элемента управления ActiveX с привязкой данных
При разработке элемента управления ActiveX, который будет привязан к элементу управления источником данных, можно создавать собственное приложение контейнера и использовать этот контейнер в сеансе отладки.

 Например, создайте диалоговое приложение MFC и поместите элемент управления источником данных и свой элемент управления с привязкой данных в диалоговом окне. Это MFC-приложение можно будет использовать для тестирования во время выполнения и в качестве исполняемого контейнера для отладки элемента управления ActiveX с привязкой данных.

## <a name="using-the-test-container"></a>Использование тестового контейнера
 Если нужен контейнер, который можно легко изменять для поддержки различных интерфейсов элемента управления или контейнера, используйте тестовый контейнер элемента управления ActiveX в качестве исполняемого во время сеанса отладки. В тестовом контейнере элемента управления ActiveX выберите **Параметры** из меню **Контейнер** для включения различных интерфейсов. Дополнительные сведения см. в разделе [тестирование свойств и событий с использованием тестового контейнера](/cpp/mfc/testing-properties-and-events-with-test-container).

 В случае необходимости захода в код контейнера во время отладки используйте отладочную версию контейнера или используйте отладочную версию тестового контейнера элемента управления ActiveX. Дополнительные сведения см. в разделе [TSTCON образца: Тестовый контейнер элементов управления ActiveX](https://msdn.microsoft.com/library/72fa40ef-27d3-400c-813f-10b03236e600).

## <a name="see-also"></a>См. также
- [Отладка COM и ActiveX](../debugger/com-and-activex-debugging.md)
- [Элементы управления ActiveX](/cpp/mfc/activex-controls)