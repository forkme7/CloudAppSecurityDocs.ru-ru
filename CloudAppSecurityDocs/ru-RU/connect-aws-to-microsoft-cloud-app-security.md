---
title: Подключение AWS к Cloud App Security для видимости и контроля использования | Документы Майкрософт
description: В этом разделе приводятся сведения о подключении приложения AWS к Cloud App Security с помощью соединителя API.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 64c3ac8cea662aa1eab69f46f5d226bc585e5e83
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*

# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Подключение AWS к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Microsoft Cloud App Security к существующей учетной записи Amazon Web Services с помощью интерфейсов API соединителя.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Порядок подключения Amazon Web Services к Cloud App Security  
  
1.  В [консоли Amazon Web Services](https://console.aws.amazon.com/) в разделе **Безопасность, идентификация и соответствие** щелкните **IAM**.  
  
     ![Идентификация и доступ AWS](./media/aws-identity-and-access.png "AWS identity and access")  
  
2.  Откройте вкладку **Пользователи** и нажмите кнопку **Добавить пользователя**.  
  
     ![Пользователи AWS](./media/aws-users.png "AWS users")      
  
4.  На шаге **Details** (Сведения) введите имя пользователя для Cloud App Security. В поле **Access type** (Тип доступа) установите флажок **Programmatic access** (Программный доступ) и нажмите кнопку **Далее разрешения** (Далее — разрешения).  

     ![Создание пользователя в AWS](./media/aws-create-user.png "Create user in AWS")

5. Откройте вкладку "JSON".

     ![AWS JSON](./media/aws-json.png "Вкладка AWS JSON")

6. Вставьте следующий сценарий в указанную область.

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

     ![Код AWS](./media/aws-code.png "Код AWS")
    
6. Щелкните **Просмотр политики**.

7. Укажите **Имя** и нажмите кнопку **Создать политику**.

     ![Назначение имени для политики AWS](./media/aws-create-policy.png "Создание политики AWS")

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

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
  