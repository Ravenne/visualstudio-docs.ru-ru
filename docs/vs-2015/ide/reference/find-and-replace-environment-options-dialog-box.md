---
title: Страница "Поиск и замена", папка "Среда", диалоговое окно "Параметры" | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.FindReplace
- VS.ToolsOptionsPages.Environment.FindandReplace
helpviewer_keywords:
- Find and Replace, Options dialog box
- Find and Replace, customizing
ms.assetid: f804d6d5-6309-46e4-8294-b83e880b5ec9
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 305a19ed08c58d6858c95a3f1109cdf4877d848f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63437170"
---
# <a name="find-and-replace-environment-options-dialog-box"></a>"Поиск и замена", "Среда", диалоговое окно "Параметры"
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Используйте эту страницу диалогового окна **Параметры** для управления текстовыми полями сообщений и другими аспектами операций поиска и замены. Перейти к этому диалоговому окну можно из меню **Сервис**, щелкнув **Параметры**, развернув узел **Среда** и выбрав пункт **Поиск и замена**. Если эта страница отсутствует в списке, выберите **Показать все параметры** в диалоговом окне **Параметры**.  
  
> [!NOTE]
> Доступные в диалоговых окнах параметры, а также названия и расположение команд меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Отображать информационные сообщения**  
 Выберите этот параметр, чтобы отображать все информационные сообщения функции поиска и замены с параметром **Всегда показывать это сообщение**. Например, если вы отключили вывод сообщения "Поиск достиг отправной точки", при выборе этого параметра это информационное сообщение снова будет появляться при использовании функции поиска и замены.  
  
 Если вы не хотите, чтобы на экран выводились какие-либо информационные сообщения функции поиска и замены, снимите этот флажок.  
  
 Если вы сняли флажок **Всегда показывать это сообщение** для некоторых, но не для всех информационных сообщений функции **Поиск и замена**, флажок **Отображать информационные сообщения** будет отображаться как заполненный, но не установленный. Чтобы восстановить все необязательные сообщения **поиска и замены**, снимите этот флажок, а затем установите его снова.  
  
> [!NOTE]
> Этот параметр не влияет на информационные сообщения функции **поиска и замены**, для которых не предусмотрен параметр **Всегда показывать это сообщение**.  
  
 **Отображать предупреждающие сообщения**  
 Выберите этот параметр, чтобы отображать все предупреждающие сообщения функции поиска и замены с параметром **Всегда показывать это сообщение**. Например, если отключили вывод предупреждения **Заменить все**, появляющееся при попытке замены в файлах, которые не открыты для редактирования, при выборе этого параметра это предупреждающее сообщение снова будет появляться при попытке применить эту функцию.  
  
 Если вы не хотите, чтобы на экран выводились какие-либо предупреждающие сообщения функции поиска и замены, снимите этот флажок.  
  
 Если вы сняли флажок **Всегда показывать это сообщение** для некоторых, но не для всех предупреждающих сообщений функции **Поиск и замена**, флажок **Отображать предупреждающие сообщения** будет отображаться как заполненный, но не установленный. Чтобы восстановить все необязательные сообщения **поиска и замены**, снимите этот флажок, а затем установите его снова.  
  
> [!NOTE]
> Этот параметр не влияет на предупреждающие сообщения функции **поиска и замены**, для которых не предусмотрен параметр **Всегда показывать это сообщение**.  
  
 **Автоматически заполнять поле "Найти" текстом из редактора**  
 Выберите этот параметр, чтобы вставлять текст с любой стороны от текущей точки вставки редактора в поле **Образец** при выборе любого представления окна **Поиск и замена** в меню **Правка**. Снимите этот флажок, чтобы использовать последний шаблон поиска из предыдущего поиска в качестве строки **Образец**.  
  
## <a name="see-also"></a>См. также раздел  
 [Поиск и замена текста](../../ide/finding-and-replacing-text.md)
