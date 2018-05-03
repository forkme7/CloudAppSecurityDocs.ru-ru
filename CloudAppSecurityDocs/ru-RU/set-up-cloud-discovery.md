---
title: Развертывание Cloud Discovery с Microsoft Cloud App Security | Документы Майкрософт
description: В этом разделе описывается процедура настройки для запуска Cloud Discovery.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2017
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 3daf04f3caa2541bacafe6be33c7f9714b1dda71
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*


# <a name="set-up-cloud-discovery"></a>Настройка Cloud Discovery
Cloud Discovery анализирует журналы трафика на основе каталога облачных приложений Microsoft Cloud App Security, включающего более 15 000 приложений, которые оцениваются по более чем 60 факторов риска. Это обеспечивает непрерывный контроль использования облачной среды, теневых ИТ-ресурсов и риска, который эти ресурсы представляют для организации.

## <a name="snapshot-and-continuous-risk-assessment-reports"></a>Отчеты о снимках и непрерывной оценке рисков 

Вы можете создавать отчеты двух типов. 
- **Отчеты о снимках** позволяют динамически контролировать набор журналов трафика, которые вы отправляете вручную из брандмауэров и с прокси-серверов.

- **Непрерывные отчеты** служат для анализа всех журналов, которые пересылаются из вашей сети с помощью сборщика журналируемых данных Cloud App Security. Они позволяют лучше контролировать все данные и автоматически определять случаи аномального использования с помощью либо подсистемы обнаружения аномалий на основе машинного обучения, либо определенных вами политик.

## <a name="log-process-flow-from-raw-data-to-risk-assessment"></a>Процедура обработки журналов: от необработанных данных к оценке рисков  
Анализ рисков включает следующие этапы и занимает от нескольких минут до нескольких часов в зависимости от объема данных.  

-   **Отправка** — веб-журналы трафика из сети передаются на портал.  

-   **Синтаксический анализ** — Cloud App Security выполняет анализ данных трафика и их извлечение из журналов с помощью специального средства синтаксического анализа для каждого источника данных.  

-   **Анализ** — данные трафика анализируются с использованием каталога облачных приложений, позволяющего определить более 15 000 облачных приложений и оценить их риски. Во время анализа также определяются активные пользователи и IP-адреса.  

-   **Создание отчета** — отчет оценки рисков создается на основе данных, извлеченных из файлов журналов.   


>[!NOTE]
>- Данные непрерывных отчетов анализируются два раза в день.
>- Сборщик журналируемых данных сжимает данные перед отправкой. Исходящий трафик сборщика журналируемых данных составляет 10 % от размера журналов трафика, которые он получает. 

## <a name="using-traffic-logs-for-cloud-discovery"></a>Использование журналов трафика для Cloud Discovery
Служба Cloud Discovery использует данные из ваших журналов трафика. Чем подробнее журнал, тем выше уровень контроля. Службе Cloud Discovery требуются данные веб-трафика со следующими атрибутами:
- Дата транзакции
- Исходный IP-адрес
- Исходный пользователь — настоятельно рекомендуется
- IP-адрес назначения
- URL-адрес назначения **рекомендуется** (URL-адреса обеспечивают более точное обнаружение облачных приложений, чем IP-адреса)
- Общий объем данных (информация о данных крайне важна)
- Объем отправленных или скачанных данных (позволяет выявлять закономерности в использовании облачных приложений)
- Выполненное действие (разрешено или заблокировано)

Служба Cloud Discovery не может выводить или анализировать атрибуты, которые не включены в ваши журналы.
Например, журнал стандартного формата **брандмауэра Cisco ASA** не содержит атрибуты **Количество отправленных байт на транзакцию** и **Имя пользователя**, а также атрибут **Целевой URL-адрес** (имеется только целевой IP-адрес).
Следовательно, эти атрибуты не будут отображаться в данных Cloud Discovery для этих журналов и видимость облачных приложений будет ограниченна. Для брандмауэров Cisco ASA необходимо задать уровень информации 6. 


Для успешного создания отчета Cloud Discovery журналы трафика должны соответствовать указанным ниже условиям.
1.  Источник данных поддерживается (см. список ниже).
2.  Формат журнала соответствует требуемому стандартному формату (проверяется средством работы с журналами при отправке).
3.  Возраст событий не превышает 90 дней.
4.  Файл журнала является допустимым и содержит информацию об исходящем трафике.



## Поддерживаемые брандмауэры и прокси-серверы <a name="supported-firewalls-and-proxies"></a>

- Barracuda — брандмауэр веб-приложений (W3C)
- Blue Coat Proxy SG — журнал доступа (W3C)
- Check Point
- Брандмауэр Cisco ASA Firewall (для брандмауэров Cisco ASA необходимо задать уровень информации 6)
- Cisco Active Server Application с FirePOWER
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Meraki — журнал URL-адресов
- Clavister NGFW (системный журнал)
- Dell Sonicwall
- Digital Arts i-FILTER
- Fortinet Fortigate
- Juniper SRX
- Juniper SSG
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Palo Alto series Firewall
- Sophos SG
- Sophos Cyberoam
- Squid (Common)
- Squid (Native)
- Websense — Web Security Solutions — подробный аналитический отчет (CSV)
- Websense — Web Security Solutions — журнал интернет-активности (CEF)
- Zscaler

> [!NOTE]
> Cloud Discovery поддерживает адреса IPv4 и IPv6.

Если ваш журнал не поддерживается, выберите **Другой** в качестве **источника данных** и укажите устройство и журнал, который вы пытаетесь отправить. Ваш журнал будет проверен группой аналитиков Cloud App Security, и вам сообщат, добавлена ли поддержка его типа. Также можно определить пользовательское средство синтаксического анализа, которое соответствует вашему формату. Дополнительные сведения см. в статье [Использование настраиваемого средства синтаксического анализа журналов](custom-log-parser.md).


Атрибуты данных (в соответствии с документацией поставщика):


|                 Источник данных                  |    Целевой URL-адрес приложения    |    Целевой IP-адрес приложения     |       Имя пользователя       |      Исходный IP-адрес       |    Общий объем трафика     |    Отправлено байтов    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |          Нет          |          Нет          |
|                  Blue Coat                   | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                  Контрольная точка                  |          Нет          | <strong>Да</strong> |          Нет          | <strong>Да</strong> |          Нет          |          Нет          |
|              Cisco ASA (Syslog)              |          Нет          | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> |          Нет          |
|           Cisco Active Server Application с FirePOWER           | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                  Cisco FWSM                  |          Нет          | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> |          Нет          |
|              Cisco Ironport WSA              | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                 Cisco Meraki                 | <strong>Да</strong> | <strong>Да</strong> |          Нет          | <strong>Да</strong> |          Нет          |          Нет          |
|           Clavister NGFW (системный журнал)            | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                Dell SonicWall                | <strong>Да</strong> | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|            Digital Arts i-FILTER             | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                  Fortigate                   |          Нет          | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                 Juniper SRX                  |          Нет          | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                 Juniper SSG                  |          Нет          | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                  McAfee SWG                  | <strong>Да</strong> |          Нет          |          Нет          | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                    MS TMG                    | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|              Palo Alto Networks              |          Нет          | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                    Sophos                    | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |          Нет          |
|                Squid (Common)                | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> |          Нет          | <strong>Да</strong> |
|                Squid (Native)                | <strong>Да</strong> |          Нет          | <strong>Да</strong> | <strong>Да</strong> |          Нет          | <strong>Да</strong> |
| Websense — анализ подробного отчета (CSV) | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|    Websense — журнал действий в Интернете (CEF)    | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |
|                   Zscaler                    | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> | <strong>Да</strong> |

## <a name="see-also"></a>См. также статью

[Создание отчетов о снимках Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Настройка автоматической отправки журналов для непрерывных отчетов](configure-automatic-log-upload-for-continuous-reports.md)

[Работа с данными Cloud Discovery](working-with-cloud-discovery-data.md)