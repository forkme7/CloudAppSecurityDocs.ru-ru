---
title: "Подключение Azure к Cloud App Security для прозрачности и контроля работы | Microsoft Docs"
description: "Этот раздел описывает, как подключить Azure к Cloud App Security с помощью API соединителя."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/6/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 75b5a6fb3707872f0455da1a1856b55adb17c597
ms.sourcegitcommit: f9851779aa15b11f559e56ac818f1333f027c000
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2017
---
# <a name="connect-azure-to-microsoft-cloud-app-security"></a>Подключение Azure к Microsoft Cloud App Security

Этот раздел содержит указания по подключению Cloud App Security к имеющейся у вас учетной записи Azure с помощью API соединителя приложений.  
  
## <a name="setting-up-azure-for-connection-to-cloud-app-security"></a>Настройка Azure для подключения к Cloud App Security

Cloud App Security подключается к Azure через концентраторы событий. Этот раздел содержит указания по потоковой передаче всех ваших журналов действий в общий концентратор событий в вашей подписке. 

### <a name="step-1-stream-your-azure-activity"></a>Шаг 1: потоковая передача ваших действий в Azure

1.  Настройте потоковую передачу журнала действий вашей подписки Azure в концентратор событий. Следуйте официальному руководству в документации Azure: https://docs.microsoft.com/ru-ru/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs

 > [!NOTE]
 > При наличии нескольких подписок Azure это нужно будет сделать для каждой из них, используя общий концентратор событий.

 После выполнения указаний будет создан новый концентратор событий в выбранном вами пространстве имен.

### <a name="step-2-get-a-connection-string-to-your-event-hub"></a>Шаг 2: получение строки подключения к концентратору событий

1.  Перейдите к колонке концентраторов событий.
  
   ![Колонка концентраторов событий](media/azure-event-hubs.png "Концентраторы событий Azure")

2.  Выберите нужное пространство имен концентратора событий.
  
    ![Пространство имен концентратора событий](media/azure-namespace.png "Пространство имен Azure")

3.  В меню в разделе **Сущности** щелкните **Концентраторы событий**. 
  
    ![Сущности концентраторов событий](media/azure-event-hubs-entities.png "Сущности концентратора событий Azure")

4.  Выберите новый концентратор событий, созданный Azure Monitor. Он называется **insights-operational-logs**.
  
    ![Операционные журналы аналитики](media/azure-insight-operational-logs.png "Операционные журналы аналитики Azure")

5. Создайте политику доступа, которая предоставит Cloud App Security разрешение на чтение из концентратора событий. Для этого щелкните **Политики общего доступа**, а затем — **Добавить**.
  
    ![Политики общего доступа](media/azure-shared-access-policies.png "Политика общего доступа Azure")

6.  Введите имя новой политики и обязательно включите в нее как минимум **утверждение "Прослушивание"**. По завершении щелкните **Создать**.
  
    ![Новая политика Azure](media/azure-new-policy.png "Создание новой политики Azure")

7.  В разделе **Параметры** — **Политики общего доступа** щелкните только что созданную вами политику доступа.   
  
    ![Выбор политики Azure](media/azure-select-policy.png "Выбор политики Azure")

8. В окне политики скопируйте одну из строк подключения, нажав на кнопку рядом с полем **Строка подключения — первичный ключ** или **Строка подключения — вторичный ключ**.

### <a name="step-3-add-azure-to-cloud-app-security"></a>Шаг 3: добавление Azure к Cloud App Security
 
1.  На портале Cloud App Security выберите пункты **Исследовать** и **Подключенные приложения**.  
  
3.  На странице **Соединители с приложениями** щелкните знак "плюс" и выберите **Microsoft Azure**.  
  
     ![Подключение Azure к Cloud App Security](media/azure-connect-app.png "Подключение Azure")  
  
4.  В поле **Строка подключения** вставьте строку, скопированную вами на предыдущем шаге.  
  
5.  В поле **Группа потребителей** введите "$Default", если вы не создали для использования другую группу.
  
6.  Нажмите кнопку **Подключить**.
8.  Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Закрыть**.  
  





## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  