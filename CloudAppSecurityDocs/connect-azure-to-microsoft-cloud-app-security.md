---
title: "Подключение Azure к Cloud App Security для прозрачности и контроля работы | Microsoft Docs"
description: "Этот раздел описывает, как подключить Azure к Cloud App Security с помощью API соединителя."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 81860849cb2c1a2a6d35c34e893d0e241a5f670f
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2018
---
# <a name="connect-azure-to-microsoft-cloud-app-security"></a>Подключение Azure к Microsoft Cloud App Security

Этот раздел содержит указания по подключению Cloud App Security к имеющейся у вас учетной записи Azure с помощью API соединителя приложений.  
  
## <a name="setting-up-azure-for-connection-to-cloud-app-security"></a>Настройка Azure для подключения к Cloud App Security

Cloud App Security подключается к Azure через концентраторы событий. Этот раздел содержит указания по потоковой передаче всех ваших журналов действий в общий концентратор событий в вашей подписке. 

### <a name="step-1-stream-your-azure-activity-logs-to-event-hubs"></a>Шаг 1. Потоковая передача журналов действий Azure в концентраторы событий

1.  Настройте потоковую передачу журнала действий вашей подписки Azure в концентратор событий. Следуйте официальному руководству в документации Azure: https://docs.microsoft.com/ru-ru/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs

 > [!NOTE]
 > При наличии нескольких подписок Azure это нужно будет сделать для каждой из них, используя общий концентратор событий.

 После выполнения указаний будет создан новый концентратор событий в выбранном вами пространстве имен.
 
 > [!NOTE]
 > Если при попытке экспортировать журналы действий возникает ошибка, перейдите в Azure к колонке **Поставщики ресурсов** и проверьте в меню слева, зарегистрирован ли компонент microsoft.insights.

### <a name="step-2-get-a-connection-string-to-your-event-hub"></a>Шаг 2: получение строки подключения к концентратору событий

1.  Откройте меню слева **Концентраторы событий (предварительная версия)**.
  
   ![Меню концентраторов событий](media/azure-event-hubs.png "Концентраторы событий Azure")

2.  Выберите нужное пространство имен концентратора событий.
  
    ![Пространство имен концентратора событий](media/azure-namespace.png "Пространство имен Azure")

3.  В меню в разделе **Сущности** щелкните **Концентраторы событий**. 
  
    ![Сущности концентраторов событий](media/azure-event-hubs-entities.png "Сущности концентратора событий Azure")

4.  Выберите новый концентратор событий, созданный Azure Monitor. Он называется **insights-operational-logs**.
  > [!NOTE]
  > Создание концентратора событий может занять несколько минут.

   ![Операционные журналы аналитики](media/azure-insight-operational-logs.png "Операционные журналы аналитики Azure")
  
  
5. Создайте политику доступа, которая предоставит Cloud App Security разрешение на чтение из концентратора событий. Для этого щелкните **Политики общего доступа**, а затем — **Добавить**.
  
    ![Политики общего доступа](media/azure-shared-access-policies.png "Политика общего доступа Azure")

6.  Введите имя новой политики и обязательно включите в нее как минимум **утверждение "Прослушивание"**. По завершении щелкните **Создать**.
  
    ![Новая политика Azure](media/azure-new-policy.png "Новая политика Azure")

7.  В разделе **Параметры** — **Политики общего доступа** щелкните созданную вами политику доступа.   
  
    ![Политика Azure](media/azure-select-policy.png "Политика Azure")

8. В окне политики скопируйте одну из строк подключения, нажав кнопку рядом с полем **Строка подключения — первичный ключ** или **Строка подключения — вторичный ключ**.

### <a name="step-3-add-azure-to-cloud-app-security"></a>Шаг 3: добавление Azure к Cloud App Security
 
1.  На портале Cloud App Security выберите пункты **Исследовать** и **Подключенные приложения**.  
  
3.  На странице **Соединители с приложениями** щелкните знак "плюс" и выберите **Microsoft Azure**.  
  
     ![Подключение Azure к Cloud App Security](media/azure-connect-app.png "Подключение Azure")  
  
4.  В поле **Строка подключения** вставьте строку, скопированную вами на предыдущем шаге.  
  
5.  В поле **Группа потребителей** введите `$Default`
    
   >[!NOTE] 
   > Если вы создали для использования другую группу, вставьте в поле **Группа потребителей** ее имя.
  
6.  Нажмите кнопку **Подключиться**, чтобы подключиться и проверить соединение. Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Закрыть**.  


> [!NOTE]
> Этот компонент находится в частной предварительной версии.


## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  