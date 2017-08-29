---
title: "Требования к сети Cloud App Security | Microsoft Docs"
description: "В этом разделе указаны IP-адреса и порты, которые нужно открыть для работы с Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: dac230e191c7c2d8159a2f373e6ef939fdd841a4
ms.sourcegitcommit: c3fda43ef6fe0d15f0eb9ea23a6f245bad8c371b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2017
---
# <a name="network-requirements"></a>Сетевые требования

В этом разделе приводится список портов и IP-адресов, которые нужно добавить в список разрешений для работы с Cloud App Security. 


## <a name="portal-access"></a>Доступ к порталу

Для доступа к порталу Cloud App Security в список разрешений брандмауэра необходимо добавить следующие IP-адреса.  
  
104.42.231.28  


## <a name="app-connector-access"></a>Доступ к соединителю приложений

Для некоторых сторонних приложений, к которым обращается Cloud App Security, может потребоваться добавить перечисленные ниже IP-адреса в список разрешений, чтобы позволить Cloud App Security собирать журналы и предоставлять доступ для консоли Cloud App Security.  
  
104.209.35.177  
13.91.98.185 40.118.211.172 13.93.216.68 13.91.61.249 13.93.233.42 13.64.196.27 13.64.198.97 13.64.199.41 13.64.198.19

> [!NOTE]
>Вы можете увидеть эти IP-адреса в журналах действий поставщика, так как Cloud App Security выполняет с этих IP-адресов действия управления и проверки. 
  

## <a name="siem-agent-and-log-collector"></a>Агент SIEM и сборщик журналируемых данных

Чтобы позволить Cloud App Security подключаться к SIEM и запускать сборщик журналируемых данных, необходимо открыть

- исходящий порт 443 для 104.42.231.28

## <a name="external-dlp-integration"></a>Интеграция с внешней системой защиты от потери данных

Чтобы компонент Cloud App Security мог отправлять данные через защищенный туннель на сервер ICAP, откройте в брандмауэре сети периметра внешние IP-адреса, используемые Cloud App Security с номером динамического исходного порта. 

1.  Исходные адреса: они должны быть добавлены в список разрешений, как указано выше для сторонних приложений соединителя API.
2.  Исходный TCP-порт: динамический
3.  Конечные адреса: один или два IP-адреса для сервера stunnel, подключенного к внешнему серверу ICAP.
4.  TCP-порт назначения: как определено в сети

> [!NOTE] 
> По умолчанию порт stunnel имеет номер 11344. При необходимости его можно изменить, но при этом обязательно запишите новый номер порта.



  
## <a name="see-also"></a>См. также  
[Ежедневные мероприятия для защиты облачной среды](daily-activities-to-protect-your-cloud-environment.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  

   