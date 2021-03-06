---
title: Практическое руководство. Выбор используемых схем XML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41f830214b20df24587cf902e6b180e8a43a8cd3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63007408"
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>Практическое руководство. Выбор используемых схем XML

XML editor предоставляет кэш схем, расположенный в *%VSInstallDir%\xml\Schemas* каталога. Кэш схем включает известные XML-схемы, используемые для поддержки технологии IntelliSense и проверки правильности XML-документа.

Используйте **схемы** свойством, чтобы выбрать один или несколько XML схемами языка определения схемы (XSD) документа. Вы можете выбрать схемы из кэша схем или в другом месте.

Схемы, можно указать сохраняются в файле параметров пользователя (скрытый) решения (. *SUO*), вместе с другими XML-свойства документа. Таким образом не нужно снова вводить эти значения при следующем открытии решения.

> [!NOTE]
> Редактор можно проверить с помощью встроенной схемы или схемы ссылается `xsd:schemaLocation` атрибута. Дополнительные сведения см. в разделе [Проверка XML-документа](../xml-tools/xml-document-validation.md).

## <a name="to-select-an-xml-schema-from-the-schema-cache"></a>Чтобы выбрать схему XML из кэша схем

1. Откройте файл в приложении XML Editor.

2. В окне свойств документа нажмите кнопку в **схемы** поля. Когда обзора кнопку (...) отображается, щелкните его.

   ![Свойство схемы для XML-файла](media/properties-schemas.png)

   [Диалоговом схем XML](xml-schemas-dialog-box.md) открывает. В диалоговом окне указываются все схемы с. *xsd* расширения в кэше схем (включая схемы, на которые ссылается *catalog.xml* файл), а также любой схемы, который в текущем решении, откройте в Visual Studio, на который ссылается `xsd:schemaLocation` атрибут, или на которые ссылается **схемы** свойство.

3. Выберите схемы, которые будут использоваться для проверки правильности, одним из приведенных ниже способов.

   - Выберите схему из списка в **XML-схем** диалоговое окно, нажмите кнопку **используйте** столбец, а затем выберите **использовать эту схему**.

     -или-

   - Выделите несколько схем в **XML-схем** диалоговое окно, а затем щелкните правой кнопкой мыши и выберите **использовать эту схему**.

4. Нажмите кнопку **ОК**.

   Список выбранных схем копируется обратно **схемы** свойством документа.

## <a name="to-add-an-xml-schema-to-the-schema-cache"></a>Чтобы добавить схему XML в кэш схем

1. В окне свойств документа нажмите кнопку на **схемы** поля.

2. Нажмите кнопку **Добавить**.

   **Открытие XSD-схемы** откроется диалоговое окно.

3. Выполните поиск и выберите схемы, которые нужно добавить в кэш схем.

4. Нажмите кнопку **Открыть**.

   Схемы добавляются в кэш схем и **используйте** присваивается значение столбца **использовать эту схему**.

## <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>Чтобы удалить схему XML из кэша схем

1. В окне свойств документа нажмите кнопку на **схемы** поля.

2. Выберите схему, нужно удалить, а затем нажмите кнопку **удалить**.

   Схема удаляется из кэша схем, находящегося в оперативной памяти, но не из файловой системы.

   > [!NOTE]
   > Если у вас по-прежнему есть ссылку на схему через `schemaLocation` атрибута или соответствующий `targetNamespace` затем **удалить** не будет работать в этой ситуации из-за автоматического связывания. В этом случае рекомендуется пометить схему как **не использовать выбранные схемы** в **использовать** столбца.

## <a name="see-also"></a>См. также

- [Кэш схем](../xml-tools/schema-cache.md)
- [Диалоговое окно схемы XML](../xml-tools/xml-schemas-dialog-box.md)
- [Редактор XML](../xml-tools/xml-editor.md)