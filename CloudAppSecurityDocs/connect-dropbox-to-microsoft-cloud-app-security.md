---
title: "Подключение Dropbox к Cloud App Security для видимости и контроля использования | Документы Майкрософт"
description: "В этом разделе приводятся сведения о подключении приложения Dropbox к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4acd93f4-b885-4e1f-a385-43b5db02a3ee
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 56195253a603671d2f273616b652f5d821e80a51
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2017
---
# <a name="connect-dropbox-to-microsoft-cloud-app-security"></a>Подключение Dropbox к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи Dropbox с помощью интерфейсов API соединителя.  
 
 
Так как Dropbox обеспечивает доступ к файлам по общим ссылкам без входа в систему, Cloud App Security регистрирует таких пользователей как не прошедших проверку подлинности. Если вы видите не прошедших проверку пользователей Dropbox, это могут быть пользователи не из вашей организации или пользователи из вашей организации, которые не вошли в систему.

## <a name="how-to-connect-dropbox-to-cloud-app-security"></a>Порядок подключения Dropbox к Cloud App Security  
  
1.  В консоли Cloud App Security щелкните **Исследовать**, а затем — **Подключенные приложения**.  
  
2.  На странице **Соединители приложений** щелкните знак "плюс", а затем — **Dropbox**.  
  
     ![подключение dropbox](./media/connect-dropbox.png "подключение dropbox")  
  
3.  Во всплывающем окне введите адрес электронной почты учетной записи администратора.  
  
4.  Щелкните **Создать ссылку**.  
  
5.  Щелкните **Перейти по ссылке**.  
  
     Откроется страница входа в Dropbox. Введите свои учетные данные, чтобы разрешить Cloud App Security доступ к экземпляру Dropbox вашей группы.  
  
6.  Dropbox запросит, следует ли Cloud App Security разрешить доступ к журналу действий и сведениям группы, а также выполнять действия от имени любого члена группы. Для продолжения нажмите кнопку **Разрешить**.  
  
7.  После возвращения в консоль Cloud App Security должно появиться сообщение об успешном подключении Dropbox.  
  
8.  Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Закрыть**.  
  
После подключения Dropbox вы получите события за 60 дней, предшествовавших подключению.

> [!NOTE] 
> События добавления файлов в Dropbox отображаются в Cloud App Security как события отправки файлов для обеспечения соответствия с другими приложениями, подключенными к Cloud App Security. 
 
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Получить техническую поддержку можно на странице службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  