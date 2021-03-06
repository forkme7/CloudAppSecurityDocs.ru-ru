---
title: Настройка автоматической отправки журналов для непрерывных отчетов | Документы Майкрософт
description: Из этой статьи вы узнаете, как настроить автоматическую отправку журналов для непрерывных отчетов в Cloud App Security.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2017
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: c75ba963-ad5a-48e6-8d5d-610fc6e0b990
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: a55e0ff02d16af8b166b62a53fbcffb62d6dcc08
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*


# <a name="configure-automatic-log-upload-for-continuous-reports"></a>Настройка автоматической отправки журналов для непрерывных отчетов


Сборщики журналируемых данных позволяют легко автоматизировать отправку журналов из сети. Сборщик журналируемых данных выполняется в сети и получает журналы через Syslog или FTP. Каждый журнал автоматически обрабатывается, сжимается и передается на портал. При использовании FTP журналы отправляются в Microsoft Cloud App Security после завершения передачи файла по FTP в сборщик журналируемых данных.  При использовании Syslog сборщик журналируемых данных записывает получаемые журналы на диск и отправляет файл в Cloud App Security, если размер файла превышает 40 КБ.

После отправки журнала в Cloud App Security он перемещается в каталог резервного копирования, где всегда хранится по меньшей мере 20 последних журналов. При поступлении новых журналов старые удаляются. Когда у сборщика журналируемых данных заканчивается свободное место, он удаляет новые журналы до высвобождения места на диске. В этом случае вы увидите предупреждение на вкладке **Сборщики журналируемых данных** в параметрах **Отправлять журналы автоматически**.

Перед настройкой автоматического сбора файлов журнала проверьте, соответствует ли журнал требуемому типу. В противном случае службе Cloud App Security не удастся проанализировать файл.

> [!NOTE]
>-  Cloud App Security предоставляет поддержку для перенаправления журналов с сервера SIEM в сборщик журналируемых данных, предполагая, чтобы журналы перенаправляются в исходном формате. Но настоятельно рекомендуется непосредственно интегрировать сборщик журналируемых данных с вашим брандмауэром и прокси-сервером.
>- Сборщик журналируемых данных сжимает данные перед отправкой. Исходящий трафик сборщика журналируемых данных составляет 10 % от размера журналов трафика, которые он получает. 

## <a name="deployment-modes"></a>Режимы развертывания

Сборщик журналируемых данных поддерживает два режима развертывания:

-   **Контейнер**: выполняется в виде образа Docker в [локальной среде Ubuntu](discovery-docker-ubuntu.md), в [Ubuntu на Azure](discovery-docker-ubuntu-azure.md) или в [локальной среде RHEL](discovery-docker-ubuntu.md). 

-   **Виртуальное устройство**: [работает в виде образа через гипервизор Hyper-V или VMware.](configure-automatic-log-upload-for-continuous-reports.md)




## <a name="see-also"></a>См. также статью
 
[Создание отчетов о снимках Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Работа с данными Cloud Discovery](working-with-cloud-discovery-data.md)

