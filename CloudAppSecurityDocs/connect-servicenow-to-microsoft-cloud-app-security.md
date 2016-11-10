---
title: "Подключение ServiceNow к Microsoft Cloud App Security | Документы Майкрософт"
description: "В этом разделе приводятся сведения о подключении приложения ServiceNow к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 30ddba23a0c481cb434e9239950cce90c52efc4f


---

# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>Подключение ServiceNow к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи ServiceNow с помощью API соединителя приложений.  
  
## <a name="how-to-connect-servicenow-to-cloud-app-security"></a>Порядок подключения ServiceNow к Cloud App Security  
  
> [!NOTE]  
>  Cloud App Security поддерживает версии ServiceNow Eureka и Fiji. Для подключения к ServiceNow с помощью Cloud App Security требуются разрешения уровня администратора, а экземпляр ServiceNow должен поддерживать доступ к API.  
  
1.  Войти в учетную запись ServiceNow с помощью с учетной записи администратора.  
  
2.  Создайте учетную запись службы для Cloud App Security и подключите к ней роль администратора.  
  
3.  Убедитесь в том, что подключаемый модуль REST API включен.  
  
     ![учетная запись servicenow](./media/servicenow-account.png "servicenow account")  
  
4.  На портале Cloud App Security щелкните **Сведения** и затем **Санкционированные приложения**.  
  
5.  Перейдя в строку ServiceNow, щелкните элемент **Подключение** в столбце **Состояние соединителя приложений** или нажмите кнопку **Подключить приложение**, а затем щелкните элемент **ServiceNow**.  
  
     ![подключение servicenow](./media/connect-servicenow.png "connect servicenow")  
  
6.  На вкладке "API" страницы параметров ServiceNow добавьте имя пользователя, пароль и URL-адрес экземпляра ServiceNow в соответствующих полях.  
  
7.  Нажмите кнопку **Подключить**.  
  
     ![изменение пароля servicenow](./media/servicenow-update-password.png "servicenow update password")  
  
8.  Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Закрыть**.  
  
После подключения ServiceNow вы получите события за 60 дней, предшествовавших подключению.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


