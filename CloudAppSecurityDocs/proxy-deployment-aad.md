---
title: "Развертывание прокси-сервера Cloud App Security для Azure AD | Документация Майкрософт"
description: "В этой статье объясняется, как развернуть прокси-сервер Cloud App Security для приложений Azure AD."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/10/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2490c5e5-e723-4fc2-a5e0-d0a3a7d01fc2
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 58b309ddcc893d47a8adc89e9b286eff97ec99ed
ms.sourcegitcommit: 4cf65f627f2d370ee4a4decae1acbb9658874056
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2017
---
# <a name="deploying-the-cloud-app-security-proxy-for-azure-ad"></a>Развертывание прокси-сервера Cloud App Security для Azure AD

> [!NOTE]
> Мы настоятельно рекомендуем установить прокси-сервер в песочнице или в среде тестирования, прежде чем устанавливать его в рабочей среде.

Выполните описанные ниже действия, чтобы развернуть прокси-сервер Cloud App Security и включить управление доступом и сеансом.


## <a name="step-1-create-an-azure-ad-conditional-access-policy"></a>Шаг 1. Создание политики условного доступа Azure AD

1. В Azure Active Directory в разделе **Безопасность** щелкните **Условный доступ**.

 ![Условный доступ Azure AD](./media/conditional-access.png)

2. Щелкните **Создать политику** и создайте политику, выбрав в разделе **Сеанс** значение **Использовать ограничения, применяемые прокси-сервером**.

## <a name="step-2-log-on-to-each-app"></a>Шаг 2. Вход в каждое приложение

С помощью учетных данных войдите в каждое приложение, которым необходимо управлять с помощью прокси-сервера.

## <a name="step-3-add-the-apps-in-cloud-app-security"></a>Шаг 3. Добавление приложений в Cloud App Security

1.  На портале Cloud App Security щелкните значок шестеренки "Параметры" и выберите пункт **Прокси-сервер**.

2. В таблице должны появиться приложения, в которые вы выполнили вход. 

3. Для каждого приложения щелкните значок с многоточием в правом углу строки таблицы, а затем щелкните **Продолжить установку**.

4. В мастере прокси-сервера нажмите кнопку **Готово**.


Через несколько минут все запросы на вход в приложение будут направляться через прокси-сервер Cloud App Security. 

## <a name="test-the-configuration"></a>Проверка конфигурации

1.  Попытайтесь войти в приложение. Если войти не удалось, убедитесь, что в мастере прокси-сервера все шаги выполнены правильно. 

2.  На портале Cloud App Security в разделе **Сведения** выберите **Журнал действий** и проверьте, регистрируются ли на прокси-сервере события **единого входа**.



## <a name="see-also"></a>См. также  
[Работа с прокси-сервером Cloud App Security](proxy-intro.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  