---
title: "Подключение ServiceNow к Cloud App Security для видимости и контроля использования | Документы Майкрософт"
description: "В этом разделе приводятся сведения о подключении приложения ServiceNow к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1f4fd428f762bcbe1fb2a26bf44268cf985fbd4f
ms.sourcegitcommit: c79c405a1277c5fcebbc245fa12ff8feb53248d5
translationtype: HT
---
# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>Подключение ServiceNow к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи ServiceNow с помощью API соединителя приложений.  
  
## <a name="how-to-connect-servicenow-to-cloud-app-security"></a>Порядок подключения ServiceNow к Cloud App Security  
  
> [!NOTE]  
>  Cloud App Security поддерживает версии ServiceNow Eureka, Fiji, Geneva, Helsinki и Istanbul. Для подключения к ServiceNow с помощью Cloud App Security требуется роль **администратора**, а экземпляр ServiceNow должен поддерживать доступ к API.  Дополнительные сведений см. в [документации по ServiceNow](http://wiki.servicenow.com/index.php?title=Base_System_Roles#gsc.tab=0).
  
1.  Войти в учетную запись ServiceNow с помощью с учетной записи администратора.  
  
2.  В строке поиска **Filter navigator** (Навигатор фильтра) введите **OAuth** и выберите **Application Registry** (Реестр приложения).

3. В строке меню **Application Registries** (Реестры приложения) выберите пункт **New** (Создать), чтобы создать профиль OAuth.

   ![Новый профиль OAuth в ServiceNow](./media/servicenow-app-registry.png)

4. В разделе **What kind of OAuth application?** (Тип приложения OAuth) щелкните **Create an OAuth API endpoint for external clients** (Создать конечную точку API OAuth для внешних клиентов).

   ![Тип OAuth в ServiceNow](./media/servicenow-oauth-app-type.png)

5. В разделе **Application Registries New record** (Новая запись в реестрах приложения) укажите следующие данные:
    
    - В поле **Name** (Имя) введите имя нового профиля OAuth, например CloudAppSecurity. 
    
    - Значение в поле **Client ID** (Идентификатор клиента) будет создано автоматически. Скопируйте этот идентификатор — его потребуется вставить в Cloud App Security для завершения подключения.
    
    - В поле **Client Secret** (Секрет клиента) введите строку. Если оставить это поле пустым, автоматически будет создан произвольный секрет. Скопируйте и сохраните его для последующего использования. 
    
    - Увеличьте значение в поле **Access Token Lifespan** (Время существования токена доступа) по крайней мере до 3600.
    
    - Нажмите кнопку **Отправить**.

   ![Идентификаторы профилей ServiceNow](./media/servicenow-profile-ids.png)

6.  На портале Cloud App Security выберите пункты **Исследовать** и **Подключенные приложения**.  
  
7.  На странице **App connectors** (Соединители с приложениями) щелкните знак "плюс", а затем — **ServiceNow**.  
  
     ![подключение servicenow](./media/connect-servicenow.png "подключение servicenow")  
  
8.  Во всплывающем окне добавьте имя пользователя, пароль, URL-адрес экземпляра ServiceNow, а также идентификатор клиента и секрет клиента.  
  
9.  Нажмите кнопку **Подключить**.  
  
     ![подключение servicenow к ЦС](./media/servicenow-portal-connect.png "подключение servicenow на портале")  
  
10.  Убедитесь, что подключение установлено, щелкнув **Test now** (Проверить).  
  
     Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Закрыть**.  
  
После подключения ServiceNow вы получите события за 60 дней, предшествовавших подключению.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
