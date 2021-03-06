---
title: "Управление токенами API в Cloud App Security | Документы Майкрософт"
description: "Этот раздел содержит сведения о создании токенов API для Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4f5e6b1e-6b2c-4358-98f0-945e2993d5fe
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: a7ae478fcd85bdb16a1783886f274a8ab81462bb
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2018
---
# <a name="api-tokens"></a>Токены API
    
API Cloud App Security обеспечивает программный доступ к Cloud App Security через конечные точки REST API. Приложения могут использовать этот API, чтобы выполнять операции чтения и изменения данных и объектов в Cloud App Security. Например, API Cloud App Security поддерживает следующие распространенные операции для объекта-пользователя:

- отправка файлов журнала для Cloud Discovery;
- создание скриптов блокировки;
- список действий, оповещения и отчеты о политиках;
- закрытие и разрешение оповещений.

Чтобы просмотреть полную документацию по API, на портале Cloud App Security перейдите в меню "Справка" > **Документация по API**.

Чтобы получить доступ к API, нужно создать токен API и использовать его в программном обеспечении для подключения к API Cloud App Security.

Вкладка "Токены API" позволяет управлять всеми токенами API клиента. 


## <a name="generate-a-token"></a>Создание токена

1. В меню **Параметры** последовательно выберите пункты **Расширения безопасности** и **Токены API**.

2. Щелкните значок "плюс", выберите **Создать новый токен**, укажите имя, по которому сможете найти токен в будущем, и нажмите кнопку **Далее**.
![Создание токена API в Cloud App Security](./media/api-token-gen.png)

3. Скопируйте значение токена и сохраните его на случай восстановления. Если вы его потеряете, вам нужно будет создать токен заново. На токен распространяются права выдавшего его пользователя. Например, читатель безопасности не может выдать токен, способный изменять данные.

4. Токены можно фильтровать по состоянию: "Активный", "Неактивный" или "Созданный". 

  - Состояние "Созданный" имеют токены, которые никогда не использовались. 
  - Состояние "Активный" имеют токены, которые были созданы и использовались в течение предыдущих 7 дней. 
  - Состояние "Неактивный" имеют токены, которые использовались ранее, но не применялись в течение последних 7 дней.
5. После создания токена вы получите новый URL-адрес для доступа к порталу Cloud App Security. 

 ![Токен API Cloud App Security](./media/generate-api-token.png)

Универсальный URL-адрес портала продолжает работать, но значительно медленнее, чем пользовательский URL-адрес с токеном. Если вы забыли URL-адрес, просмотрите ее, перейдя к значку **?** значок в меню и выбрав **О программе**.

## <a name="api-token-management"></a>Управление токенами API

Страница токенов API содержит таблицу всех созданных токенов API.

Администраторы со всеми правами видят все токены, созданные для этого клиента. Другие пользователи видят только созданные ими токены.

Таблица содержит сведения о времени создания и последнего использования токена, а также позволяет отменить токен. 

Отмененный токен удаляется из таблицы, а использовавшее его программное обеспечение не может вызывать API до предоставления нового токена. 

> [!NOTE]
> Соединители SIEM и сборщики журналируемых данных также используют токены API. Управление этими токенами осуществляется из разделов агентов SIEM и сборщиков, а не из этой таблицы. 





## <a name="see-also"></a>См. также  
[Устранение проблем, связанных с агентом SIEM](troubleshooting-siem.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  

## <a name="check-out-this-video"></a>Посмотрите это видео!
[Microsoft Cloud App Security — API REST и токены](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security--REST-APIs-and-Tokens)  