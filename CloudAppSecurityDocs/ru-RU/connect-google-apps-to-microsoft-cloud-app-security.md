---
title: Подключение G Suite к Cloud App Security для видимости и контроля использования | Документы Майкрософт
description: В этом разделе приводятся сведения о подключении G Suite к Cloud App Security с помощью соединителя API.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 670d5f479d53741d4cd047b9ad9c864e1239d5d8
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*

# <a name="connect-g-suite-to-microsoft-cloud-app-security"></a>Подключение G Suite к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Microsoft Cloud App Security к существующей учетной записи G Suite с помощью интерфейсов API соединителя.
  
  
## <a name="configure-g-suite"></a>Настройка G Suite  
  
1. Войдите в <a href="https://cloud.google.com/console/project" target="_blank">https://cloud.google.com/console/project</a> в качестве суперадминистратора G Suite.  
  
2. Щелкните **Create project** (Создать проект) для запуска нового проекта.  
  
    ![google1](./media/google1.png "google1")  
  
3. На экране **New project** (Новый проект) присвойте имя проекту:</br>
   **Microsoft Cloud App Security**, а затем нажмите кнопку **Создать**.  
          ![google2](./media/google2.png "google2")  
  
4. После создания проекта выберите **Google Cloud Platform** в панели инструментов и убедитесь, что в раскрывающемся списке вверху выбран нужный проект.
       
      ![Проект google](./media/googleverify-project.png "Проект googleverify")  

5. В разделе **APIs** (API-интерфейсы) щелкните **Go to APIs overview** (Перейти к обзору API-интерфейсов).  
  
     ![google3](./media/google3.png "google3")  
  
6. В разделе **API** отключите все перечисленные API-интерфейсы.  
      
7. Щелкните **Library** (Библиотека) и включите следующие API (если API не отображается в списке **Popular APIs** (Популярные API), воспользуйтесь строкой поиска):  
     
   -   Admin SDK (SDK администрирования)  
  
   -   Audit API (API аудита)  
  
   -   API Google Drive  
  
   -   Пакет SDK для Apps Marketplace  
  
   -   Gmail API  
            
   ![API-интерфейсы google](./media/google4.png "google4")  
  
   > [!NOTE]  
   >  Проигнорируйте предупреждение об **учетных данных**.  

8. Щелкните "Включить" для каждого API-интерфейса.
     ![Включение Google APPI](./media/google-api.png "google-api")  
9. Здесь должно быть 5 **включенных API**, не забудьте отключить остальные API:
  
     ![включенные api google](./media/google5.png "google5")  
  
10. Щелкните **Credentials** (Учетные данные) и откройте вкладку **OAuth consent** (Получение согласия OAuth).
  
    - В поле **Product name shown to users** (Имя продукта, отображаемое пользователям) введите **Microsoft Cloud App Security**.  
  
    - Заполнять остальные поля необязательно.  
  
    - Нажмите кнопку **Сохранить**.  
  
      ![Имя продукта Google](./media/google6.png "google6")  
  
11. На вкладке **Credentials** (Учетные данные) щелкните стрелку рядом с полем **Create credentials** (Создать учетные данные).  
  
     ![Учетные данные Google](./media/google7.png "google7")  

12. Выберите пункт **Service account key** (Ключ учетной записи службы).

     ![Ключ учетной записи службы Google](./media/google8.png "google8")  
  
13. В поле **Service account** (Учетная запись службы) выберите **New service account** (Новая учетная запись службы) и введите любое имя, например **Service account 1**. В разделе **Role** (Роль) выберите **Project** (Проект) и **Editor** (Редактор). В разделе **Key type** (Тип ключа) выберите **P12** и нажмите кнопку **Create** (Создать). Файл сертификата P12 будет сохранен на компьютере.
 
     ![Создание ключа учетной записи службы в Google](./media/google9.png "google9")  
  
14. Скопируйте присвоенное службе значение **Service account ID** (Идентификатор учетной записи службы) — оно понадобится позже.    
        
15. В правой части экрана **Credentials** (Учетные данные) щелкните **Manage service accounts** (Управление учетными записями служб).  
     
    ![Данные учетной записи службы G Suite](./media/google10.png "G Suite credentials service account")  
  
16. Щелкните три точки справа от созданной учетной записи службы и выберите **Edit** (Изменить).  
  
     ![редактирование в google](./media/google11.png "редактирование в google")  
  
17. Установите флажок **Enable G Suite Domain-wide Delegation** (Включить делегирование в рамках домена G Suite) и нажмите кнопку **Save** (Сохранить).  
  
     ![Идентификатор учетной записи службы Google](./media/google12.png "google12")  
  
18. Откройте меню Google, щелкнув три горизонтальные линии рядом с Google Cloud Platform. Выберите **Google Cloud Platform** и щелкните вкладку **APIs and services** (API-интерфейсы и службы) в меню слева.  
    
19. На открывшейся панели мониторинга прокрутите список включенных API-интерфейсов и щелкните **API Google Drive**.   
       ![Выбор Google Drive](./media/google14.png "google14")  

20. Откройте вкладку **Drive UI Integration** (Интеграция пользовательского интерфейса диска) и введите следующие сведения:

    - **Application Name** (Имя приложения): Microsoft Cloud App Security.  
  
    - **Short Description & Long Description** (Короткое и длинное описание) (необязательно): Microsoft Cloud App Security обеспечивает видимость облачных приложений, помогая контролировать, анализировать и регулировать использование облачных приложений, защищать корпоративные данные, а также обнаруживать подозрительные действия для любого облачного приложения.  
  
    - Google требует отправить по крайней мере один значок приложения. Перейдите по ссылке [https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826), чтобы скачать ZIP-файл, содержащий значки Cloud App Security. После этого в разделе **Значок приложения** нажмите кнопку **Выбрать** рядом с изображением 128x128 и перетащите его на экран контекстного меню. Нажмите кнопку **Выбрать** рядом с изображением 32x32 и перетащите его на экран контекстного меню.  
  
    - Прокрутите страницу вниз до раздела **Drive Integration** (Интеграция диска) и введите следующие данные в поле **Open URL** (Открыть URL-адрес):  
  
       https://portal.cloudappsecurity.com/#/services/11770?tab=files  
    
      ![Изменить Google Drive](./media/google15.png "google15")  

21. Щелкните **Save changes** (Сохранить изменения).

22. Вернитесь к списку **Enabled APIs** (Включенные API-интерфейсы). Щелкните **Apps Marketplace SDK** (Пакет SDK для Apps Marketplace). 
      
23. Откройте вкладку **Configuration** (Конфигурация). 
  
    -   Скопируйте отображаемое сверху значение **Project number (App ID)** (Номер проекта — идентификатор приложения) для использования в дальнейшем.  
  
    -   В разделе **Application Name** (Имя приложения) введите **Microsoft Cloud App Security**.
  
         В поле **Application description** (Описание приложения) введите следующее: "Microsoft Cloud App Security обеспечивает видимость облачных приложений, помогая контролировать, анализировать и регулировать их использование, защищать корпоративные данные, а также обнаруживать подозрительные действия для любого облачного приложения".  
  
    -   Снимите флажок **Enable individual install** (Включить отдельную установку).  
  
    -   Настройте четыре требуемых изображения в разделе **Application icons** (Значки приложения).  
  
         Изображения можно найти здесь: [https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826)  
  
    -   Задайте приведенные ниже значения **Support URLs** (URL-адреса поддержки):  
  
        -   **Terms of service URL** (URL-адрес условий предоставления услуг): http://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **Privacy policy URL** (URL-адрес политики конфиденциальности): http://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   В разделе **OAuth 2.0 scopes** (Области OAuth 2.0) скопируйте и вставьте следующие URL-адреса (копируйте их по одному, нажимая клавишу ВВОД после каждого адреса):  
  
           https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
           https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
           https://www.googleapis.com/auth/drive  
  
           https://www.googleapis.com/auth/drive.appdata  
  
           https://www.googleapis.com/auth/drive.apps.readonly  
  
           https://www.googleapis.com/auth/drive.file  
  
           https://www.googleapis.com/auth/drive.metadata.readonly  
  
           https://www.googleapis.com/auth/drive.readonly  
  
           https://www.googleapis.com/auth/drive.scripts  
  
           https://www.googleapis.com/auth/admin.directory.user.readonly  
  
           https://www.googleapis.com/auth/admin.directory.user.security  
  
           https://www.googleapis.com/auth/admin.directory.user.alias  
  
           https://www.googleapis.com/auth/admin.directory.orgunit  
  
           https://www.googleapis.com/auth/admin.directory.notifications  
  
           https://www.googleapis.com/auth/admin.directory.group.member  
  
           https://www.googleapis.com/auth/admin.directory.group  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile  
  
           https://www.googleapis.com/auth/admin.directory.user  

    -   В разделе **Visibility** (Видимость) выберите **My domain** (Мой домен) (не общедоступный). 
    -   Щелкните **Сохранить изменения**.  
        ![Видимость Google](./media/google-visibility.png "Видимость google")  
24. Перейдите на страницу [admin.google.com](https://admin.google.com/) и выберите **Security** (Безопасность). 
   
      ![Безопасность Google](./media/googlesec.png "google security")  
 
25. Выберите **API reference** (Справочник по API).  
       ![Включение доступа к API Google](./media/googleapi.png "google api")  
      
26. Выберите **Enable API Access** (Включить доступ к API) и нажмите кнопку **Save changes** (Сохранить изменения).  
  
    ![справочник по api google](./media/googleapiref.png "google8")  

  
## <a name="configure-cloud-app-security"></a>Настройка Cloud App Security  
  
1.  На портале Cloud App Security выберите пункты **Исследовать** и **Подключенные приложения**.  
  
2.  На странице **Connected apps** (Подключенные приложения) щелкните знак "плюс" и выберите **G Suite**.  
       
  
3.  Во всплывающем окне введите следующее:  
  
     ![Настройка G Suite в Cloud App Security](./media/gsuite-config-cas.png "Настройка G Suite в Cloud App Security")  
  
    1.  **Service account ID** (Идентификатор учетной записи службы), скопированный на шаге 13.  
  
    2.  **Project number (App ID)** (Номер проекта — идентификатор приложения), скопированный в шаге 21.  
  
    3.  Отправьте **Certificate** (Сертификат) P12, сохраненный на шаге 12. Для этого потребуется сохраненный ранее пароль.  
  
    4.  Введите один **адрес электронной почты учетной записи администратора** вашего администратора G Suite.  
  
    5.  Если у вас есть учетная запись G Suite Business или Enterprise, установите этот флажок. Сведения о том, какие функции доступны в Cloud App Security для G Suite Business или Enterprise, можно найти в руководстве по [включению мгновенной видимости, защиты и действий управления для приложений](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).  
  
    6.  Щелкните **Сохранить настройки**.  
  
    7.  **Перейдите по ссылке** для подключения к G Suite. Откроется G Suite и будет предложено авторизовать доступ для Cloud App Security.  
         
    8.  Убедитесь, что подключение установлено, щелкнув **Test now** (Проверить).  
  
         Проверка может занять несколько минут.  
  
         После получения уведомления об успешном выполнении нажмите кнопку **Готово** и закройте страницу G Suite.  
  
  
После подключения G Suite вы получите события за 60 дней, предшествовавших подключению.
  
После подключения G Suite служба Cloud App Security выполняет полное сканирование. В зависимости от количества файлов и пользователей полное сканирование может занять некоторое время. Для включения сканирования практически в реальном времени, файлы, в которых обнаружены действия, перемещаются в начало очереди сканирования. Например, файл, который редактируется, обновляется или совместно используется, сканируется первым. Это не касается файлов, которые недоступны для изменений. Например, файлы, которые просматриваются, предварительно просматриваются, печатаются или экспортируются, сканируются по запланированному расписанию.
  
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  