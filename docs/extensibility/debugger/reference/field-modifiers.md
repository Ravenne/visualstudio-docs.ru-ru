---
title: FIELD_MODIFIERS | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FIELD_MODIFIERS
helpviewer_keywords:
- FIELD_MODIFIERS enumeration
ms.assetid: 1e44681c-1f03-41a9-9c04-b79f231b0822
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b22559af26a0a5f6c8af68726a5ba336e1bcfb4a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689633"
---
# <a name="fieldmodifiers"></a>FIELD_MODIFIERS
Задает модификаторы для типа поля.

## <a name="syntax"></a>Синтаксис

```cpp
enum enum_FIELD_MODIFIERS {
    FIELD_MOD_NONE             = 0x00000000,

    // Modifier of the field
    FIELD_MOD_ACCESS_NONE      = 0x00000001,
    FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,
    FIELD_MOD_ACCESS_PROTECTED = 0x00000004,
    FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,

    // Storage modifier of the field
    FIELD_MOD_NOMODIFIERS      = 0x00000010,
    FIELD_MOD_STATIC           = 0x00000020,
    FIELD_MOD_CONSTANT         = 0x00000040,
    FIELD_MOD_TRANSIENT        = 0x00000080,
    FIELD_MOD_VOLATILE         = 0x00000100,
    FIELD_MOD_ABSTRACT         = 0x00000200,
    FIELD_MOD_NATIVE           = 0x00000400,
    FIELD_MOD_SYNCHRONIZED     = 0x00000800,
    FIELD_MOD_VIRTUAL          = 0x00001000,
    FIELD_MOD_INTERFACE        = 0x00002000,
    FIELD_MOD_FINAL            = 0x00004000,
    FIELD_MOD_SENTINEL         = 0x00008000,
    FIELD_MOD_INNERCLASS       = 0x00010000,
    FIELD_TYPE_OPTIONAL        = 0x00020000,
    FIELD_MOD_BYREF            = 0x00040000,
    FIELD_MOD_HIDDEN           = 0x00080000,
    FIELD_MOD_MARSHALASOBJECT  = 0x00100000,
    FIELD_MOD_SPECIAL_NAME     = 0x00200000,
    FIELD_MOD_HIDEBYSIG        = 0x00400000,

    FIELD_MOD_WRITEONLY        = 0x80000000,
    FIELD_MOD_ACCESS_MASK      = 0x000000ff,
    FIELD_MOD_MASK             = 0xffffff00,
    FIELD_MOD_ALL              = 0x7fffffff
};
typedef DWORD FIELD_MODIFIERS;
```

```csharp
public enum enum_FIELD_MODIFIERS {
    FIELD_MOD_NONE             = 0x00000000,

    // Modifier of the field
    FIELD_MOD_ACCESS_NONE      = 0x00000001,
    FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,
    FIELD_MOD_ACCESS_PROTECTED = 0x00000004,
    FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,

    // Storage modifier of the field
    FIELD_MOD_NOMODIFIERS      = 0x00000010,
    FIELD_MOD_STATIC           = 0x00000020,
    FIELD_MOD_CONSTANT         = 0x00000040,
    FIELD_MOD_TRANSIENT        = 0x00000080,
    FIELD_MOD_VOLATILE         = 0x00000100,
    FIELD_MOD_ABSTRACT         = 0x00000200,
    FIELD_MOD_NATIVE           = 0x00000400,
    FIELD_MOD_SYNCHRONIZED     = 0x00000800,
    FIELD_MOD_VIRTUAL          = 0x00001000,
    FIELD_MOD_INTERFACE        = 0x00002000,
    FIELD_MOD_FINAL            = 0x00004000,
    FIELD_MOD_SENTINEL         = 0x00008000,
    FIELD_MOD_INNERCLASS       = 0x00010000,
    FIELD_TYPE_OPTIONAL        = 0x00020000,
    FIELD_MOD_BYREF            = 0x00040000,
    FIELD_MOD_HIDDEN           = 0x00080000,
    FIELD_MOD_MARSHALASOBJECT  = 0x00100000,
    FIELD_MOD_SPECIAL_NAME     = 0x00200000,
    FIELD_MOD_HIDEBYSIG        = 0x00400000,

    FIELD_MOD_WRITEONLY        = 0x80000000,
    FIELD_MOD_ACCESS_MASK      = 0x000000ff,
    FIELD_MOD_MASK             = 0xffffff00,
    FIELD_MOD_ALL              = 0x7fffffff
};
```

## <a name="members"></a>Участники
FIELD_MOD_ACCESS_TYPE указывает, что поле будет недоступно.

FIELD_MOD_ACCESS_PUBLIC указывает, что поле имеет общий доступ.

FIELD_MOD_ACCESS_PROTECTED указывает, что поле имеет защищенный доступ.

FIELD_MOD_ACCESS_PRIVATE указывает, что поле имеет закрытый доступ.

FIELD_MOD_NOMODIFIERS указывает, что поле не содержит модификаторы.

FIELD_MOD_STATIC указывает, что поле является статическим.

FIELD_MOD_CONSTANT указывает, что поле является константой.

FIELD_MOD_TRANSIENT указывает, что поле является временным.

FIELD_MOD_VOLATILE указывает, что поле является временным.

FIELD_MOD_ABSTRACT указывает, что поле является абстрактным.

FIELD_MOD_NATIVE указывает, что поле имеет собственный.

FIELD_MOD_SYNCHRONIZED указывает, что это поле синхронизируется.

FIELD_MOD_VIRTUAL указывает, что поле является виртуальным.

FIELD_MOD_INTERFACE указывает, что поле является интерфейсом.

FIELD_MOD_FINAL указывает, что поле является окончательной.

FIELD_MOD_SENTINEL указывает на то, что поле метки.

FIELD_MOD_INNERCLASS указывает на то, что поле вложенного класса.

FIELD_TYPE_OPTIONAL указывает, что поле является необязательным.

FIELD_MOD_BYREF указывает, что поле является ссылочным аргументом. Это специально для аргументов метода.

FIELD_MOD_HIDDEN указывает, что поле должно содержать скрытые или в другом контексте; например [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] Статические локальные переменные.

FIELD_MOD_MARSHALASOBJECT указывает, что поле представляет объект с `IUnknown` интерфейс.

FIELD_MOD_SPECIAL_NAME указывает, что поле имеет специальное имя, например, `.ctor` для конструктора ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] только).

FIELD_MOD_HIDEBYSIG указывает, что поле имеет `Overloads` ключевое слово, примененных к нему ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] только).

FIELD_MOD_WRITEONLY указывает, что поле доступно только для записи. Это значение не включено в `FIELD_MOD_ALL`, как только такие поля только для записи используется для вычисления функции. Пользователь должен явно запросить `FIELD_MOD_WRITEONLY` поля.

FIELD_MOD_ACCESS_MASK указывает a маска для доступ к полям.

FIELD_MOD_MASK указывает маску для модификаторы поля.

## <a name="remarks"></a>Примечания
Используется для `dwModifiers` членом [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) структуры.

Эти значения также передаются [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md) способ фильтрации для отдельных полей.

## <a name="requirements"></a>Требования
Заголовок: sh.h

Пространство имен: Microsoft.VisualStudio.Debugger.Interop

Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)
- [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)
