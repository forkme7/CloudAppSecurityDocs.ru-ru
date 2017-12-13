---
title: "Интеграция SIEM с Cloud App Security | Microsoft Docs"
description: "В этой статье представлена информация об интеграции SIEM с Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4649423b-9289-49b7-8b60-04b61eca1364
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 2acabcc195b8496f0a9bda812cc11b289911b81a
ms.sourcegitcommit: 2e89f41bc2581859a24d55b700dcd89e70e730a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2017
---
# <a name="siem-integration"></a>Интеграция SIEM
    
Теперь вы можете интегрировать Cloud App Security со своим сервером SIEM и получить централизованный мониторинг оповещений и действий в подключенных приложениях. По мере того как подключенные приложения начинают поддерживать новые действия и события, в Cloud App Security появляется поддержка их мониторинга. Интеграция со службой SIEM позволяет повысить степень защищенности облачных приложений без изменения обычного рабочего процесса обеспечения безопасности путем автоматизации процедуры системы безопасности и установления взаимосвязей между действиями в облаке и локальной среде. Агент SIEM Cloud App Security работает на сервере, запрашивает оповещения и действия от Cloud App Security и передает их на сервер SIEM.

При первой интеграции SIEM с Cloud App Security в SIEM будут перенаправлены действия и оповещения за последние два дня, а также все последующие действия и оповещения в зависимости от выбранного вами фильтра. Кроме того, если вы отключите эту функцию на длительное время, то при повторном включении будут перенаправлены действия и оповещения за последние два дня и все последующие.

## <a name="siem-integration-architecture"></a>Архитектура интеграции SIEM

Агент SIEM развертывается в сети организации. При развертывании и настройке он запрашивает типы данных (оповещения и действия), настроенные с помощью интерфейсов RESTful API Cloud App Security.
После этого трафик отправляется через зашифрованный HTTPS-канал на порту 443.

После получения данных из Cloud App Security агент SIEM отправляет сообщения системного журнала в локальную среду SIEM с помощью сетевой конфигурации, указанной во время установки (TCP или UDP с настраиваемым портом). 

![Архитектура интеграции SIEM](./media/siem-architecture.png)

## <a name="supported-siems"></a>Поддерживаемые системы SIEM

Сейчас Cloud App Security поддерживает платформу Micro Focus ArcSight и общий формат CEF.

## <a name="how-to-integrate"></a>Интеграция

Интеграция SIEM выполняется в три этапа:
1. Настройка SIEM на портале Cloud App Security. 
2. Скачивание JAR-файла и его запуск на сервере.
3. Проверка работы агента SIEM.

### <a name="prerequisites"></a>Предварительные условия

- Стандартный сервер с Windows или Linux (можно использовать виртуальную машину).
- На сервере должна быть запущена Java 8; более ранние версии не поддерживаются.

## <a name="integrating-with-your-siem"></a>Интеграция SIEM

### <a name="step-1-set-it-up-in-the-cloud-app-security-portal"></a>Шаг 1: настройка SIEM на портале Cloud App Security

1. На портале Cloud App Security под шестеренкой "Параметры" щелкните **Расширения безопасности** и откройте вкладку **Агенты SIEM**.

2. Щелкните значок "плюс", чтобы запустить мастер **Добавить агент SIEM**.
3. В окне мастера нажмите кнопку **Запустить мастер**.   
4. В окне мастера введите название и **выберите формат SIEM**, а также укажите любые **дополнительные параметры** для этого формата. Нажмите кнопку **Далее**.

   ![Общие параметры SIEM](./media/siem1.png)

5. Введите IP-адрес или имя **узла с удаленным системным журналом** и **номер порта для системного журнала**. Выберите TCP или UDP в качестве протокола для удаленного системного журнала.
Если у вас нет этих данных, их можно получить у вашего администратора по безопасности.
Нажмите кнопку **Далее**.

  ![Параметры удаленного системного журнала](./media/siem2.png)

6. Выберите типы данных, **оповещения** и **действия**, которые нужно экспортировать на сервер SIEM. Включите или отключите их при помощи ползунка. По умолчанию выбраны все типы. Для отправки только определенных типов оповещений и действий на сервер SIEM можно воспользоваться фильтрами из раскрывающегося списка **Apply to** (Применить к).
Чтобы проверить правильность работы фильтра, можно нажать кнопку **Edit and preview results** (Изменить и показать результаты). Нажмите кнопку **Далее**. 

  ![Параметры типов данных](./media/siem3.png)

7. Скопируйте токен и сохраните его для последующего использования. После нажатия кнопки "Готово" и завершения работы мастера агент SIEM, добавленный в таблице, отобразится на странице SIEM. Этот агент будет иметь состояние **Created** (Создан). Впоследствии он будет подключен.

### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a>Шаг 2: скачивание JAR-файла и его запуск на сервере

1. В [Центре загрузки Майкрософт](https://go.microsoft.com/fwlink/?linkid=838596) примите [условия лицензии](https://go.microsoft.com/fwlink/?linkid=862491), скачайте ZIP-файл и распакуйте его.

2. Запустите извлеченный файл на сервере.
    
        java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN

> [!NOTE]
> - Имя файла зависит от версии агента SIEM.
> - Параметры в квадратных скобках [] необязательные; их следует использовать только при необходимости.
> - Рекомендуется выполнять JAR во время запуска сервера.
>   - Windows. Реализуйте выполнение в рамках запланированной задачи и убедитесь, что для задачи задан параметр **Выполнять вне зависимости от регистрации пользователя** и снят флажок **Останавливать задачу, выполняемую дольше**.
>   - Linux. Добавьте команду выполнения с **&** в файл rc.local. Пример: `java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &`

Где используются следующие переменные:
- DIRNAME — это путь к каталогу, который вы хотите использовать для журналов отладки локального агента.
- Адрес[:порт] — адрес прокси-сервера и порт, которые сервер использует для подключения к Интернету.
- Токен — токен агента SIEM, скопированный на предыдущем шаге.

Чтобы получить справку, введите -h. Эта команда доступна всегда.

Вот примеры журналов действий, отправляемых в службу SIEM:
```
2017-11-22T17:50:04.000Z CEF:0|MCAS|SIEM_Agent|0.111.85|EVENT_CATEGORY_LOGOUT|Log out|0|externalId=1511373015679_167ae3eb-ed33-454a-b548-c2ed6cea6ef0 rt=1511373004000 start=1511373004000 end=1511373004000 msg=Log out suser=admin@contoso.com destinationServiceName=ServiceNow dvc=13.82.149.151 requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511373015679_167ae3eb-ed33-454a-b548-c2ed6cea6ef0,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:40:15.000Z CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_VIEW_REPORT|View report|0|externalId=1511898027370_e272cd5f-31a3-48e3-8a6a-0490c042950a rt=1511898015000 start=1511898015000 end=1511898015000 msg=View report: ServiceNow Report 23 suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511898027370_e272cd5f-31a3-48e3-8a6a-0490c042950a,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=23,sys_report,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:25:34.000Z CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_DELETE_OBJECT|Delete object|0|externalId=1511897141625_7558b33f-218c-40ff-be5d-47d2bdd6b798 rt=1511897134000 start=1511897134000 end=1511897134000 msg=Delete object: ServiceNow Object f5122008db360300906ff34ebf96198a suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511897141625_7558b33f-218c-40ff-be5d-47d2bdd6b798,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-27T20:40:14.000Z CEF:0|MCAS|SIEM_Agent|0.112.49|EVENT_CATEGORY_CREATE_USER|Create user|0|externalId=1511815215873_824f8f8d-2ecd-439b-98b1-99a1adf7ba1c rt=1511815214000 start=1511815214000 end=1511815214000 msg=Create user: user 747518c0db360300906ff34ebf96197c suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511815215873_824f8f8d-2ecd-439b-98b1-99a1adf7ba1c,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,747518c0db360300906ff34ebf96197c,sys_user,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-27T20:41:20.000Z CEF:0|MCAS|SIEM_Agent|0.112.49|EVENT_CATEGORY_DELETE_USER|Delete user|0|externalId=1511815287798_bcf60601-ecef-4207-beda-3d2b8d87d383 rt=1511815280000 start=1511815280000 end=1511815280000 msg=Delete user: user 233490c0db360300906ff34ebf9619ef suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511815287798_bcf60601-ecef-4207-beda-3d2b8d87d383,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,233490c0db360300906ff34ebf9619ef,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:24:55.000Z LAB-EUW-ARCTEST CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_DELETE_OBJECT|Delete object|0|externalId=1511897117617_5be018ee-f676-4473-a9b5-5982527409be rt=1511897095000 start=1511897095000 end=1511897095000 msg=Delete object: ServiceNow Object b1709c40db360300906ff34ebf961923 suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511897117617_5be018ee-f676-4473-a9b5-5982527409be,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

```
А вот пример файла журнала оповещений:
```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=

```
#### <a name="sample-cloud-app-security-alerts-in-cef-format"></a>Пример оповещения Cloud App Security в формате CEF


##### <a name="activity-logs"></a>Журналы действий

-   EVENT_CATEGORY_* — категория действий высокого уровня.

-   <ACTION> — тип действия, который отображается на портале.

-   externalId — идентификатор события.

-   start — метка времени действия.

-   end — метка времени действия.

-   rt — метка времени действия.

-   msg — описание события, которое отображается на портале.

-   suser — пользователь действия.

-   destinationServiceName — приложение происхождения действия, например, Office 365, Sharepoint, Box.

-   dvc — IP-адрес клиентского устройства.

-   requestClientApplication — агент пользователя клиентского устройства.

-   cs<X>Label — у каждой метки есть свое значение, и сама метка объясняет его, например targetObjects.

-   cs<X> — сведения, относящиеся к метке (целевой пользователь действия или оповещение для примера метки).

##### <a name="alerts"></a>Оповещения

-   <alert type> — например, “ALERT_CABINET_EVENT_MATCH_AUDIT”.

-   <name>— имя соответствующей политики.

-   externalId — идентификатор оповещения.

-   start — метка времени оповещения.

-   end – метка времени оповещения.

-   rt — метка времени оповещения.

-   msg — описание оповещения, которое отображается на портале.

-   suser — пользователь темы оповещения.

-   destinationServiceName — приложение происхождения оповещения, например, Office 365, Sharepoint, Box.

-   cs<X>Label — у каждой метки есть свое значение, и сама метка объясняет его, например targetObjects.

-   cs<X> — сведения, относящиеся к метке (целевой пользователь действия или оповещение для примера метки).


### <a name="step-3-validate-that-the-siem-agent-is-working"></a>Шаг 3: проверка работы агента SIEM

1. Убедитесь, что агент SIEM на портале Cloud App Security не находится в состоянии **Ошибка подключения** или **Отключен** и что оповещения для этого агента отсутствуют. Состояние **Ошибка подключения** возникает, если подключение отсутствует более двух часов, а состояние **Отключен** возникает, если подключение отсутствует более 12 часов.
 ![SIEM disconnected](./media/siem-not-connected.png) (SIEM отключен)
 
   Должно отображаться состояние "Подключено", как показано на этом снимке экрана: ![Служба SIEM подключена](./media/siem-connected.png)

2. Убедитесь, что на сервере с системными журналами или сервере SIEM отображаются действия и оповещения, поступающие от Cloud App Security.


## <a name="regenerating-your-token"></a>Повторное создание токена
При утере токена его всегда можно создать повторно, щелкнув многоточие в конце строки агента SIEM в таблице и выбрав **Regenerate token** (Создать маркер повторно).

 ![SIEM — повторное создание токена](./media/siem-regenerate-token.png)

## <a name="editing-your-siem-agent"></a>Изменение агента SIEM 
Если в будущем потребуется изменить агент SIEM, щелкните многоточие в конце строки агента SIEM в таблице и выберите **Edit** (Изменить). При изменении агента SIEM повторно запускать JAR-файл не нужно, он будет обновлен автоматически.

![SIEM — изменение](./media/siem-edit.png)

## <a name="deleting-your-siem-agent"></a>Удаление агента SIEM
Если нужно удалить агент SIEM, щелкните многоточие в конце строки агента SIEM в таблице и выберите **Delete** (Удалить).

![SIEM — удаление](./media/siem-delete.png)

> [!NOTE]
> Этот компонент доступен в виде общедоступной предварительной версии.

## <a name="high-availability-options"></a>Способы обеспечения высокой доступности

Агент SIEM — это единая конечная точка, которая поддерживает восстановление при простое до двух дней. Высокий уровень доступности можно также обеспечить, используя в качестве конечной точки клиента подсистему балансировки нагрузки.

## <a name="see-also"></a>См. также  
[Устранение неполадок интеграции SIEM](troubleshooting-siem.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  