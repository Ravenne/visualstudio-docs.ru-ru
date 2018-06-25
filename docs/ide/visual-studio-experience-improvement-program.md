---
title: Программа улучшения качества программного обеспечения
description: Узнайте, как управлять параметрами конфиденциальности в Visual Studio.
ms.date: 05/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
author: PoulChapman
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8dbc83a2d3fe1b2f5bb32a6baaf336c0a6c46e7d
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572638"
---
# <a name="visual-studio-customer-experience-improvement-program"></a>Программа улучшения качества программного обеспечения Visual Studio

Программа улучшения качества программного обеспечения Visual Studio (VSCEIP) помогает Майкрософт совершенствовать Visual Studio. Эта программа [собирает сведения об ошибках](../ide/diagnostic-data-collection.md), компьютерном оборудовании и использовании Visual Studio, не прерывая работу пользователей на компьютере. Собранные сведения помогают корпорации Майкрософт понять, какие функции нуждаются в улучшении. В этом документе описано, как принять участие в программе VSCEIP или отказаться.

[!INCLUDE [gdpr-hybrid-note](../misc/includes/gdpr-hybrid-note.md)]

## <a name="opt-in-or-out"></a>Управления участием в программе

Программа VSCEIP включена по умолчанию. Вы можете отключить ее или включить снова следующим образом:

1. Запустите Visual Studio.

1. В меню **Справка** нажмите **Отправить отзыв** и выберите **Параметры**.

   Откроется диалоговое окно **Программа улучшения Visual Studio**.

1. Чтобы отказаться от участия, выберите **Я не хочу участвовать** и нажмите **ОК**.
   Чтобы согласиться на участие, выберите **Я хочу участвовать** и нажмите **ОК**.

   ![Диалоговое окно "Программа улучшения Visual Studio"](media/experience-improvement-program.png)

### <a name="registry-settings"></a>Параметры реестра

Если вы устанавливаете [Build Tools для Visual Studio](https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2017), обновите реестр, чтобы настроить VSCEIP. Корпоративные клиенты могут создать групповую политику на основе реестра, в которой будет включено или отключено участие в программе VSCEIP.

Ниже приведены соответствующие разделы и параметры реестра:

В 64-разрядной операционной системе: ключ = **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSCommon\15.0\SQM**  
В 32-разрядной операционной системе: ключ = **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSCommon\15.0\SQM**  
Если включена групповая политика: ключ = **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\VisualStudio\SQM**  

Запись = **OptIn**

Значение = (DWORD)
- **0** — отказаться (отключить VSCEIP)
- **1** — согласиться (включить VSCEIP)

> [!CAUTION]
> Неправильное редактирование реестра может нанести серьезный вред системе. Перед внесением изменений следует создать резервные копии всех важных данных, имеющихся на компьютере. В случае возникновения неполадок после внесения изменений вручную можно использовать параметр запуска **Загрузка последней удачной конфигурации**.

Для получения информации о собранных, обработанных или переданных VSCEIP сведениях см. [Заявление о конфиденциальности Майкрософт](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>См. также

* [Диагностическая информация, собираемая Visual Studio](diagnostic-data-collection.md)
* [Обратная связь](../ide/talk-to-us.md)
* [Как сообщить о проблеме с Visual Studio 2017](../ide/how-to-report-a-problem-with-visual-studio-2017.md)
* [Сообщество разработчиков Visual Studio](https://developercommunity.visualstudio.com/)
* [Заявление о конфиденциальности Майкрософт](https://privacy.microsoft.com/privacystatement)