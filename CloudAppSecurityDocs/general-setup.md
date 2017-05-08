---
title: "Настройка портала Cloud App Security для получения наилучших результатов | Документы Майкрософт"
description: "В этой статье описываются первые действия для настройки портала."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f05a39b834178406a6b4b010cd7a1c6096f8c37f
ms.sourcegitcommit: 945cb3c047ae1bfc05be20cc7798c43005b27c9b
ms.translationtype: HT
ms.contentlocale: ru-RU
---
# <a name="customize-the-portal"></a>Настройка портала
В следующей процедуре представлены инструкции по настройке портала Cloud App Security.
  
## <a name="set-up-the-portal"></a>Настройка портала  
  
1.  В строке меню на портале Cloud App Security щелкните значок параметров ![значок параметров](./media/settings-icon.png "значок параметров") и выберите пункт **Общие параметры**, чтобы настроить следующее:  
  
3.  **Сведения об организации**  
  
     Важно указать **Отображаемое имя организации**. Оно будет отображаться в сообщениях электронной почты и на веб-страницах, отправляемых из системы.  
  
     Укажите **Имя среды** (клиент). Это особенно важно, если вы управляете несколькими клиентами.  
  
4. Кроме того, можно указать **Логотип**, который будет отображаться в уведомлениях электронной почты и веб-страницах, отправляемых из системы. Логотип должен быть PNG-файлом размером до 150x50 пикселей на прозрачном фоне.  

4.  Задайте список **Управляемые домены**. Управляемые домены помогают Cloud App Security определить, какие пользователи являются внутренними, а какие — внешними, а также куда можно или запрещено предоставлять файлы для общего доступа. Это используется для отчетов, а также для оповещений.  
> [!NOTE] 
> - Пользователи, которые не настроены как внутренние, будут помечены как внешние, и их действия и файлы проверяться не будут.
> - При интеграции с Azure Information Protection см. сведения в разделе [Интеграция с Azure Information Protection](azip-integration.md). 
  
4.  **Параметры конфиденциальности для письма с журналом действий**  
  
     При обнаружении сообщений электронной почты из Exchange Online можно настроить их отображение таким образом, чтобы соблюсти конфиденциальность. Для этого можно использовать параметр **Маскированная строка темы**, **Полная строка темы** или **Только по идентификаторам**.  
  
     ![общие параметры](./media/general-settings.png "общие параметры")  
  
5.  **Язык и региональные стандарты**  
  
     Задайте для портала **Язык** по умолчанию. Чтобы изменить язык для отдельного администратора, выберите **Параметры пользователей** > **Настройки учетной записи**.  
  
     ![язык часового пояса](./media/timezone-language.png "язык часового пояса")  
  
     Задайте **Основной часовой пояс**. Cloud App Security постоянно анализирует и агрегирует данные. По умолчанию для портала Cloud App Security устанавливается часовой пояс UTC. Очень важно задать основной часовой пояс, который позволяет Cloud App Security точно регистрировать даты инцидентов в системе. Например, на диаграмме активности данные упорядочиваются по дате, которая зависит от часового пояса вашей системы, поэтому если вы не изменили часовой пояс по умолчанию, данные будут упорядочены по 24-часовым дням (согласно часовому поясу UTC), что может привести к рассинхронизации данных на несколько часов.  
  
     ![основной часовой пояс](./media/master-time-zone.png "основной часовой пояс")  
  
6.  Если вы захотите создать резервную копию параметров портала, воспользуйтесь этим экраном. Нажмите кнопку "Экспортировать параметры портала" для создания JSON-файла со всеми параметрами портала, включая правила политики, группы пользователей и диапазоны IP-адресов.  
  
     ![консоль архивации](./media/backup-console.png "консоль архивации")  
  
7.  Чтобы добавить дополнительных администраторов для Cloud App Security, щелкните значок параметров с шестеренкой ![значок параметров](./media/settings-icon.png "значок параметров") и выберите пункт **Управление административным доступом**. Добавьте администраторов, которым требуется доступ к Cloud App Security, и нажмите кнопку **Закрыть**.  
>[!NOTE]
>Любой не приглашенный пользователь (с соответствующей ролью: глобального администратора, администратора безопасности, администратора соответствия требованиям) может приглашать других пользователей в Cloud App Security.
  
![управление административным доступом](./media/manage-admin-access.png "управление административным доступом")  
  
##  <a name="Adminsettings"></a> Настройка параметров администратора  
Чтобы задать для себя параметры администратора Cloud App Security, щелкните свое имя в строке меню портала и выберите пункт **Параметры пользователей** для настройки следующих параметров:  
  
1.  Щелкните **Параметры учетной записи**. Здесь можно настроить язык портала. Можно оставить язык портала по умолчанию или выбрать другой язык.  
  
     ![пользовательские параметры](./media/custom-user-settings.png "пользовательские параметры")  
  
2.  Щелкните **Уведомления** и настройте параметры уведомлений электронной почты и текстовых уведомлений для сообщений электронной почты, получаемых из системы.  Можно задать уровень серьезности для оповещений и нарушений, по которым требуется получать сообщения электронной почты. Серьезность задается для каждой политики, поэтому при появлении нарушений отправка уведомления зависит от настроенных здесь параметров и параметра серьезности, заданного в нарушенной политике. Сообщения электронной почты отправляются на псевдоним, связанный с учетной записью администратора, которую вы использовали для входа в Cloud App Security. Введите номер телефона, чтобы система Cloud App Security могла отправлять вам текстовые сообщения при выдаче оповещений и уведомлений, и задайте уровень серьезности, для которого требуется получать уведомления.  
  
> [!NOTE] 
> Максимальное количество оповещений, отправляемых в виде текстовых сообщений, составляет 10 оповещений на каждый номер телефона в день. Обратите внимание на то, что день вычисляется в соответствии с часовым поясом UTC. 
  
  ![параметры уведомлений](./media/notification-settings.png "параметры уведомлений")  
  
3. Завершив настройку, нажмите кнопку **Сохранить**.  
  
##  <a name="IPtagsandRanges"></a> Задание диапазонов IP-адресов  
Чтобы легко определять известные IP-адреса, например IP-адреса физического офиса, необходимо задать диапазоны IP-адресов, позволяющие использовать теги и классификацию, а также настроить способ отображения журналов и оповещений.   
Дополнительные сведения см. в разделе [Теги IP-адресов](ip-tags.md).
  
## <a name="import-user-groups"></a>Импорт групп пользователей

При подключении приложений с помощью соединителей API служба Cloud App Security позволяет импортировать группы пользователей, например, из Office 365 и Azure Active Directory.

Дополнительные сведения см. в разделе [Группы пользователей](user-groups.md).

##  <a name="mailsettings"></a> Персонализация работы  
В строке меню щелкните значок параметров ![значок параметров](./media/settings-icon.png "значок параметров") и выберите пункт **Параметры почты**, чтобы задать параметры для уведомлений электронной почты, отправляемых из Cloud App Security администраторам, запрашивающим предупреждения, и уведомлений, отправляемых конечным пользователям по поводу нарушений, к которым они имеют отношение.  
  
![меню "параметры почты"](./media/mail-setting-menu.png "меню "параметры почты"")  
  
Необходимо установить:  
  
1.  **Адрес электронной почты отправителя**: учетная запись электронной почты, которую требуется использовать для отправки уведомления.  
  
     **Отображаемое имя отправителя**: имя, отображаемое в поле **От** сообщения электронной почты.  
  
     **Адрес электронной почты для ответа**: учетная запись электронной почты, используемая для ответов на сообщения.  
  
     ![изменение параметров почты](./media/mail-settings-config.png "изменение параметров почты")  
  
2.  Можно настроить и изменить структуру сообщений электронной почты, отправляемых из системы, с помощью HTML-файла. HTML-файл, используемый для шаблона, должен содержать следующее:  
  
    -   Все CSS должны быть встроены в шаблон.  
  
    -   Шаблон должен иметь три неизменяемых заполнителя:  
  
         %%logo%% — URL-адрес логотипа организации, который был отправлен на странице "Общие параметры".  
  
         %%title%% — заполнитель для заголовка сообщения электронной почты; задается политикой.  
  
         %%content%% — заполнитель для содержимого, которое будет включено для конечных пользователей; задается политикой.  
  
     Ниже приведен пример шаблона сообщения электронной почты: 
```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
  <html>  
       <head>  
            <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>  
            <meta name="viewport" content="width=device-width, initial-scale=1.0"/>  
          </head>  
          <body class="end-user">  
          <table border="0" cellpadding="20%" cellspacing="0" width="100%" id="background-table">  
            <tr>  
              <td align="center">  
                <!--[if (gte mso 9)|(IE)]>  
                <table width="600" align="center" cellpadding="0" cellspacing="0" border="0">  
                  <tr>  
                    <td>  
                <![endif]-->  
                <table bgcolor="#ffffff" align="center" border="0" cellpadding="0" cellspacing="0" style="padding-bottom: 40px;" id="container-table">  
                  <tr>  
                    <td align="right" id="header-table-cell">  
                      <img src="%%logo%%" alt="Microsoft Cloud App Security" id="org-logo" />  
                    </td>  
                  </tr>  
                  <tr>  
                    <td style="padding-top: 58px;" align="center" valign="top">  
                      <table width="100%" cellpadding="12">  
                        <tr>  
                          <td align="center" class="round-title">  
                            %%title%%  
                          </td>  
                        </tr>  
                      </table>  
                    </td>  
                  </tr>  
                  <tr>  
                    <td style="padding: 0 40px 79px 40px;" class="content-table-cell" align="left" valign="top">  
                        %%content%%  
                    </td>  
                  </tr>  
                  <tr>  
                    <td class="last-row"></td>  
                  </tr>  
                </table>  
                <!--[if (gte mso 9)|(IE)]>  
                </td>  
                </tr>  
                </table>  
                  <![endif]-->  
              </td>  
              </tr>  
          </table>  
            </body>  
          </html>  
    ```

  
3.  Click **Upload a template...** and select the file you created.  
  
     Then, click **Send a test email** to send yourself a test email to see an example of the template you created.  
     The email will be sent to the account you used to log into the portal. In the test email you will be able to see the metadata fields, the template, the email subject, the title in the email body and the content.  
  
## Single sign-on  
Cloud App Security is coupled with Azure Active Directory for authentication, provisioning, and licensing related activities. For information on how to manage single sign-on, see [Azure Active Directory federation compatibility list: third-party identity providers that can be used to implement single sign-on](https://msdn.microsoft.com/library/azure/jj679342.aspx).  


> [!NOTE] 
> If you use ExpressRoute, Cloud App Security is deployed in Azure and fully integrated with [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). All interactions with the Cloud App Security apps and traffic sent to Cloud App Security, including upload of discovery logs, is routed via ExpressRoute **public peering** for improved latency, performance and security. There are no configuration steps required from the customer side.  
    For more information about  Public Peering, see [ExpressRoute circuits and routing domains](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
    
## See Also  
[Set up Cloud Discovery](set-up-cloud-discovery.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  