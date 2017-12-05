---
title: "Устранение неполадок с политиками Cloud App Security | Microsoft Docs"
description: "Этот раздел описывает процесс устранения неполадок с созданием политик в Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 29/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 828cc94a-248b-44f6-a1ba-c28c0a135f8c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6c8cbfa8899a6cfa66f6fc2a9ec9ff75375acecb
ms.sourcegitcommit: f4ec7f2cb81c9d83bb7f406ddcca91ab07790a98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-cloud-app-security-policies"></a>Устранение неполадок с политиками Cloud App Security

|Ошибка|Описание|Разрешение|
|----|----|----|
| **Политика <policy name> была автоматически отключена из-за ошибки конфигурации.**|Если вы получаете в Cloud App Security эту ошибку, необходимо исправить конфигурацию названной политики. При создании политики Cloud App Security вы часто используете другие объекты, созданные в Cloud App Security, например теги или фильтры диапазонов IP-адресов. Если используемый тег или диапазон IP-адресов в политике впоследствии удаляется, политика будет автоматически отключена и вы получите эту ошибку. |Чтобы восстановить политику, измените ее, исключив все удаленные объекты из ее фильтров, и сохраните политику.|



## <a name="see-also"></a>См. также
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)
[Вы можете получить техническую поддержку на странице технической поддержки Cloud App Security](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)

