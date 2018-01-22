---
title: "Настройка портала Cloud App Security для получения наилучших результатов | Документы Майкрософт"
description: "В этой статье содержатся сведения о предоставлении данных об организации в Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5f9868fab58c1809b80aaa6b06a797c4e70e2e64
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2018
---
# <a name="basic-set-up"></a>Основная настройка
В следующей процедуре представлены инструкции по настройке портала Cloud App Security.

## <a name="prerequisites"></a>Предварительные условия 
Для доступа к порталу Cloud App Security в список разрешений брандмауэра необходимо добавить следующие IP-адреса:  
  
- 104.42.231.28  
  
> [!NOTE]  
>  Для получения обновлений при смене URL-адресов и IP-адресов, подпишитесь на RSS в соответствии с инструкциями из статьи [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) (Диапазоны URL- и IP-адресов Office 365).  
  
## <a name="set-up-the-portal"></a>Настройка портала  
  
1.  В строке меню на портале Cloud App Security щелкните значок параметров ![значок параметров](./media/settings-icon.png "значок параметров") и выберите пункт **Общие параметры**, чтобы настроить следующее:  
     
     ![общие параметры](./media/general-settings.png "общие параметры")  
  
3.  В разделе **Сведения об организации** важно указать значение в поле **Отображаемое имя организации**. Оно будет отображаться в сообщениях электронной почты и на веб-страницах, отправляемых из системы.  
  
4. Укажите **Имя среды** (клиент). Это особенно важно, если вы управляете несколькими клиентами.  
  
4. Кроме того, можно указать **Логотип**, который будет отображаться в уведомлениях электронной почты и веб-страницах, отправляемых из системы. Логотип должен быть PNG-файлом размером до 150x50 пикселей на прозрачном фоне.  

4.  Не забудьте задать список **Управляемые домены**. Это важный шаг, так как управляемые домены помогают Cloud App Security определить, какие пользователи являются внутренними, а какие — внешними, а также где разрешено или запрещено публиковать файлы для общего доступа. Это используется для отчетов, а также для оповещений.  
> [!NOTE] 
> - Пользователи, которые не настроены как внутренние, будут помечены как внешние, и их действия и файлы проверяться не будут.

5. При интеграции с Azure Information Protection см. сведения в разделе [Интеграция с Azure Information Protection](azip-integration.md). 
  
  
6.  Если вы захотите создать резервную копию параметров портала, воспользуйтесь этим экраном. Нажмите кнопку **Экспортировать параметры портала** для создания JSON-файла со всеми параметрами портала, включая правила политики, группы пользователей и диапазоны IP-адресов.  
  
       



> [!NOTE] 
> Если вы используете ExpressRoute, служба Cloud App Security развертывается в Azure и полностью интегрируется с [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Все взаимодействия с приложениями Cloud App Security и трафик, передаваемый в Cloud App Security, в том числе отправка журналов обнаружения, маршрутизируются через **открытый пиринг** ExpressRoute в целях снижения задержки, а также повышения производительности и безопасности. Со стороны клиента никаких действий по настройке не требуется.  
    Дополнительные сведения об открытом пиринге см. в статье [ExpressRoute circuits and routing domains](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/) (Цепи и домены маршрутизации ExpressRoute).  
    
## <a name="see-also"></a>См. также  
[Настройка Cloud Discovery](set-up-cloud-discovery.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  