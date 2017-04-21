---
title: "Подключение Office 365 к Cloud App Security для видимости и контроля использования | Документы Майкрософт"
description: "В этой статье приводятся сведения о подключении Office 365 к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a79bf393-0d2c-44b6-8dab-86c740fd7333
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f5dfdcb0d420434a66b73098d546e4de4a36f60e
ms.sourcegitcommit: 355226ee21981563066d637e7db0bff0d53c2da6
translationtype: HT
---
# <a name="connect-office-365-to-microsoft-cloud-app-security"></a>Подключение Office 365 к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи Microsoft Office 365 с помощью API соединителя приложений.  
  
  

## <a name="how-to-connect-office-365-to-cloud-app-security"></a>Порядок подключения Office 365 к Cloud App Security  
  
> [!NOTE]
>- Для подключения Office 365 к Cloud App Security требуется по крайней мере одна назначенная лицензия Office 365.
>-  Ведение журнала аудита действий администратора Exchange, которое включено по умолчанию в Office 365, записывает событие в журнал аудита Office 365, когда администратор (или пользователь, которому назначены права администратора) вносит изменение в организации Exchange Online. Изменения, вносимые с помощью Центра администрирования Exchange или командлета Windows PowerShell, записываются в журнал аудита действий администратора Exchange. Более подробные сведения о ведении журнала аудита действий администратора в Exchange см. в статье [Ведение журнала аудита администратора](http://go.microsoft.com/fwlink/p/?LinkID=619225).
>- Чтобы записывать в журнал действия пользователей в Exchange Online, необходимо включить ведение журнала аудита почтовых ящиков Exchange для каждого пользовательского почтового ящика. См. статью [Действия, связанные с почтовыми ящиками Exchange](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).
>- Если включены приложения Office, группы, входящие в Office 365, также создаются в отдельных приложениях Office. Например, если включена система SharePoint, группы Office 365 будут созданы в SharePoint.
 
1.  На странице **Connected apps** (Подключенные приложения) щелкните знак "плюс" и выберите **Office 365**.  

2.  Во всплывающем окне Office 365 щелкните "Подключить Office 365".

      ![подключение Office 365](./media/connect-0365.png) 
 
3.  Чтобы проверить подключение к Office 365, нажмите кнопку "Протестировать сейчас". Проверка может занять несколько минут.
  
    ![проверка подключения к Office 365](./media/o365-test-connection.png) 
 
4.   После появления сообщения об успешном подключении Office 365 нажмите кнопку **Закрыть**.
  
     ![Office 365 подключен](./media/o365-connected.png) 

> [!NOTE] 
> После подключения Office 365 вы увидите данные за последнюю неделю, в том числе события сторонних приложений, которые подключены к Office 365 и используют интерфейсы API. Если сторонние приложения не использовали интерфейсы API до подключения, вы увидите события, произошедшие с момента подключения Office 365, так как Cloud App Security включает все интерфейсы API, которые были отключены по умолчанию.

## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  