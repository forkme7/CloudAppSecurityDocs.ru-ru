---
title: "Подключение Salesforce | Microsoft Docs"
description: "В этой статье приводятся сведения о подключении приложения Salesforce к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 776d7589-acdb-4cb6-99a0-3be2f7b6aab2
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 129181e4768f068a0e30f6ef3a2d3f7fc6d47024
ms.openlocfilehash: 0932c6bc696e7b050eae543fbea7d847dfa42b4b


---


# <a name="connect-salesforce-to-microsoft-cloud-app-security"></a>Подключение Salesforce к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи Salesforce с помощью API соединителя приложений.  
  
## <a name="how-to-connect-salesforce-to-cloud-app-security"></a>Порядок подключения Salesforce к Cloud App Security  
  
1.  Рекомендуется использовать выделенную учетную запись администратора службы для Cloud App Security.  
  
2.  Убедитесь, что в Salesforce включен REST API.  
  
     Ваша учетная запись Salesforce должна относиться к одному из следующих выпусков, поддерживающих REST API:  
  
     **Performance**, **Enterprise**, **Unlimited** или **Developer**.  
  
     Выпуск **Professional** не имеет REST API по умолчанию, но его можно добавить по запросу.  
  
     Убедитесь, что REST API доступен и включен во всех используемых выпусках:  
  
    -   Войдите в учетную запись Salesforce и перейдите на страницу **Установка**.  
  
    -   В разделе **Управление пользователями** перейдите на страницу **Профили**.  
  
         ![профили управления пользователями salesforce](./media/salesforce-manageusers-profiles.png "профили управления пользователями salesforce")  
  
    -   Выберите профиль, используемый для развертывания Cloud App Security, и нажмите кнопку **Изменить**. Это профиль для использования учетной записи службы Cloud App Security при настройке соединителя приложения.  
  
         ![изменение профиля salesforce](./media/salesforce-edit-profile.png "изменение профиля salesforce")  
  
    -   Убедитесь, что флажок **API Enabled** (API включен) установлен. Если это не так, вам может потребоваться обратиться в Salesforce, чтобы добавить его в учетную запись.  
  
         ![api salesforce включен](./media/salesforce-api-enabled.png "api salesforce включен")  
  
3.  Если в вашей организации включен параметр **Salesforce CRM Content** (Содержимое Salesforce CRM), убедитесь, что он включен и в используемой учетной записи администратора.  
  
    1.  Перейдите на страницу установки Salesforce.  
  
         ![настройка salesforce](./media/salesforce-setup.png "настройка salesforce")  
  
    2.  В боковом меню выберите пункт **Управление пользователями** и нажмите кнопку **Пользователи**.  
  
         ![меню "пользователи" salesforce](./media/salesforce-menu-users.png "меню "пользователи" salesforce")  
  
    3.  Выберите вашего выделенного пользователя Cloud App Security в качестве текущего пользователя с правами администратора.  
  
    4.  Убедитесь, что установлен флажок **Salesforce CRM Content User** (Пользователь содержимого Salesforce CRM).  
  
         Если он не установлен, щелкните **Изменить** и установите его.  
  
         ![пользователь содержимого salesforce crm](./media/salesforce-crm-content-user.png "пользователь содержимого salesforce crm")  
  
    5.  Нажмите кнопку **Сохранить**.  
  
4.  В консоли Cloud App Security щелкните **Исследовать**, а затем — **Подключенные приложения**.  
  
5.  На странице **App connectors** (Соединители с приложениями) щелкните знак "плюс", а затем — **Salesforce**.  
  
     ![подключение salesforce](./media/connect-salesforce.png "подключение salesforce")  
  
6.  На вкладке "API" страницы параметров Salesforce щелкните **Перейти по ссылке** с учетом того, какой экземпляр требуется установить.  
  
7.  Открывается страница входа в Salesforce. Введите свои учетные данные, чтобы разрешить Cloud App Security доступ к приложению Salesforce вашей группы.  
  
     ![вход в salesforce](./media/salesforce-logon.png "вход в salesforce")  
  
8.  Salesforce запрашивает, следует ли Cloud App Security разрешить доступ к журналу действий и сведениям группы, а также выполнение любых действий от лица любого члена группы. Для продолжения нажмите кнопку **Разрешить**.  
  
9. На этом этапе выдается уведомление об успехе или неудаче развертывания. Служба Cloud App Security теперь авторизована на сайте Salesforce.com.  
  
10. После возвращения в консоль Cloud App Security должно появиться сообщение об успешном подключении Salesforce.  
  
11. Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После получения уведомления об успешном выполнении нажмите кнопку **Готово**.  
  
  
После подключения Salesforce вы будете получать события следующим образом: триггеры — с момента подключения; события входа и журнал аудита настройки — за 60 дней, предшествовавших подключению; EventMonitoring — за 30 или один предшествующий день в зависимости от лицензии Salesforce EventMonitoring.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Dec16_HO2-->


