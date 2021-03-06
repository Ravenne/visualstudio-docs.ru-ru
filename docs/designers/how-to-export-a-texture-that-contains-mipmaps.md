---
title: Как выполнить Экспорт текстуры, содержащей MIP-карты
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f5226903112d06d5efa362c61db938124eed8e68
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62897322"
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>Как выполнить Экспорт текстуры, содержащей MIP-карты

Конвейер содержимого изображения может создавать MIP-карты из исходного изображения как часть этапа сборки вашего проекта. Для достижения некоторых эффектов иногда требуется задавать содержимое изображения каждого уровня MIP вручную. Если делать этого не нужно, создание MIP-карты во время сборки гарантирует, что содержимое MIP-карты будет всегда синхронизировано. Это также позволяет избежать снижения производительности из-за создания MIP-карты во время выполнения.

В этой статье рассматриваются следующие действия:

- Настройка исходного изображения для обработки в конвейере содержимого изображения.

- Настройка конвейера содержимого изображения для формирования MIP-карты.

## <a name="export-mipmaps"></a>Экспорт MIP-карты

Использование MIP-уровней обеспечивает автоматический уровень детализации экрана пространства для текстурированных поверхностей в трехмерных играх или приложениях. Такой подход позволяет повысить производительность рендеринга игры или приложения путем предварительного вычисления версий текстуры с пониженным качеством. Благодаря этому не требуется вычислять всю текстуру с пониженным качеством всякий раз, когда производится ее выборка.

### <a name="to-export-a-texture-that-has-mipmaps"></a>Экспорт текстуры, содержащей MIP-карты

1. Сначала создайте простейшую текстуру. Загрузите существующий файл изображения или создайте его, как описано в разделе [Практическое руководство. Создание простейшей текстуры](../designers/how-to-create-a-basic-texture.md). Для поддержки MIP-карт укажите текстуру, ширина и высота которой являются степенью 2 например, 64 x 64, 256 x 256 или 512 x 512.

2. Настройте только что созданный файл текстуры так, чтобы он обрабатывался конвейером содержимого изображения. В **обозревателе решений** откройте контекстное меню созданного файла текстуры и выберите пункт **Свойства**. На странице **Свойства конфигурации** > **Общие** задайте для свойства **Тип элемента** значение **Конвейер содержимого изображения**. Убедитесь в том, что свойство **Содержимое** имеет значение **Да**, а свойство **Исключить из сборки** — значение **Нет**. Нажмите кнопку **Применить**.

   Откроется страница свойств конфигурации **конвейера содержимого изображения**.

3. Настройте конвейер содержимого изображения для формирования MIP-карт. На странице **Свойства конфигурации** > **Конвейер содержимого изображения** > **Общие** задайте для свойства **Создать MIP-объекты** значение **Да (/generatemips)**.

4. Нажмите кнопку **ОК**.

Когда выполняется сборка проекта, конвейер содержимого изображения преобразует исходное изображение из рабочего формата в указанный вами выходной формат (в том числе MIP-уровни). Результат копируется в выходной каталог проекта.