---
title: Защита конфиденциальности пользователей в Cloud App Security при помощи анонимизации данных | Microsoft Docs
description: В этой статье рассказывается об анонимизации имен пользователей в данных Cloud Discovery.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: eb250ede-fede-4699-a08b-b8ea4b232f07
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 86ca11744cf602aac979fafa0577731da8fbf277
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
*Область применения: Microsoft Cloud App Security*


# <a name="cloud-discovery-data-anonymization"></a>Анонимизация данных Cloud Discovery

Анонимизация данных Cloud Discovery позволяет защищать конфиденциальность пользователей. После отправки журнала данных на портал Microsoft Cloud App Security из журнала удаляются имена пользователей и заменяются зашифрованными именами пользователей. Таким образом, все действия в облаке остаются анонимными. При необходимости администраторы смогут раскрыть имя пользователя для служебного расследования (например, при нарушении целостности системы безопасности или при подозрительных действиях со стороны пользователя). Если администратор имеет основания подозревать конкретного пользователя, он также может использовать в своем расследовании зашифрованное имя пользователя. Преобразование каждого имени пользователя фиксируется в **журнале управления** на портале.

Основные моменты:
-   Персональные данные не хранятся и не отображаются. Все данные зашифрованы.
-   Закрытые данные шифруются при помощи стандарта AES-128. Для каждого клиента — свой ключ.
-   Определение настоящего имени пользователя выполняется только для конкретного случая путем расшифровки указанного зашифрованного имени пользователя.


Как работает анонимизация данных

1. Существует три способа применения анонимизации данных. 
    
   - Вы можете настроить анонимизацию данных для определенного файла журнала, [создав отчет с моментальным снимком](create-snapshot-cloud-discovery-reports.md) и выбрав **Анонимизировать закрытую информацию**.

     ![Анонимизация данных снимка](./media/anonymize-log.png)

   - Вы можете настроить анонимизацию данных из [автоматической отправки источника данных](configure-automatic-log-upload-for-continuous-reports.md). Для этого выберите **Anonymize private information** (Анонимизировать закрытую информацию) при добавлении нового источника данных.  
  
     ![Анонимизация данных журнала](./media/anonymize-autolog.png)

   - Чтобы настроить в Cloud App Security анонимизацию по умолчанию для всех данных как из отчетов со снимками данных из отправленных файлов журналов, так и из непрерывных отчетов от сборщиков данных журналов, сделайте следующее:
     
     1. В меню шестеренки "Параметры" выберите **Cloud Discovery settings** (Параметры Cloud Discovery).
     
     2. На вкладке Anonymization (Анонимизация) выберите **Anonymize private information by default in new reports and data sources** (Анонимизировать закрытую информацию по умолчанию в новых отчетах и источниках данных). Имена пользователей будут анонимизироваться по умолчанию.

     3. В разделе "Ключ шифрования" выберите **выделенный ключ, созданный для портала**, или **настраиваемый ключ**. Если вы решили **использовать настраиваемый ключ**, введите 16-байтовый ключ шифрования UTF8.
     4. Нажмите кнопку **Сохранить**.
 
        ![Анонимизация](./media/anonymizer1.png)
  

2. При включении анонимизации Cloud App Security анализирует журнал трафика и извлекает определенные атрибуты данных.
3. Cloud App Security заменяет имя пользователя на зашифрованное.
4. Затем Cloud App Security анализирует данные об использовании облака и создает отчеты на основе анонимизированных данных.
 
   ![Анонимизация панели мониторинга Cloud Discovery](./media/anonymize-dashboard.png)
 
5. Для конкретного расследования, например для расследования оповещения об аномальном использовании, можно раскрыть имя определенного пользователя на портале, предоставив деловое обоснование. 
   На этой странице также можно найти зашифрованное имя пользователя, если известно реальное. 

   1. В меню шестеренки "Параметры" выберите **Cloud Discovery settings** (Параметры Cloud Discovery).
   2. На вкладке **Anonymization** (Анонимизация) в поле **Anonymize and resolve usernames** (Анонимизация и раскрытие имен пользователей) укажите обоснование раскрытия.
   3. В поле **Enter username to resolve** (Введите имя пользователя для раскрытия) выберите **From anonymized** (Из анонимизированного) и введите анонимизированное имя или выберите **To anonymized** (В аномизированное) и введите исходное имя пользователя. Нажмите кнопку **Resolve** (Раскрыть). 

   ![Анонимизация](./media/anonymizer.png)

6. Это действие фиксируется в **журнале управления** на портале. 

    ![Анонимизация](./media/anonymize-gov-log.png)




  
      
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
    
      
  
