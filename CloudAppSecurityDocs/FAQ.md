---
title: "Часто задаваемые о Cloud App Security вопросы | Microsoft Docs"
description: "В этой статье приводятся ответы на часто задаваемые вопросы о Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 081c2cf4-2750-4546-9490-4b65e87ae48c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: acc80f823431f5f903412b8e984683a3e8f62d34
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2018
---
# <a name="frequently-asked-questions"></a>Вопросы и ответы

## <a name="what-kind-of-permissions-do-i-need-to-have-in-order-to-access-cloud-app-security"></a>Какие разрешения требуются для получения доступа к Cloud App Security?

Необходимы права глобального администратора, администратора соответствия требованиям или администратора безопасности в Azure Active Directory. Недостаточно просто иметь эти роли в Центре безопасности и соответствия требованиям Office 365.
Чтобы назначить пользователя в качестве глобального администратора, администратора соответствия требованиям или администратора безопасности в Azure Active Directory, выполните следующее в Windows PowerShell:

        $cred = Get-Credential
        Connect-MsolService -credential $cred
        Add-MsolRoleMember -RoleName "Compliance Administrator" -RoleMemberEmailAddress "XX@XX.XX"
 или Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress XX@XX.XX

## <a name="see-also"></a>См. также статью  
Сведения об использовании и настройке политик для управления применением облачных приложений см. в разделе [Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md).   

Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на [портале Premier](https://premier.microsoft.com/).  
