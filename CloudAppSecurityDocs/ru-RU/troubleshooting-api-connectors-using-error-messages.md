---
title: Устранение проблем с соединителями с приложениями при помощи сообщений об ошибках в Cloud App Security | Microsoft Docs
description: В этой статье приводится список сообщений об ошибках соединителей приложений API, а также рекомендации по устранению каждой из них.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 4b6ac04a-4653-4c4a-bd6f-5926743475cc
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 7868aeef5b2a8650d909e4103d0718a724d0c97d
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*

# <a name="troubleshooting-app-connectors-using-error-messages"></a>Устранение проблем с соединителями с приложениями при помощи сообщений об ошибках

Ошибки в соединителе с приложением можно увидеть в диалоговом окне соединителя с приложением после попытки подключиться к облачному приложению при помощи соединителя с приложением API.


> [!div class="mx-tableFixed"]
> 
> |Сообщение об ошибке|Соответствующее приложение|Описание|Разрешение|
> |----|----|----|------------|
> |HttpRequestFailure: Сервер вернул сообщение: 400 — неверный запрос: {"error":{"code":"AF20012","message":"Указанный идентификатор клиента (Tenant_ID) неправильно настроен в системе."|Office 365 |Не найдены назначенные лицензии Office 365. |Назначьте клиенту по крайней мере одну лицензию Office 365.| 
> |AuthFatalFailureException: com.box.boxjavalibv2.exceptions.BoxServerException: {"error":"invalid_grant","error_description":"Недопустимый токен обновления"}|Поле|Недопустимый токен обновления Box|Выполните процедуру подключения Box к Cloud App Security снова.|
> |BoxRestException: не удалось проанализировать запрос.|Поле|Внутренняя ошибка|Еще раз щелкните ссылку "Протестировать сейчас", чтобы протестировать подключение к Box.|
> |ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"Недопустимый токен обновления"}|Поле|Недопустимый токен обновления Box|Выполните процедуру подключения Box к Cloud App Security снова.|
> |BoxServerException: эта функция недоступна пользователю без корпоративной версии|Поле|Учетная запись Box не является учетной записью версии Enterprise.|Обновите лицензию Box до версии Enterprise, а затем выполните процедуру подключения Box к Cloud App Security снова.|
> |BoxServerException: недостаточно прав — невозможно произвести авторизацию в этой службе|Поле|Администратор Box удалил приложение Cloud App Security в Box.|Выполните процедуру подключения Box к Cloud App Security снова.|
> |HttpRequestFailure: сервер вернул сообщение: 401 — не санкционировано|Okta|Недопустимый токен Okta.|Выполните процедуру подключения Okta к Cloud App Security снова.|
> |IOException:|Okta|Внутренняя ошибка|Обратитесь в службу поддержки.|
> |HttpRequestFailure: сервер вернул сообщение: 404 — не найдено|Okta|Внутренняя ошибка|Обратитесь в службу поддержки.|
> |SocketTimeoutException: истекло время ожидания операции чтения|Salesforce|Внутренняя ошибка|Еще раз щелкните ссылку "Протестировать сейчас", чтобы протестировать подключение к Salesforce.|
> |HttpRequestFailure: сервер вернул сообщение: 400 — неверный запрос|Salesforce|Не удалось установить подключение к Salesforce, либо истек срок его действия.|Выполните процедуру подключения Salesforce к Cloud App Security снова.|
> |HttpRequestFailure: сервер вернул сообщение: 401 — не санкционировано|Office 365|Внутренняя проблема|Еще раз щелкните ссылку "Протестировать сейчас".|
> |TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: ошибка при проверке учетных данных. AADSTS70008: истек срок действия предоставленного кода авторизации или токена обновления. Отправьте новый интерактивный запрос авторизации для этого пользователя и ресурса.|Office 365|Истек срок действия токена|Выполните процедуру подключения Office 365 к Cloud App Security снова.|
> |SocketTimeoutException: истекло время ожидания операции чтения|Office 365|Внутренняя ошибка|Еще раз щелкните ссылку "Протестировать сейчас".|
> |NullPointerException|Office 365|Внутренняя ошибка|Обратитесь в службу поддержки.|
> |IgniteException|Office 365|Недопустимый домен или пользователь|Сбросьте настройки и выполните процедуру подключения Office 365 к Cloud App Security снова.|
> |ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: ошибка при проверке учетных данных. AADSTS70008: истек срок действия предоставленного кода авторизации или токена обновления. Отправьте новый интерактивный запрос авторизации для этого пользователя и ресурса.|Office 365|Недопустимый домен или пользователь|Сбросьте настройки и выполните процедуру подключения Office 365 к Cloud App Security снова.|
> |HttpRequestFailure: сервер вернул сообщение: 400 — неверный запрос|Office 365|Внутренняя ошибка|Щелкните ссылку "Протестировать сейчас" еще раз через несколько минут. Если это не поможет, выполните процедуру подключения Office 365 к Cloud App Security снова.|
> |GoogleJsonResponseException: 401 —недостаточно прав|G Suite|Доступ запрещен. У вас нет прав на чтение записей действий. Вам необходимо войти в G Suite с правами администратора.|Выполните процедуру подключения G Suite к Cloud App Security повторно, используя учетную запись администратора.|
> |GoogleJsonResponseException: 403 — запрещено|G Suite|Ошибка при выполнении API G Suite.|Если вы только что развернули соединитель приложения Cloud App Security для G Suite, проверьте следующее: если вы выбрали вариант "Без ограничений", в вашей учетной записи G Suite действительно должны отсутствовать ограничения. Если это не так, запустите соединитель приложений снова и отмените выбор неограниченной учетной записи. Проверьте правильность областей действия, определенных при настройке. Если это не новое развертывание, причина возникновения такой ошибки может заключаться в том, что сегодня достигнут предел использования API и сбор событий G Suite возобновится завтра.|
> |TokenResponseException: 400 — неверный запрос|G Suite|Не удалось установить подключение к G Suite, либо истек срок его действия.|Повторно выполните процедуру подключения G Suite к Cloud App Security.|
> |RuntimeException: com.adallom.adalib.httputils.exceptions.HttpRequestFailure: сервер вернул сообщение: 403 — запрещено|ServiceNow|Неправильные разрешения|Выполните процедуру подключения ServiceNow к Cloud App Security снова, используя учетную запись администратора.|
> |HttpRequestFailure: сервер вернул сообщение: 401 — не санкционировано|Exchange Online|Неверное имя пользователя или пароль|Проверьте правильность имени пользователя и пароля, а затем выполните процедуру подключения Exchange Online к Cloud App Security снова.|
> |HttpRequestFailure: сервер вернул сообщение: 404 — не найдено|Exchange Online|Учетная запись, которую вы используете для входа в Exchange Online, не имеет основного почтового ящика в Exchange Online (это может быть, например, пользователь, которого нет в Azure AD или который имеется в Azure AD, но у которого нет лицензии Exchange Online).|Выполните процедуру подключения Exchange Online к Cloud App Security снова, используя новую учетную запись администратора.|
> |NullPointerException|AWS|Внутренняя ошибка|Обратитесь в службу поддержки.|
> |HttpRequestFailure: сервер вернул сообщение: 500 — внутренняя ошибка сервера|Все приложения|В приложении произошла ошибка.|Проверьте состояние приложения|
> |Время ожидания службы истекло|Все приложения|Истекло время ожидания подключения между Cloud App Security и приложением. Это может быть вызвано проблемой с приложением.|Повторите попытку позднее.|

## <a name="see-also"></a>См. также  
[Ежедневные мероприятия для защиты облачной среды](daily-activities-to-protect-your-cloud-environment.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  

