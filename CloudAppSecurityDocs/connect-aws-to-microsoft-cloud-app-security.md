---
title: "Подключение AWS к Microsoft Cloud App Security | Документы Майкрософт"
description: "В этом разделе приводятся сведения о подключении приложения AWS к Cloud App Security с помощью соединителя API."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e41c04d25f12aa5207ef9ffbb6a22f4b894e92cb
ms.openlocfilehash: d78f324cc8fba6c45a49c1260c157fb4f4feaab7


---

# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Подключение AWS к Microsoft Cloud App Security
Этот раздел содержит инструкции по подключению Cloud App Security к существующей учетной записи Amazon Web Services с помощью интерфейсов API соединителя.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Порядок подключения Amazon Web Services к Cloud App Security  
  
1.  В консоли Amazon Web Services щелкните **Управление идентификацией и доступом**.  
  
     ![удостоверение и доступ к aws](./media/aws-identity-and-access.png "aws identity and access")  
  
2.  Откройте вкладку **Пользователи**.  
  
     ![пользователи aws](./media/aws-users.png "aws users")  
  
3.  Щелкните **Создание новых пользователей**.  
  
     ![Создание пользователя в AWS](./media/aws-create-user.png "AWS create user")  
  
4.  Создайте пользователя для Cloud App Security и установите флажок **Generate an access key for each user** (Создать ключ доступа для каждого пользователя).  
  
5.  Щелкните **Download Credentials** (Скачать учетные данные).  
  
     ![скачивание учетных данных в aws](./media/aws-dl-cred.png "aws dl cred")  
  
6.  На вкладке **Permissions** (Разрешения) нажмите кнопку **Attach Policy** (Присоединить политику).  
  
     ![присоединение политики пользователя в aws](./media/aws-attach-user-policy.png "aws attach user policy")  
  
7.  Откроется экран **Review Policy** (Просмотр политики).
 
     ![просмотр политики](./media/aws-review-policy.png "aws review policy")  
  

8. В поле **Policy Name** (Имя политики) введите "AdallomTrustPolicy". 
10. Скопируйте следующий фрагмент и вставьте его в области **Policy Document** (Документ политики):  
  
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
  
9. В скачанном файле `credentials.csv` найдите учетные данные нового пользователя. Позднее они еще понадобятся.  
  
10. Вернитесь на главную страницу консоли AWS и в правом верхнем углу выберите свой основной регион из раскрывающегося списка, а затем выберите **CloudTrail** в главном меню.  
  
     ![cloudtrail aws](./media/aws-cloudtrail.png "aws cloudtrail")  
  
    1.  Если ранее вы не использовали CloudTrail для этого региона, нажмите кнопку **Приступая к работе** и настройте этот компонент, выбрав соответствующий сегмент S3.  
  
         Откройте вкладку **Конфигурация** в верхней левой части экрана. В разделе **Дополнительная конфигурация** щелкните значок правки.  
  
         ![конфигурация cloudtrail в aws](./media/aws-cloudtrail-config.png "aws cloudtrail config")  
  
    2.  Щелкните **Да** при отображении вопроса о **включении глобальных служб** и нажмите кнопку **Сохранить**. Это касается только выбранного региона.  
  
         ![включение глобальных служб в aws](./media/aws-include-global-svc.png "aws include global svc")  
  
    3.  Повторите шаг 11 для всех регионов, не включая глобальные службы ни для одного из остальных регионов.  
  
11. На портале Cloud App Security выберите пункты **Исследовать** и **Подключенные приложения**.  
  
12. На странице **Соединители приложений** нажмите кнопку **Подключить приложение**, а затем — **AWS**.  
  
     ![подключение AWS](./media/connect-aws.png "connect AWS")  
  
13. Во всплывающем окне вставьте **Ключ доступа** и **Секретный ключ** из CSV-файла в поля на странице API и нажмите кнопку **Обновить ключ доступа**.  
  
14. Убедитесь, что подключение установлено, щелкнув элемент **Тестирование API**.  
  
     Проверка может занять несколько минут. После завершения выдается уведомление об успехе или неудаче. После получения уведомления об успешном выполнении нажмите кнопку **Готово**.  
  
После подключения AWS вы получите события за 7 дней, предшествовавших подключению.
  
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier](https://premier.microsoft.com/).  
  
  


<!--HONumber=Nov16_HO4-->


