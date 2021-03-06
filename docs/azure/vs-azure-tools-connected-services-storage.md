---
title: Добавление службы хранилища Azure с помощью подключенных служб | Документация Майкрософт
description: Добавление хранилища Azure в приложение с помощью диалогового окна "Добавление подключенных служб" в Visual Studio
author: ghogen
manager: jillfra
assetId: 521ec044-ad4b-4828-8864-01decde2e758
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/26/2017
ms.author: ghogen
ms.openlocfilehash: 649f99911726e562f9602fe6697591ec6cfb96eb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62561029"
---
# <a name="adding-azure-storage-by-using-visual-studio-connected-services"></a>Добавление хранилища Azure с использованием подключенных служб Visual Studio

В Visual Studio с помощью диалогового окна **Add Connected Services** (Добавление подключенных служб) можно подключить любое из следующих хранилищ Azure:

- облачную службу C#;
- серверную мобильную службу .NET;
- веб-сайт или службу ASP.NET;
- службу ASP.NET Core;
- службу веб-заданий Azure.

Подключенные службы добавляют необходимые ссылки и код подключения в проект и вносят соответствующие изменения в файлы конфигурации.

По завершении в диалоговом окне **Add Connected Services** (Добавление подключенных служб) автоматически отображается документация с подробным описанием действий, необходимых для начала работы с хранилищем BLOB-объектов, очередями и таблицами.

> [!NOTE]
> Этот раздел относится к Visual Studio в Windows. Информацию о Visual Studio для Mac см. в статье [Подключенные службы в Visual Studio для Mac](/visualstudio/mac/connected-services).

## <a name="connect-to-azure-storage-using-the-connected-services-dialog"></a>Подключение к хранилищу Azure с помощью диалогового окна подключенных служб

1. Откройте проект в Visual Studio.

1. В **обозревателе решений** щелкните правой кнопкой мыши узел **Подключенные службы** и выберите в контекстном меню пункт **Добавить подключенную службу**.

    ![Добавление подключенной службы Azure](./media/vs-azure-tools-connected-services-storage/IC796702.png)

1. На странице **Подключенные службы** выберите элемент **Облачное хранилище в службе хранения Azure**.

    ![Добавление учетной записи хранения Azure](./media/vs-azure-tools-connected-services-storage/add-azure-storage.png)

1. В диалоговом окне **Служба хранилища Azure** выберите существующую учетную запись хранения и нажмите кнопку **Добавить**.

    Если вам нужно создать учетную запись хранения, перейдите к следующему шагу. В противном случае перейдите к шагу 6.

    ![Добавление существующей учетной записи хранения в проект](./media/vs-azure-tools-connected-services-storage/select-azure-storage-account.png)

1. Чтобы создать учетную запись хранения, сделайте следующее:

   1. Щелкните **Создание новой учетной записи хранения** в нижней части диалогового окна.

   1. Заполните поля в диалоговом окне **Создание учетной записи хранения** и нажмите кнопку **Создать**.

       ![Новая учетная запись хранения Azure](./media/vs-azure-tools-connected-services-storage/create-storage-account.png)

   1. Когда отобразится диалоговое окно **Служба хранилища Azure**, новая учетная запись хранения появится в списке. Выберите в списке новую учетную запись хранения и нажмите кнопку **Добавить**.

1. Подключенная служба хранилища появится в узле **Веб-ссылки** проекта.

## <a name="how-your-project-is-modified"></a>Какие изменения произойдут в проекте

Когда вы закроете диалоговое окно, Visual Studio добавит ссылки и внесет изменения в определенные файлы конфигурации. Конкретные изменения зависят от типа проекта.

- Проекты ASP.NET: ознакомьтесь со статьей [Приступая к работе с хранилищем BLOB-объектов Azure и подключенными службами Visual Studio (ASP.NET)](http://go.microsoft.com/fwlink/p/?LinkId=513126).
- Проекты ASP.NET Core: ознакомьтесь со статьей [Начало работы с хранилищем больших двоичных объектов Azure и подключенными службами Visual Studio (ASP.NET 5)](http://go.microsoft.com/fwlink/p/?LinkId=513124).
- Проекты облачной службы (веб-роли и рабочие роли): ознакомьтесь со статьей [Начало работы с хранилищем больших двоичных объектов Azure и подключенными службами Visual Studio (проектами облачных служб)](http://go.microsoft.com/fwlink/p/?LinkId=516965).
- Проекты веб-заданий: ознакомьтесь со статьей [Что произошло с моим проектом веб-заданий (подключенными к службе хранилища Azure службами Visual Studio)?](/azure/visual-studio/vs-storage-webjobs-what-happened)

## <a name="see-also"></a>См. также

- [Форум MSDN: служба хранилища Azure](https://social.msdn.microsoft.com/forums/azure/home?forum=windowsazuredata)
- [Блог команды разработчиков службы хранилища Microsoft Azure](http://blogs.msdn.com/b/windowsazurestorage/)
- [Документация по службе хранилища Azure](https://docs.microsoft.com/azure/storage/)
- [Подключенные службы ( Visual Studio для Mac)](/visualstudio/mac/connected-services)
