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
ms.assetid: 9c3673b9-99bd-400c-9da1-5bf809ea5892
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e41c04d25f12aa5207ef9ffbb6a22f4b894e92cb
ms.openlocfilehash: f5f355a42321e4467ce3ef487c48508522a286ab


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
  
3.  В консоли Cloud App Security щелкните **Исследовать**, а затем — **Подключенные приложения**.  
  
4.  На странице **Соединители приложений** нажмите кнопку **Подключить приложение**, а затем — **Okta**.  
  
     ![подключение okta](./media/connect-okta.png "connect okta")  
  
5.  Во всплывающем окне в поле **Домен** укажите домен Okta и вставьте токен в поле **Токен**.  
  
6.  Щелкните **Подключить**, чтобы создать токен для Okta в Cloud App Security.  
  
7.  Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Закрыть**.  
  
После подключения Okta вы получите события за 60 дней, предшествовавших подключению.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier](https://premier.microsoft.com/).  
  
  


<!--HONumber=Nov16_HO4-->


