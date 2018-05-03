---
title: Подключение Okta к Cloud App Security для видимости и контроля использования | Документы Майкрософт
description: В этой статье приводятся сведения о подключении приложения Okta к Cloud App Security с помощью соединителя API.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9c3673b9-99bd-400c-9da1-5bf809ea5892
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c8f789798297b01ee324e3e3c824461f14eb3e9c
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*



# <a name="connect-okta-to-microsoft-cloud-app-security"></a>Подключение Okta к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Microsoft Cloud App Security к существующей учетной записи Okta с помощью интерфейсов API соединителя.  
  
## <a name="how-to-connect-okta-to-cloud-app-security"></a>Порядок подключения Okta к Cloud App Security  
  
1.  Рекомендуется создать в Okta учетную запись службы с правами администратора для Cloud App Security.  
  
     Используйте учетную запись с разрешениями суперадминистратора.  
  
     Проверьте учетную запись Okta.  
  
2.  В консоли Okta щелкните элемент **Администрирование**.  
  
    -   Щелкните **Безопасность** и затем **API**.  
  
         ![okta api](./media/okta-api.png "okta api")  
  
    -   Щелкните **Создание токена**.  
  
         ![создание токена в okta](./media/okta-createtoken.jpg "создание токена в okta")  
  
    -   Во всплывающем окне **Create Token** (Создание токена) укажите имя токена Cloud App Security и щелкните **Create Token** (Создать токен).  
  
         ![всплывающее окно токена в okta](./media/okta-token-popup.png "всплывающее окно токена в okta")  
  
    -   Во всплывающем окне с сообщением о том, что **токен успешно создан**, скопируйте **значение токена**.  
  
         ![значение токена в okta](./media/okta-token-value.png "значение токена в okta")  
  
3.  В консоли Cloud App Security щелкните **Исследовать**, а затем — **Подключенные приложения**.  
  
4.  На странице **App connectors** (Соединители с приложениями) щелкните знак "плюс", а затем — **Okta**.  
  
     ![подключение okta](./media/connect-okta.png "подключение okta")  
  
5.  Во всплывающем окне в поле **Домен** укажите домен Okta и вставьте токен в поле **Токен**.  
  
6.  Щелкните **Подключить**, чтобы создать токен для Okta в Cloud App Security.  
  
7.  Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Закрыть**.  
  
После подключения Okta вы получите события за 60 дней, предшествовавших подключению.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  