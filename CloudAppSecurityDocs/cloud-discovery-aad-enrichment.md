---
title: "Обогащение данных обнаружения Cloud App Security с помощью имен пользователей Azure AD | Документы Майкрософт"
description: "Эта статья рассказывает об обогащении данных обнаружения Cloud App Security с помощью имен пользователей Azure AD."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/19/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 45295c2c-3e4d-4482-bf95-2e47072f9236
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 909fa75c48fb9c698d083f2fb85f5f53bfadf76c
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2017
---
# <a name="cloud-discovery-enrichment"></a>Обогащение Cloud Discovery

Данные Cloud Discovery теперь можно дополнять сведениями об именах пользователей из Azure Active Directory. При включении этой функции имя пользователя, полученное в журналах трафика обнаружения, будет сопоставляться с именем пользователя в Azure AD и заменяться им, что дает указанные ниже возможности.
-   Вы можете изучать использование теневых ИТ отдельными пользователями Azure Active Directory.
-   Вы можете сопоставлять использование обнаруженного облачного приложения с собранными действиями API.
-   Затем вы можете создавать пользовательские журналы на основе групп пользователей в Azure AD. Например, можно составить отчет по теневым ИТ для отдела маркетинга.


## <a name="prerequisites"></a>Необходимые условия:
- Источник данных должен предоставлять сведения об именах пользователей.
- Должен быть подключен соединитель приложений Office 365.

## <a name="enabling-user-data-enrichment"></a>Обеспечение обогащения данных пользователя 
    
1. В меню шестеренки "Параметры" выберите **Cloud Discovery settings** (Параметры Cloud Discovery).
     
2. Чтобы разрешить Cloud App Security по умолчанию использовать данные Azure Active Directory для обогащения сведений о пользователях, на вкладке **Обогащение пользователей** выберите **Добавлять к идентификаторам обнаруженных пользователей имена пользователей Azure Active Directory**.

3. Нажмите кнопку **Сохранить**.
 
![Обогащение обнаружения Cloud App Security с помощью имен пользователей Azure AD](./media/discovery-enrichment.png)
  

  
      
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
    
      
  