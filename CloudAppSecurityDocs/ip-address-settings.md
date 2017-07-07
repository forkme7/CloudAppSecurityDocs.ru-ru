---
title: "Подключение приложений для расширения возможностей видимости и контроля с помощью Cloud App Security | Документы Майкрософт"
description: "В этой статье описывается процесс подключения приложений, используя соединители API, к приложениям в облачной среде организации."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/3/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7e718d77-aae7-4a3a-8421-5ba7cee7d67c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c8c9b63f4265876fc1de6a24c6576f917f9d2278
ms.sourcegitcommit: a0290ac2a662994f7771975ef6c20d0b47e9edd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2017
---
Для подключения Cloud App Security к вашей сети требуются указанные ниже адреса. 

## <a name="cloud-app-security-system-ip-addresses"></a>Системные IP-адреса Cloud App Security

Для подключения Cloud App Security к средам клиентов используются указанные ниже IP-адреса. Они необходимы при подключении по протоколу [ICAP](icap-stunnel.md) и с помощью соединителей с приложениями. Для некоторых приложений может потребоваться добавить перечисленные ниже IP-адреса в список разрешений, чтобы разрешить Cloud App Security сбор журналов и предоставить доступ для консоли Cloud App Security. В некоторых приложениях эти IP-адреса могут также использоваться для определения действий Cloud App Security, например в журналах аудита службы. 
  
-   Для журналов:  
  
    104.209.35.177  
  
    13.91.98.185
 
    40.118.211.172

    13.93.216.68

    13.91.61.249

    13.93.233.42

    13.64.196.27

    13.64.198.97

    13.64.199.41

    13.64.198.19
  
  
## <a name="cas-portal-url-and-ip-addresses"></a>URL-адрес и IP-адреса портала Cloud App Security

URL-адрес, порт 443 и IP-адреса Cloud App Security используются для доступа клиента к порталу, для подключения к интерфейсам API Cloud App Security, а также для сборщика журналируемых данных и агента SIEM. 
  
     104.42.231.28  

 
  
> [!NOTE]  
>  Для получения обновлений при смене URL-адресов и IP-адресов, подпишитесь на RSS в соответствии с инструкциями из статьи [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) (Диапазоны URL- и IP-адресов Office 365).  
  

  
## <a name="see-also"></a>См. также  
[Ежедневные мероприятия для защиты облачной среды](daily-activities-to-protect-your-cloud-environment.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  

   