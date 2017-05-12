---
title: "Управление доступом администратора к порталу Cloud App Security | Документация Майкрософт"
description: "Эта статья содержит инструкции по настройке доступа для администраторов к порталу Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/7/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ce7a3bb3951e16efeaeafa3e2fc463a3ac5d9dbc
ms.sourcegitcommit: 945cb3c047ae1bfc05be20cc7798c43005b27c9b
ms.translationtype: HT
ms.contentlocale: ru-RU
---
## <a name="managing-admin-access"></a>Управление доступом администратора

Cloud App Security поддерживает следующие роли администратора.

- Глобальный администратор. Глобальным администраторам предоставляется **полный доступ**. Администраторы с правами полного доступа в Cloud App Security могут добавлять администраторов, параметры и политики, а также отправлять журналы и выполнять действия управления.
- Администратор безопасности. Администраторам безопасности предоставляется **полный доступ**. Администраторы с правами полного доступа в Cloud App Security могут добавлять администраторов, параметры и политики, а также отправлять журналы и выполнять действия управления.
- Читатель безопасности. Читателю безопасности предоставляются разрешения только на чтение и управление оповещениями. Читателю безопасности запрещено выполнять следующие действия.
      - Создавать новые политики и изменять существующие 
      - Выполнять любые действия управления 
      - Передавать журналы обнаружения
      - Блокировать или утверждать приложения третьей стороны
      - Открывать и просматривать страницу параметров диапазона IP-адресов
      - Открывать и просматривать любые страницы параметров 
      - Открывать и просматривать параметры обнаружения 
      - Открывать и просматривать страницу соединителей приложения
      - Открывать и просматривать журнал управления 
      - Открывать и просматривать страницу управления отчетами о снимках 

Роли администраторов в Cloud App Security совпадают с их ролями в Azure Active Directory или Office 365. Дополнительные сведения см. в статье [Назначение ролей администратора в Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles).

Вот как добавить администраторов в Cloud App Security:

1. Щелкните значок параметров с шестеренкой ![значок параметров](./media/settings-icon.png "значок параметров") и выберите пункт **Управление административным доступом**. 

2. Добавьте администраторов, которым требуется доступ к Cloud App Security.
  
      
3. Затем щелкните раскрывающийся список, чтобы определить тип доступа для администратора: **Полный доступ** или **Читатель безопасности**.

     >[!NOTE]
      >Все администраторы с ролью **читателя безопасности**, которые пытаются получить доступ к странице с ограниченным доступом или выполнить запрещенное действие, получат сообщение о том, что у них нет разрешения на доступ к странице или выполнение действия.

4. Нажмите кнопку **Закрыть**.  

   >[!NOTE]
    >Любой не приглашенный пользователь (с соответствующей ролью: глобального администратора, администратора безопасности, администратора соответствия требованиям) может приглашать других пользователей в Cloud App Security.
  
 ![управление административным доступом](./media/manage-admin-access.png "управление административным доступом")  

**Вот как переопределить разрешения администратора:**

Чтобы переопределить разрешение администратора Azure Active Directory или Office 365, добавьте пользователя вручную в Cloud App Security или назначьте ему роль.
Например, если вы хотите назначить Светлане с ролью читателя безопасности в Azure Active Directory полный доступ в Cloud App Security, добавьте ее вручную в Cloud App Security и назначьте ей полный доступ, чтобы переопределить ее роль и предоставить ей нужные разрешения в Cloud App Security. 


##  <a name="Adminsettings"></a> Настройка параметров администратора  
Чтобы задать для себя параметры администратора Cloud App Security, щелкните свое имя в строке меню портала и выберите пункт **Параметры пользователей** для настройки следующих параметров:  
  
1.  Щелкните **Параметры учетной записи**. Здесь можно настроить язык портала. Можно оставить язык портала по умолчанию или выбрать другой язык.  
  
     ![пользовательские параметры](./media/custom-user-settings.png "пользовательские параметры")  
  
2.  Щелкните **Уведомления** и настройте параметры уведомлений электронной почты и текстовых уведомлений для сообщений электронной почты, получаемых из системы.  Можно задать уровень серьезности для оповещений и нарушений, по которым требуется получать сообщения электронной почты. Серьезность задается для каждой политики, поэтому при появлении нарушений отправка уведомления зависит от настроенных здесь параметров и параметра серьезности, заданного в нарушенной политике. Сообщения электронной почты отправляются на псевдоним, связанный с учетной записью администратора, которую вы использовали для входа в Cloud App Security. Введите номер телефона, чтобы система Cloud App Security могла отправлять вам текстовые сообщения при выдаче оповещений и уведомлений, и задайте уровень серьезности, для которого требуется получать уведомления.  
  
   > [!NOTE] 
   > Максимальное количество оповещений, отправляемых в виде текстовых сообщений, составляет 10 оповещений на каждый номер телефона в день. Обратите внимание на то, что день вычисляется в соответствии с часовым поясом UTC. 
  
  ![параметры уведомлений](./media/notification-settings.png "параметры уведомлений")  
  
3. Завершив настройку, нажмите кнопку **Сохранить**.  


## <a name="region-and-language-settings"></a>Язык и региональные стандарты  
  
1. Задайте для портала **Язык** по умолчанию. Чтобы изменить язык для отдельного администратора, выберите **Параметры пользователей** > **Настройки учетной записи**.  
  
   ![язык часового пояса](./media/timezone-language.png "язык часового пояса")  
  
2. Задайте **Основной часовой пояс**. Cloud App Security постоянно анализирует и агрегирует данные. По умолчанию для портала Cloud App Security устанавливается часовой пояс UTC. Очень важно задать основной часовой пояс, который позволяет Cloud App Security точно регистрировать даты инцидентов в системе. Например, на диаграмме активности данные упорядочиваются по дате, которая зависит от часового пояса вашей системы, поэтому если вы не изменили часовой пояс по умолчанию, данные будут упорядочены по 24-часовым дням (согласно часовому поясу UTC), что может привести к рассинхронизации данных на несколько часов.  
  
     ![основной часовой пояс](./media/master-time-zone.png "основной часовой пояс")  
  
## <a name="back-up-portal-settings"></a>Резервное копирование параметров портала

Если вы захотите создать резервную копию параметров портала, воспользуйтесь этим экраном. Нажмите кнопку "Экспортировать параметры портала" для создания JSON-файла со всеми параметрами портала, включая правила политики, группы пользователей и диапазоны IP-адресов.  
  
![консоль архивации](./media/backup-console.png "консоль архивации")  
  
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
  
  