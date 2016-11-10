---
title: "Подключение Google Apps к Microsoft Cloud App Security | Документы Майкрософт"
description: "В этом разделе приводятся сведения о подключении Google Apps к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 0f38f61be8a0db4a28d3c7df614807ace69bb38e


---

# <a name="connect-google-apps-to-microsoft-cloud-app-security"></a>Подключение Google Apps к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи Google Apps с помощью интерфейсов API соединителя.  
  
## <a name="configure-google-apps"></a>Настройка Google Apps  
  
1.  Являясь суперадминистратором Google Apps, войдите на сайт [https://cloud.google.com/console/project](https://cloud.google.com/console/project).  
  
2.  Щелкните **Create an empty project** (Создать пустой проект) для запуска нового проекта.  
  
     ![google1](./media/google1.png "google1")  
  
3.  На экране **Новый проект** выполните следующее:  
  
    1.  Назовите проект **Cloud App Security for Google**.  
  
    2.  Укажите, требуется ли подписаться на обновления.  
  
    3.  Просмотрите и утвердите условия использования.  
  
    4.  Нажмите кнопку **Create** (Создать).  
  
         ![google2](./media/google2.png "google2")  
  
4.  После создания проекта щелкните элемент **Enable and manage APIs** (Включить API и управлять ими).  
  
     ![google3](./media/google3.png "google3")  
  
5.  Откройте вкладку **Enabled APIs** (Включенные API) и отключите все перечисленные API.  
  
     ![google5](./media/google5.png "google5")  
  
6.  Откройте вкладку **Google APIs** (API Google) и включите следующие API (если API не отображается в списке **Popular APIs** (Популярные API), воспользуйтесь строкой поиска):  
  
     ![google8](./media/google8.png "google8")  
  
    > [!NOTE]  
    >  Проигнорируйте предупреждение об **учетных данных**.  
  
    -   Admin SDK (SDK администрирования)  
  
    -   Audit API (API аудита)  
  
    -   Drive API (API диска)  
  
    -   Google Apps Marketplace SDK  
  
    -   Gmail API  
  
         ![предупреждение google11](./media/google11-warning.png "google11 warning")  
  
7.  В списке **Enabled APIs** (Включенные API) должно быть пять элементов:  
  
     ![google15](./media/google15.png "google15")  
  
8.  Щелкните **Credentials** (Учетные данные) и затем **OAuth consent** (Получение согласия OAuth).  
  
    -   В поле **Product name shown to users** (Имя продукта, отображаемое пользователям) введите **Cloud App Security for Google**.  
  
    -   Заполнять остальные поля необязательно.  
  
    -   Нажмите кнопку **Сохранить**.  
  
     ![google16](./media/google16.png "google16")  
  
9. На вкладке **Credentials** (Учетные данные) щелкните стрелку рядом с элементом **Create credentials** (Создать учетные данные) и выберите **Service account key** (Ключ учетной записи службы).  
  
     ![google17](./media/google17.png "google17")  
  
10. В поле **Service account** (Учетная запись службы) выберите **New service account** (Новая учетная запись службы) и введите любое имя, например **Service account 1**.  
  
     ![google19](./media/google19.png "google19")  
  
     В разделе **Key type** (Тип ключа) выберите **P12** и нажмите кнопку **Create** (Создать).  
  
     Скачивается файл сертификата P12. Сохраните сертификат для использования в дальнейшем.  
  
     ![google20](./media/google20.png "google20")  
  
11. В правой части вкладки **Credentials** (Учетные данные) щелкните **Manage service accounts** (Управление учетными записями служб).  
  
     ![данные учетной записи службы google apps](./media/google-apps-credentials-service-account.png "google apps credentials service account")  
  
12. Щелкните три точки справа от созданной учетной записи службы и выберите **Изменить**.  
  
     ![google22](./media/google22.png "google22")  
  
13. Установите флажок **Enable Google Apps Domain-wide Delegation** (Включить делегирование в рамках домена Google Apps) и нажмите кнопку **Save** (Сохранить).  
  
     ![google24](./media/google24.png "google24")  
  
14. Скопируйте присвоенное службе значение **Email address** (Адрес электронной почты) — оно понадобится позже.  
  
     ![google25](./media/google25.png "google25")  
  
15. Откройте меню Google, щелкнув три горизонтальные линии рядом с Google Cloud Platform, и выберите **API manager** (Диспетчер API).  
  
     ![меню google](./media/google-menu.png "google menu")  
  
     Выберите **Enabled APIs** (Включенные API).  
  
     ![google27](./media/google27.png "google27")  
  
16. Щелкните значок параметров с шестеренкой рядом с элементом **Drive API** (API диска) и в разделе **Drive UI Integration** (Интеграция пользовательского интерфейса диска) укажите следующие:  
  
    -   **Application Name** (Имя приложения): Cloud App Security for Google.  
  
    -   **Short Description & Long Description** (Короткое и длинное описание): Microsoft Cloud App Security обеспечивает видимость облачных приложений, помогая контролировать, анализировать и регулировать использование облачных приложений, защищать корпоративные данные, а также обнаруживать подозрительные действия для любого облачного приложения.  
  
    -   В разделе **Application icon** (Значок приложения) загрузите изображения размером 128x128 и 32x32.  
  
         Эти изображения можно найти по адресу: [https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
    -   Введите следующие сведения в поле **Open URL** (Открыть URL-адрес):  
  
         https://portal.cloudappsecurity.com/#/services/11770?tab=files  
  
    -   Щелкните **Save Changes** (Сохранить изменения).  
  
         ![google29](./media/google29.png "google29")  
  
17. В списке **Enabled APIs** (Включенные API) выберите значок параметров с шестеренкой рядом с **Google Apps Marketplace SDK** и откройте вкладку **Configuration** (Конфигурация).  
  
    -   Скопируйте отображаемое сверху значение **Project number (App ID)** (Номер проекта — идентификатор приложения) для использования в дальнейшем.  
  
    -   **Application Name** (Имя приложения): Cloud App Security for Google.  
  
         Укажите в поле **Application description** (Описание приложения) следующее: "Microsoft Cloud App Security обеспечивает видимость облачных приложений, помогая контролировать, анализировать и регулировать использование облачных приложений, защищать корпоративные данные, а также обнаруживать подозрительные действия для любого облачного приложения".  
  
    -   Снимите флажок **Enable individual install** (Включить отдельную установку).  
  
    -   Настройте четыре требуемых изображения в разделе **Application icons** (Значки приложения).  
  
         Эти изображения можно найти по адресу: [https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
         ![google31](./media/google31.png "google31")  
  
    -   Задайте приведенные ниже значения **Support URLs** (URL-адреса поддержки):  
  
        -   **URL-адрес условий использования**: http://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **URL-адрес политики конфиденциальности**: http://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   В поле **областей OAuth 2.0** введите следующие адреса (по одному на строку; нажимайте клавишу ВВОД для подтверждения):  
  
        -   https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
        -   https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
        -   https://www.googleapis.com/auth/drive  
  
        -   https://www.googleapis.com/auth/drive.appdata  
  
        -   https://www.googleapis.com/auth/drive.apps.readonly  
  
        -   https://www.googleapis.com/auth/drive.file  
  
        -   https://www.googleapis.com/auth/drive.metadata.readonly  
  
        -   https://www.googleapis.com/auth/drive.readonly  
  
        -   https://www.googleapis.com/auth/drive.scripts  
  
        -   https://www.googleapis.com/auth/admin.directory.user.readonly  
  
        -   https://www.googleapis.com/auth/admin.directory.user.security  
  
        -   https://www.googleapis.com/auth/admin.directory.user.alias  
  
        -   https://www.googleapis.com/auth/admin.directory.orgunit  
  
        -   https://www.googleapis.com/auth/admin.directory.notifications  
  
        -   https://www.googleapis.com/auth/admin.directory.group.member  
  
        -   https://www.googleapis.com/auth/admin.directory.group  
  
        -   https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
        -   https://www.googleapis.com/auth/admin.directory.device.mobile  
  
        -   https://www.googleapis.com/auth/admin.directory.user  
  
    -   Щелкните **Сохранить изменения**.  
  
18. Выберите **Security** (Безопасность) в списке элементов управления. Если этот параметр отсутствует, выберите "More controls" (Дополнительные элементы управления) на серой панели в нижней части страницы, а затем выберите **Security** (Безопасность).  
  
     ![безопасность google apps](./media/google-apps-security.png "google apps security")  
  
19. Выберите **API reference** (Справочник по API).  
  
     ![справочник по api google](./media/google-api-ref.png "google api ref")  
  
20. Выберите **Enable API Access** (Включить доступ к API) и нажмите кнопку **Save changes** (Сохранить изменения).  
  
     ![доступ к api google](./media/google-api-access.png "google api access")  
  
## <a name="configure-cloud-app-security"></a>Настройка Cloud App Security  
  
1.  На портале Cloud App Security щелкните **Сведения** и затем **Санкционированные приложения**.  
  
2.  Перейдя в строку Google Apps, щелкните элемент **Подключение** в столбце **Состояние соединителя приложений** или нажмите кнопку **Подключить приложение**, а затем щелкните элемент **Google Apps**.  
  
     ![подключение google apps](./media/connect-google-apps.png "connect google apps")  
  
3.  На странице параметров Google Apps введите следующие данные:  
  
     ![Настройка Google Apps в Cloud App Security](./media/google-apps-configuration-in-cloud-app-security.png "Google Apps Configuration in Cloud App Security")  
  
    1.  **Google Service Account email address** (Адрес электронной почты учетной записи службы Google), скопированный на шаге 14.  
  
    2.  **Google Project number (App ID)** (Номер проекта — идентификатор приложения), скопированный в шаге 17.  
  
    3.  Отправьте **Google Certificate** (Сертификат Google) P12, сохраненный на шаге 10.  
  
    4.  Введите один **адрес электронной почты администратора** вашего администратора Google Apps.  
  
    5.  При наличии учетной записи Google Apps Unlimited установите этот флажок. Сведения о том, какие функции доступны в Cloud App Security для Google Apps Unlimited, см. в статье [Включение мгновенной видимости, защиты и действий управления для приложений](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).  
  
    6.  Щелкните **Сохранить настройки**.  
  
    7.  **Перейдите по ссылке** для подключения к Google Apps. При этом открывается Google Apps и предлагается авторизовать доступ для Cloud App Security.  
  
         ![Запрос авторизации Google Apps](./media/google-apps-authorization-request.png "Google Apps authorization request")  
  
    8.  Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
         Проверка может занять несколько минут.  
  
         После получения уведомления об успешном выполнении нажмите кнопку **Готово** и закройте страницу Google Apps.  
  
  
После подключения Google Apps вы получите события за 60 дней, предшествовавших подключению.
  
После подключения Google Apps служба Cloud App Security выполняет полное сканирование. В зависимости от количества файлов и пользователей полное сканирование может занять некоторое время. Чтобы обеспечить сканирование почти в реальном времени, файлы, действия с которыми обнаружены, перемещаются в начало очереди сканирования. Например, файл, который изменяется, обновляется или предоставляется, сканируется немедленно, так что вам не приходится ждать, когда он будет обработан стандартным процессом сканирования. Это не относится к файлам, содержимое которых не изменяется, например к файлам, которые просматриваются, печатаются или экспортируются.
  
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


