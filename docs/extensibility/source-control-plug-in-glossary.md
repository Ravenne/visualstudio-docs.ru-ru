---
title: Глоссарий подключаемого модуля управления источника | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- glossary [Visual Studio SDK]
- source control plug-ins, glossary
ms.assetid: f224bbc9-38fc-4c80-ab09-51dcc8969f8e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0df624a27513fa0eb18b2643bb7c680d71d94c0c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62432425"
---
# <a name="source-control-plug-in-glossary"></a>Глоссарий подключаемого модуля системы управления версиями
Следующие полезные термины и определения относятся к документации по SDK подключаемого модуля управления источника.

## <a name="definitions"></a>Определения
 Возврат, когда пользователь вносит изменения в рабочей копии, пользователь должен передачи изменений из рабочей копии в хранилище контроля центрального источника. Это создает новую редакцию файла, который становится доступным для других пользователей. Этот процесс называется возврат.

 Извлечение процесс запрашивает рабочую копию из репозитория, о том, в репозиторий намерение изменить его. Рабочую копию отражает состояние проекта, начиная с момента он извлечен.

 Клиент А программа системы управления исходным кодом. В этой документации это интегрированной среде разработки Visual Studio.

 Комментарий типа сообщение, описывающее изменения, которые пользователь может присоединять к версии, при выполнении операции управления версиями.

 Конфликт типа ситуация, когда два пользователя пытаются проверить изменяется на том же регионе того же файла. Как правило необходимо выполнить слияние.

 Каталог объект клиентской стороны локальную папку называется каталог. Это копия, в которой пользователь фактически вносит изменения. Может существовать множество рабочие копии данного проекта; Обычно каждый разработчик имеет собственную копию.

 Операция получения Get A переводит пользователя рабочую копию в актуальном состоянии с копией репозитория. В отличие от извлечения get выполняется, когда пользователь просто должен последней копии и планирует никаких изменений.

 Журнал, который он обычно представляет собой сводку всех извлечения, возвраты, обновлений, теги и выпуски, в репозитории системы управления версиями.

 Интегрированная среда разработки обычно относится к интегрированной среде разработки Visual Studio. Тем не менее она также может ссылаться на другие клиентские среды, которые распознают API подключаемых модулей управления источника.

 Объединить процесс во время исходного два или несколько файлов кода объединяются новый файл, который включает в себя все функции из предыдущих файлов. Эта концепция важна в системе управления версиями, где нескольким разработчикам работать с файлами, одновременно.

 Папка системы управления версиями проект A часто называют проекта. Это не имеет никакой связью с проектов или решений в Visual Studio.

 Библиотеки DLL подключаемого модуля, которая предоставляет функции системы управления версиями, реализовав API подключаемых модулей управления источника.

 Репозиторий мастер-копию, где система управления версиями хранит журнал полной версии проекта. Каждый проект имеет ровно один репозиторий.

 Версия типа зафиксированные изменения в журнал файла или набора файлов. Версии является одним моментальных снимков в постоянно меняющаяся проекта.

## <a name="see-also"></a>См. также
- [Подключаемые модули системы управления версиями](../extensibility/source-control-plug-ins.md)