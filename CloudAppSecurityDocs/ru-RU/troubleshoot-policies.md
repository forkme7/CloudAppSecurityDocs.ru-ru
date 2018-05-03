---
title: Устранение неполадок с политиками Cloud App Security | Microsoft Docs
description: Этот раздел описывает процесс устранения неполадок с созданием политик в Cloud App Security.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 828cc94a-248b-44f6-a1ba-c28c0a135f8c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9bfc880cdaa0bf87abfd2b3b34cdf647a4aa1aaf
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*


# <a name="troubleshooting-microsoft-cloud-app-security-policies"></a>Устранение неполадок с политиками Microsoft Cloud App Security

|Ошибка|Описание|Разрешение|
|----|----|----|
| **Политика <policy name> была автоматически отключена из-за ошибки конфигурации.**|Если вы получаете в Microsoft Cloud App Security эту ошибку, необходимо исправить конфигурацию названной политики. При создании политики Microsoft Cloud App Security вы часто используете другие объекты, созданные в Microsoft Cloud App Security, например теги или фильтры диапазонов IP-адресов. Если используемый тег или диапазон IP-адресов в политике впоследствии удаляется, политика будет автоматически отключена и вы получите эту ошибку. |Чтобы восстановить политику, измените ее, исключив все удаленные объекты из ее фильтров, и сохраните политику.|



## <a name="see-also"></a>См. также
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)

