---
title: "Часто задаваемые о Cloud App Security вопросы | Microsoft Docs"
description: "В этой статье приводятся ответы на часто задаваемые вопросы о Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/23/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 081c2cf4-2750-4546-9490-4b65e87ae48c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 92ad2a378b0ab0f127ef22c9746f2957f43576a8
ms.sourcegitcommit: 355226ee21981563066d637e7db0bff0d53c2da6
translationtype: HT
---
# <a name="frequently-asked-questions"></a>Вопросы и ответы

## <a name="what-kind-of-permissions-do-i-need-to-have-in-order-to-access-cloud-app-security"></a>Какие разрешения требуются для получения доступа к Cloud App Security?

Необходимы права глобального администратора, администратора соответствия требованиям или администратора безопасности в Azure Active Directory. Недостаточно просто иметь эти роли в Центре безопасности и соответствия требованиям Office 365.
Чтобы назначить пользователя в качестве глобального администратора, администратора соответствия требованиям или администратора безопасности в Azure Active Directory, выполните следующее в Windows PowerShell:

        $cred = Get-Credential
        Connect-MsolService -credential $cred
        Add-MsolRoleMember -RoleName "Compliance Administrator" -RoleMemberEmailAddress "XX@XX.XX"
 или Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress “XX@XX.XX”

## <a name="see-also"></a>См. также:  
Сведения об использовании и настройке политик для управления применением облачных приложений см. в разделе [Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md).   
Для получения технической поддержки перейдите на страницу [Служба технической поддержки Cloud App Security](http://support.microsoft.com/oas/default.aspx?prid=16031).   
Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на [портале Premier](https://premier.microsoft.com/).  
