---
title: "Подключение AWS к Cloud App Security для видимости и контроля использования | Документы Майкрософт"
description: "В этом разделе приводятся сведения о подключении приложения AWS к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 68d4c221626706ca641a5d3e1986da543771561a
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2017
---
# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Подключение AWS к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи Amazon Web Services с помощью интерфейсов API соединителя.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Порядок подключения Amazon Web Services к Cloud App Security  
  
1.  В [консоли Amazon Web Services](https://console.aws.amazon.com/) в разделе **Безопасность, идентификация и соответствие** щелкните **IAM**.  
  
     ![идентификация и доступ aws](./media/aws-identity-and-access.png "идентификация и доступ aws")  
  
2.  Откройте вкладку **Пользователи** и нажмите кнопку **Добавить пользователя**.  
  
     ![пользователи aws](./media/aws-users.png "пользователи aws")      
  
4.  На шаге **Сведения** укажите новое имя пользователя для Cloud App Security, в поле **Тип доступа** выберите **Программный доступ** и нажмите кнопку **Next Permissions** (Далее — разрешения).  

     ![Создание пользователя в AWS](./media/aws-create-user.png "Создание пользователя в AWS")

5. На шаге **Разрешения** щелкните **Attach existing policies directly** (Присоединить существующие политики напрямую), а затем нажмите кнопку **Create policy** (Создать политику).

   ![присоединение пользователя в AWS](./media/aws-attach-user-policy.png "присоединение существующей политики в AWS")

6.  В разделе **Create Policy** (Создание политики) выберите **Create Your Own Policy** (Создать собственную политику).
 
    ![создание собственной политики в AWS](./media/aws-create-own-policy.png "создание политики в AWS")
 
7.  В разделе **Review Policy** (Просмотр политики) в поле **Policy Name** (Имя политики) введите имя, например CloudAppSecurityPolicy.

    ![просмотр политики в AWS](./media/aws-review-policy.png "просмотр политики в AWS")

8. Вставьте следующий фрагмент в поле **Policy Document** (Документ политики), а затем нажмите кнопку **Create policy** (Создать политику):
  
    ```     
    {  
      "Version" : "2012-10-17",  
      "Statement" : [{  
          "Action" : [  
            "cloudtrail:DescribeTrails",  
            "cloudtrail:LookupEvents",  
            "cloudtrail:GetTrailStatus",  
            "cloudwatch:Describe*",  
            "cloudwatch:Get*",  
            "cloudwatch:List*",  
            "iam:List*",  
            "iam:Get*"  
          ],  
          "Effect" : "Allow",  
          "Resource" : "*"  
        }  
      ]  
     }  
  
    ```  
  
9. Вернитесь на страницу **Добавление пользователя**, при необходимости обновите список, выберите только что созданного пользователя и нажмите кнопку **Далее — просмотр**.

   ![просмотр политики пользователя в AWS](./media/aws-review-user.png "просмотр политики пользователя в AWS")

10. Если все сведения указаны правильно, нажмите кнопку **Создать пользователя**.

    ![разрешения пользователя в AWS](./media/aws-user-permissions.png "просмотр разрешений пользователя в AWS")

11. При получении сообщения об успехе щелкните **Скачать CSV-файл**, чтобы сохранить копию новых учетных данных пользователя, которые потребуются позднее.  

    ![Скачать CSV-файл в AWS](./media/aws-download-csv.png "Скачать CSV-файл в AWS")
  
10. В консоли AWS щелкните **Службы** и затем в разделе **Средства управления** щелкните **CloudTrail**.  
  
     ![aws cloudtrail](./media/aws-cloudtrail.png "aws cloudtrail")  
  
    Если ранее вы не использовали CloudTrail, нажмите кнопку **Приступая к работе** и настройте этот компонент, указав имя и выбрав соответствующий сегмент S3. Затем щелкните **Turn On** (Включить). Чтобы обеспечить полное покрытие, задайте для параметра **Apply to all regions** (Применить ко всем регионам) значение **Да**.
  
       ![включение CloudTrail в AWS](./media/aws-turnon-cloudtrail.png "включение CloudTrail в AWS")
  
    Вы увидите новое имя в CloudTrail в списке **Trails** (Журналы).
    
      ![список CloudTrail в AWS](./media/aws-cloudtrail-list.png "список CloudTrail в AWS")
  
11. На портале Cloud App Security выберите пункты **Исследовать** и **Подключенные приложения**.  
  
12. На странице **App connectors** (Соединители с приложениями) щелкните знак "плюс", а затем — **AWS**.  
  
     ![подключение AWS](./media/connect-aws.png "подключение AWS")  
  
13. Во всплывающем окне вставьте значения параметров **Ключ доступа** и **Секретный ключ** из CSV-файла в соответствующие поля и нажмите кнопку **Подключить**.  
   ![подключение приложения в AWS](./media/aws-connect-app.png "AWS connect app") 
  
14. Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После завершения выдается уведомление об успехе или неудаче. После получения уведомления об успешном выполнении нажмите кнопку **Готово**.  
  
После подключения AWS вы получите события за 7 дней, предшествовавших подключению, если вы пока не включили CloudTrail. В противном случае вы будете получать события с момента включения CloudTrail.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  