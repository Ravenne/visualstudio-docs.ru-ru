---
title: Практическое руководство. Обновление расширения Visual Studio | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- update package
- update extension
- new package version
ms.assetid: 93f79774-7b79-4dd6-94ad-13698f72c257
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4eb438db5fd911ed93f7072902281815633d06a7
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63415447"
---
# <a name="how-to-update-a-visual-studio-extension"></a>Практическое руководство. Обновление расширения Visual Studio
Расширение Visual Studio на компьютере можно обновить с помощью **расширения и обновления** для установки новой версии. Если вы создаете обновленную версию расширения, можно обозначить ее как обновленную, увеличив номер версии в манифесте VSIX.

 Обновления устанавливаются в том случае, когда манифест VSIX входящих расширения имеет такое же `ID` установленной версией и использовать дополнительные услуги `Version` номер. Если `Version` значения совпадают, или ниже, пакет не может быть установлен. Если `ID` значения не совпадают, пакет, который еще не установили распознается как отдельное расширение.

 Для предотвращения конфликтов во время разработки, мы рекомендуем, что вы удаления предыдущих версий расширений и также удалить или отключить потенциально конфликтующие расширения.

## <a name="to-update-an-extension-on-your-system"></a>Обновление расширения в системе

1. В меню **Сервис** выберите пункт **Расширения и обновления**.

2. В левой области щелкните **обновления**.

3. В средней области выберите обновление, которое вы хотите установить.

     Номер версии обновленного расширения отображается в правой области вместе с другими данными.

4. В нижней части правой панели, щелкните **обновления**.

## <a name="to-publish-an-update-of-an-extension"></a>Публикация обновления расширения

1. В Visual Studio откройте решение для расширения, который вы хотите обновить. Внесите изменения.

    > [!IMPORTANT]
    > Значение без знака, все пользовательские расширения не обновляются автоматически. Всегда необходимо подписывать свои расширения.

2. В **обозревателе решений**откройте *: source.extension.manifest*.

3. В конструкторе манифеста, увеличьте значение числа в **версии** поля.

4. Сохраните решение и постройте его.

5. Передать новый *.vsix* файла (в * \bin\Debug\* папку проекта) для [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) веб-сайта.

     При открытии пользователь, имеющий более ранней версии расширения **расширения и обновления**, новая версия будет отображаться в **обновления** список, в условии, что средство автоматически искать обновления.

     Можно включить или отключить автоматическая проверка наличия обновлений в нижней части **обновления** области (**включить или отключить автоматическое обнаружение доступных обновлений**), какие изменения **поиск обновления** в **средства** > **параметры** > **среды**  >  **Расширения и обновления**.

    > [!NOTE]
    > Начиная с Visual Studio 2015 с обновлением 2, можно указать (в **средства** > **параметры** > **среды**  >  **Расширения и обновления**) необходимость автоматических обновлений для расширения на уровне пользователя, все расширения пользователя или другое (значение по умолчанию).

## <a name="see-also"></a>См. также
- [Составляющие пакета VSIX](../extensibility/anatomy-of-a-vsix-package.md)
- [Поиск и использование расширений Visual Studio](../ide/finding-and-using-visual-studio-extensions.md)