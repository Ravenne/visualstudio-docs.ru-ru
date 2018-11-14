---
title: Доступ к виртуальным машинам Azure из обозревателя сервера | Документация Майкрософт
description: Получите общие сведения для просмотра, создания и управления виртуальными машинами Azure (ВМ) в обозревателе серверов в Visual Studio.
author: ghogen
manager: douge
assetId: eb3afde6-ba90-4308-9ac1-3cc29da4ede0
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 8/31/2017
ms.author: ghogen
ms.openlocfilehash: e1410b3dc60ec9689b6582e794aaf10cd13092aa
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002354"
---
# <a name="accessing-azure-virtual-machines-from-server-explorer"></a>Доступ к виртуальным машинам Azure из обозревателя сервера

Если у вас есть виртуальные машины, размещенные в Azure, они будут доступны в обозревателе серверов. Вы должны сначала войдите в свою подписку Azure просмотреть мобильные службы. Чтобы войти, откройте контекстное меню для узла Azure в обозревателе серверов и выберите **подключиться к Microsoft Azure**.

1. В Cloud Explorer выберите виртуальную машину и нажмите клавишу F4 для отображения окна ее свойств.

    В следующей таблице показано, какие свойства доступны, но они являются только для чтения. Чтобы изменить их, используйте [портала Azure](http://go.microsoft.com/fwlink/p/?LinkID=525040).

   | Свойство. | Описание |
   | --- | --- |
   | DNS-имя |URL-адрес, адрес Интернета виртуальной машины. |
   | Среда |Для виртуальной машины значение этого свойства всегда равно рабочей среде. |
   | name |Имя виртуальной машины. |
   | Размер |Размер виртуальной машины, который отражает объем памяти и дискового пространства, который доступен. Дополнительные сведения см. в разделе [размеры виртуальных машин](https://docs.microsoft.com/azure/cloud-services/cloud-services-sizes-specs). |
   | Status |Значения включают запуск, Started, остановка, остановлен и получение состояния. Если получение состояния, текущее состояние неизвестно. Значения для этого свойства отличаются от значений, которые используются в [портала Azure](http://go.microsoft.com/fwlink/p/?LinkID=525040). |
   | Идентификатор подписки |Идентификатор подписки для учетной записи Azure. Эти сведения можно узнать на [портала Azure](http://go.microsoft.com/fwlink/p/?LinkID=525040) , просмотрев свойства для подписки. |
2. Выберите узел конечной точки, а затем просмотрите **свойства** окна.
3. В следующей таблице описаны доступные свойства конечных точек, но они доступны только для чтения. Чтобы добавить или изменить конечные точки для виртуальной машины, используйте [портала Azure](http://go.microsoft.com/fwlink/p/?LinkID=525040). 

   | Свойство. | Описание |
   | --- | --- |
   | name |Идентификатор конечной точки. |
   | Частный порт |Порт для доступа к сети, внутренней для приложения. |
   | Протокол |Протокол, который использует транспортного уровня для этой конечной точки, TCP или UDP. |
   | Общий порт |Порт, который используется для общего доступа к приложению. |