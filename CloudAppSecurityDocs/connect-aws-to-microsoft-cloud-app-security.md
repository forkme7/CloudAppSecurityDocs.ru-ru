---
title: "Подключение AWS к Cloud App Security для видимости и контроля использования | Документы Майкрософт"
description: "В этом разделе приводятся сведения о подключении приложения AWS к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: bb0703442d3568556dc54df5e1bd7901906ca9b3
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2017
---
# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Подключение AWS к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи Amazon Web Services с помощью интерфейсов API соединителя.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Порядок подключения Amazon Web Services к Cloud App Security  
  
1.  В [консоли Amazon Web Services](https://console.aws.amazon.com/) в разделе **Безопасность, идентификация и соответствие** щелкните **IAM**.  
  
     ![Идентификация и доступ AWS](./media/aws-identity-and-access.png "AWS identity and access")  
  
2.  Откройте вкладку **Пользователи** и нажмите кнопку **Добавить пользователя**.  
  
     ![Пользователи AWS](./media/aws-users.png "AWS users")      
  
4.  На шаге **Details** (Сведения) введите имя пользователя для Cloud App Security. В поле **Access type** (Тип доступа) установите флажок **Programmatic access** (Программный доступ) и нажмите кнопку **Далее разрешения** (Далее — разрешения).  

     ![Создание пользователя в AWS](./media/aws-create-user.png "Create user in AWS")

5. На шаге **Разрешения** щелкните **Attach existing policies directly** (Присоединить существующие политики напрямую), а затем нажмите кнопку **Create policy** (Создать политику).

   ![Присоединение пользователя в AWS](./media/aws-attach-user-policy.png "Attach user policy in AWS")

6.  В разделе **Create Policy** (Создание политики) выберите **Create Your Own Policy** (Создать собственную политику).
 
    ![Создание собственной политики в AWS](./media/aws-create-own-policy.png "Create policy in AWS")
 
7.  В разделе **Review Policy** (Просмотр политики) в поле **Policy Name** (Имя политики) введите имя, например CloudAppSecurityPolicy.

    ![Просмотр политики в AWS](./media/aws-review-policy.png "Review policy in AWS")

8. Вставьте следующий скрипт в поле **Policy Document** (Документ политики), а затем нажмите кнопку **Create policy** (Создать политику).
  
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
  
9. Вернитесь на экран **Add user** (Добавление пользователя), при необходимости обновите список, выберите только что созданного пользователя и нажмите кнопку **Next Review** (Далее — просмотр).

   ![Просмотр политики пользователя в AWS](./media/aws-review-user.png "Review user in AWS")

10. Если все сведения указаны правильно, нажмите кнопку **Создать пользователя**.

    ![Разрешения пользователя в AWS](./media/aws-user-permissions.png "Review user permissions in AWS")

11. Когда отобразится сообщение об успешном выполнении, щелкните **Download .csv** (Скачать CSV-файл), чтобы сохранить копию новых учетных данных пользователя, которые потребуются позже.  

    ![Скачивание CSV-файла в AWS](./media/aws-download-csv.png "Download csv in AWS")
  
10. В консоли AWS щелкните **Службы** и затем в разделе **Средства управления** щелкните **CloudTrail**.  
  
     ![AWS CloudTrail](./media/aws-cloudtrail.png "AWS CloudTrail")  
  
    Если ранее вы не использовали CloudTrail, нажмите кнопку **Приступая к работе** и настройте этот компонент, указав имя и выбрав соответствующий сегмент S3. Затем щелкните **Turn On** (Включить). Чтобы обеспечить полное покрытие, задайте для параметра **Apply to all regions** (Применить ко всем регионам) значение **Да**.
  
       ![Включение CloudTrail в AWS](./media/aws-turnon-cloudtrail.png "Turn on CloudTrail in AWS")
  
    Вы увидите новое имя в CloudTrail в списке **Trails** (Журналы).
    
      ![Список CloudTrail в AWS](./media/aws-cloudtrail-list.png "CloudTrail list in AWS")
  
11. На портале Cloud App Security выберите пункты **Исследовать** и **Подключенные приложения**.  
  
12. На странице **App connectors** (Соединители с приложениями) щелкните знак "плюс", а затем — **AWS**.  
  
     ![подключение AWS](./media/connect-aws.png "подключение AWS")  
  
13. Во всплывающем окне вставьте значения параметров **Ключ доступа** и **Секретный ключ** из CSV-файла в соответствующие поля и нажмите кнопку **Подключить**.  
   ![Подключение приложения AWS](./media/aws-connect-app.png "Connect AWS app") 
  
14. Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. Когда проверка завершится, вы получите уведомление об успешном или неудачном выполнении. После получения уведомления об успешном выполнении нажмите кнопку **Готово**.  
  
После подключения AWS вы получите данные о событиях за 7 дней, предшествовавших подключению. Если вы только что подключили CloudTrail, вы получите данные о событиях с момента подключения.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Получить техническую поддержку можно на странице службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  