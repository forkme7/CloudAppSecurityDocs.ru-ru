---
title: Настройка уведомлений электронной почты | Документация Майкрософт
description: В этой статье содержатся сведения о том, как настроить уведомления электронной почты, отправленные из Cloud App Security.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 8402cdc9-4969-4150-b567-ccc9d75e5370
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: fe6d3794a19f7223df263a941e097f365c275ea1
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*


##  <a name="mailsettings"></a> Настройка уведомлений электронной почты  

Чтобы задать параметры для уведомлений электронной почты, отправляемых из Microsoft Cloud App Security администраторам, запрашивающим предупреждения, а также для уведомлений, отправляемых конечным пользователям по поводу брешей, к которым они имеют отношение, сделайте следующее: Сведения об IP-адресе сервера электронной почты для Microsoft Cloud App Security, который нужно включить в список разрешенных в службе блокирования нежелательной почты, см. в перечне [требований к сети](network-requirements.md). 


1. В строке меню щелкните значок шестеренки ![Значок параметров](./media/settings-icon.png "settings icon"), выберите **Параметры** и откройте вкладку **Параметры почты**.  

2. **Адрес электронной почты отправителя**: учетная запись электронной почты, которую требуется использовать для отправки уведомления.  
   
   **Отображаемое имя отправителя**: имя, отображаемое в поле **От** сообщения электронной почты.  
   > [!NOTE]
   > Согласно [стандарту rfc822](http://www.rfc-editor.org/rfc/rfc822.txt), отображаемое имя и адрес электронной почты поддерживают только символы Юникода.

   **Адрес электронной почты для ответа**: учетная запись электронной почты, используемая для ответов на сообщения.  
  
     ![изменение параметров почты](./media/mail-settings-config.png "изменение параметров почты")  

   >[!NOTE]
   >Чтобы использовать в поле **Адрес электронной почты отправителя** собственный домен, ознакомьтесь с приведенными [здесь](https://mandrill.zendesk.com/hc/articles/205582277-How-do-I-add-DNS-records-for-my-sending-domains-) инструкциями.
  
3. **Дизайн письма** можно менять, настраивая и изменяя структуру сообщений электронной почты, отправляемых из системы, с помощью HTML-файла. HTML-файл, используемый для шаблона, должен содержать следующее:  
  
   -   Все файлы шаблона CSS должны быть встроены в шаблон.  
  
   -   Шаблон должен иметь три неизменяемых заполнителя:  
  
        %%logo%% — URL-адрес логотипа организации, который был отправлен на странице "Общие параметры".  
  
        %%title%% — заполнитель для заголовка сообщения электронной почты; задается политикой.  

        %%content%% — заполнитель для содержимого, которое будет включено для конечных пользователей; задается политикой.  
     
4. Щелкните **Отправить шаблон...** и выберите созданный файл. 

5. Щелкните **Отправить тестовое письмо**, чтобы отправить себе тестовое сообщение в качестве примера созданного шаблона. Сообщение направляется в учетную запись, которую вы использовали для входа на портал. В тестовом сообщении можно просмотреть поля метаданных, шаблон, тему сообщения, заголовок в тексте сообщения и содержимое.  Ниже приведен пример шаблона сообщения электронной почты: 



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
  

  
  

  
    
## <a name="see-also"></a>См. также  
[Настройка Cloud Discovery](set-up-cloud-discovery.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  