---
title: Практическое руководство. Очистить стек отмены | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1d6e7c2536b7c5556139ce7a9b56756e20fd3648
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62911925"
---
# <a name="how-to-clear-the-undo-stack"></a>Практическое руководство. Очистить стек отмены
Следующую процедуру ниже объясняется, как очистить стек отмены.

## <a name="to-clear-the-undo-stack"></a>Чтобы очистить стек отмены

1. Снимите флажок использовать стек отмены [IOleUndoManager::DiscardFrom](/windows/desktop/api/ocidl/nf-ocidl-ioleundomanager-discardfrom) метод. Ниже приведен пример этого:

    ```
    HRESULT CCmdWindow::ClearUndoStack()
    {
      HRESULT hr = S_OK;

      if (m_pUndoMgr == NULL)
        {
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));
        ASSERT(m_pUndoMgr != NULL, "",;);
        }

      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));

    Error:
      return hr;
    }
    ```

## <a name="see-also"></a>См. также
- [Практическое руководство. Реализуйте механизмы управления отменой](../extensibility/how-to-implement-undo-management.md)