---
title: 'Начало работы с PTVS: редактирование кода | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b412c87c-2f09-4e25-9cc8-ab54f4c44412
caps.latest.revision: 5
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: f70e551fd44c18c9dbfc37437703ca092e982d6a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47569775"
---
# <a name="getting-started-with-ptvs-editing-code"></a>Начало работы с PTVS. Редактирование кода
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

PTVS обеспечивает эффективную среду редактирования Visual Studio для Python.  
  
 Эти инструкции можно просмотреть в очень коротком [видеоролике в Youtube](https://www.youtube.com/watch?v=uZGZNEyyeKs&index=3&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff).  
  
 Начните с базового пустого шаблона проекта приложения Python.  
  
 Начните вводить строку `from … import` в редакторе.  На экран будет выведен всплывающий список вариантов завершения с полным списком модулей, которые доступны для импорта.  Этот список зависит от версии Python и установленных библиотек.  Используйте математическую библиотеку в качестве примера.  Вы заметите, что при вводе список вариантов завершения для этих элементов фильтруется, включая введенные символы.  Завершите инструкцию, импортировав идентификатор `sin`.  
  
```python  
from math import sin  
  
```  
  
 Если при написании кода вы используете идентификатор, который не привязан, но может быть обнаружен в библиотеках, PTVS выдает всплывающее окно быстрого исправления для добавления соответствующей инструкции импорта.  Например, если вы ввели `cos`, то будет **Импорт из математических** предлагаемых.  
  
 Для создания кода можно использовать фрагменты.  В меню «Правка» выберите IntelliSense, а затем «Вставить фрагмент».  Выберите Python, а затем def.  Вызовите функцию `make_dot_string` и добавьте один параметр `x`.  Теперь можно добавить в файл утверждения для управляемой тестами разработки: PTVS выведет новые предложения функций в списке вариантов завершения.  
  
```python  
assert make_dot_string(90) == '          o'  
assert make_dot_string(180) == 'o'  
  
```  
  
 Теперь вы можете вернуться к новой функции и начать написание следующего тела функции:  
  
```python  
return " " * int(10 * cos(radians(x)) + 10) + "o"  
  
```  
  
 Вы видите, что система PTVS предположила, что параметр является целым числом, так как был проведен анализ мест вызова этой функции.   Окно быстрого исправления также может пригодиться для импорта `radians`.  
  
 Используйте еще один фрагмент, чтобы создать основной блок. Для этого введите `main` на верхнем уровне, вызвав интерфейс смарт-тегов и используя вкладку для выбора «def main …».  Напишите базовый цикл для вызова `make_dot_string`.  Как видите, PTVS становится известно, что функция вернет строку, если вы нажимаете клавишу точки, и на экран выводятся варианты завершения.  Подобные сведения о типах будут предлагаться в ходе разработки всей программы, и, какие бы значения вы ни вводили, среда может предложить подсказки и варианты завершения, которые помогут вам в понимании и написании кода.  
  
 Добавьте вызов для печати, и будет создан основной блок, аналогичный следующему:  
  
```python  
def main ():  
    for i in range(10000000):  
        s = make_dot_string(i)  
        print(s)  
```  
  
 Если нажать клавишу F5, код будет выполнен в окне cmd.exe и вы увидите мерцающую точку.  
  
 Эти инструкции можно просмотреть в очень коротком [видеоролике в Youtube](https://www.youtube.com/watch?v=uZGZNEyyeKs&index=3&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff).  
  
## <a name="see-also"></a>См. также  
 [Документация на вики-сайте](https://github.com/Microsoft/PTVS/wiki/Editor-Features)   
 [Видеоролики по началу работы и углубленному рассмотрению PTVS](https://www.youtube.com/playlist?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)
