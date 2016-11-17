---
title: "Подключение Okta к Microsoft Cloud App Security | Документация Майкрософт"
description: "В этой статье приводятся сведения о подключении приложения Okta к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a413236b04726dddc69068e39967f6ad17218719
ms.openlocfilehash: c11e133f78c3973006c3e70dd1ccd719f7b639aa


---

# <a name="connect-okta-to-microsoft-cloud-app-security"></a>Подключение Okta к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи Okta с помощью интерфейсов API соединителя.  
  
## <a name="how-to-connect-okta-to-cloud-app-security"></a>Порядок подключения Okta к Cloud App Security  
  
1.  Рекомендуется создать в Okta учетную запись службы с правами администратора для Cloud App Security.  
  
     Используйте учетную запись с разрешениями суперадминистратора.  
  
     Проверьте учетную запись Okta.  
  
2.  В консоли Okta щелкните элемент **Администрирование**.  
  
    -   Щелкните **Безопасность** и затем **API**.  
  
         ![okta api](./media/okta-api.png "okta api")  
  
    -   Щелкните **Создание токена**.  
  
         ![создание токена в okta](./media/okta-createtoken.jpg "okta createtoken")  
  
    -   Во всплывающем окне **Create Token** (Создание токена) укажите имя токена Cloud App Security и щелкните **Create Token** (Создать токен).  
  
         ![всплывающее окно токена в okta](./media/okta-token-popup.png "okta token popup")  
  
    -   Во всплывающем окне с сообщением о том, что **токен успешно создан**, скопируйте **значение токена**.  
  
         ![значение токена в okta](./media/okta-token-value.png "okta token value")  
  
3.  В консоли Cloud App Security щелкните **Сведения**, а затем — **Санкционированные приложения**.  
  
4.  Перейдя в строку Okta, щелкните элемент **Подключение** в столбце **Состояние соединителя приложений** или нажмите кнопку **Подключить приложение**, а затем щелкните элемент **Okta**.  
  
     ![подключение okta](./media/connect-okta.png "connect okta")  
  
5.  На странице API в поле **Домен** введите домен Okta и вставьте токен в поле **Токен**.  
  
6.  Щелкните **Подключить**, чтобы создать токен для Okta в Cloud App Security.  
  
7.  Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Закрыть**.  
  
После подключения Okta вы получите события за 60 дней, предшествовавших подключению.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->


