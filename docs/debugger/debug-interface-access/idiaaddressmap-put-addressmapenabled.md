---
title: IDiaAddressMap::put_addressMapEnabled | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_addressMapEnabled method
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f36cf93beb6b6c8b66ec25dc8008be7024e398b9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62554343"
---
# <a name="idiaaddressmapputaddressmapenabled"></a>IDiaAddressMap::put_addressMapEnabled
Указывает, следует ли использовать карту для преобразования символа адреса.

## <a name="syntax"></a>Синтаксис

```C++
HRESULT put_addressMapEnabled ( 
   BOOL NewVal
);
```

#### <a name="parameters"></a>Параметры
 NewVal

[in] Значение `TRUE` включить перевод символов, или `FALSE` для отключения.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Исполняемый файл после процессоров иногда обновить исполняемый файл. Доступа к интерфейсу отладки содержит механизм для поддержки преобразования символов для нового макета.

 При загрузке PDB-файл включен карта распределения, сохраненной в файле. Иногда, тем не менее, когда клиентское приложение может понадобиться предоставить свой собственный адрес карты, вызвав [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) метод. Если `set_addressMap` метод выполнен успешно, клиентское приложение должно вызывать `put_addressMapEnabled` метод с `NewVal` параметр `TRUE` для включения использования map этот адрес.

 Текущее состояние включения карты адрес можно получить с помощью вызова [IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md) метод.

## <a name="see-also"></a>См. также
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
- [IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)