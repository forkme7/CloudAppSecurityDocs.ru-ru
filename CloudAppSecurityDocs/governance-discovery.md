---
title: "Блокирование обнаруженных приложений | Документация Майкрософт"
description: "В этом разделе приведена процедура экспорта блоков сценариев для обнаруженных приложений."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/28/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: e451031e-4764-411a-b366-73a49d4f25df
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f970c293c5a1576db1800adc7870cd6f6088ab64
ms.sourcegitcommit: 4fdf9ae2e2b189d4efa6a6588898c8d46d0dda70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
## <a name="govern-discovered-apps"></a>Управление обнаруженными приложениями

После просмотра списка обнаруженных приложений вы можете принять указанные ниже меры, чтобы защитить среду от использования нежелательных приложений.

### <a name="sanctioningunsanctioning-an-app"></a>Применение и отмена санкционирования приложения 

Вы можете отменить санкционирование определенного рискованного приложения, щелкнув многоточие в конце строки и выбрав **Отменить санкционирование**.
Это не запрещает работать с приложением, но позволяет проще контролировать его использование с помощью фильтров Cloud Discovery. Вы можете уведомить пользователей об отмене санкционирования для приложения и предложить альтернативный безопасный вариант.

![Пометить как несанкционированные](./media/tag-as-unsanctioned.png)  


Если имеется список приложений, для которых требуется применить или отменить санкционирование, выберите все нужные приложения с помощью флажков и выполните действие.

Чтобы получить список несанкционированных приложений, вы можете [создать сценарий блокирования с помощью API-интерфейсов Cloud App Security](https://mod636914.us.portal.cloudappsecurity.com/api-docs/#generate-block-script).

## <a name="export-a-block-script-to-govern-discovered-apps"></a>Экспорт сценария блокирования для управления обнаруженными приложениями

Служба Cloud App Security позволяет блокировать доступ к несанкционированным приложениям, используя локальные программно-аппаратные комплексы безопасности. Создайте выделенный блок сценария и импортируйте его на своем программно-аппаратном комплексе.
Это решение не требует перенаправления всего веб-трафика организации на прокси-сервер.

1. В панели мониторинга Cloud App Security отметьте все приложения, которые нужно заблокировать, как **Несанкционированные**.

   ![Пометить как несанкционированные](./media/tag-as-unsanctioned.png)  

2. В строке заголовка щелкните многоточие и выберите команду **Создать сценарий блокирования...**. 

   ![Создание сценария блокирования](./media/generate-block-script.png)  

3. В окне **Создание сценария блокирования** выберите устройство для формирования сценария блокирования. 

   ![Всплывающее окно "Создание сценария блокирования"](./media/generate-block-script-popup.png)  

4. Затем нажмите кнопку "Создать сценарий". Будет создан сценарий блокирования для всех несанкционированных приложений. По умолчанию файл будет назван по дате, когда он был экспортирован, и типу устройства, который вы выбрали, например *2017-02-19_CAS_Fortigate_block_script.txt* 

   ![Кнопка "Создать сценарий блокирования"](./media/generate-block-script-button.png)  

5. Импортируйте созданный файл на программно-аппаратный комплекс.



## <a name="see-also"></a>См. также  
[Ежедневные мероприятия для защиты облачной среды](daily-activities-to-protect-your-cloud-environment.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  