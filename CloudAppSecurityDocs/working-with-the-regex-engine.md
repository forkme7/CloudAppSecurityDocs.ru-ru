---
title: "Использование обработчика регулярных выражений в политиках проверки содержимого | Microsoft Docs"
description: "В этом разделе приводятся инструкции по использованию регулярных выражений для сопоставления шаблонов в политиках Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: dc8b87e5-e6c1-4a65-ab8c-067fb527fce4
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1f6ee1a96a7f65c903fe6e0978fd9a31d850697e
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2018
---
# <a name="working-with-the-regex-engine"></a>Работа с подсистемой регулярных выражений
 
Политики проверки содержимого Cloud App Security используют регулярное выражение для сопоставления шаблонов. Проверка содержимого может применяться в рамках политик файлов. Для тестирования регулярных выражений можно использовать следующие веб-сайты:  
  
-   [http://regexpal.com/](http://regexpal.com/)  
  
     (Обязательно выберите обработку **без учета регистра**.)  
  
-   [https://regex101.com/](https://regex101.com/)  
  
     Предоставляет подробный анализ регулярных выражений.  
  
Для пользовательских регулярных выражений применяются следующие ограничения:  
  
-   Поиск всегда выполняется без учета регистра.  
   
-   Разрешенные квантификаторы: {n,m}, где n, m < 10.  
  
-   Все группы должны быть незахватываемыми, например: (?:xxx).  
  
     Вместо (группа) используйте (?:группа).  
  
-   Запрещенные квантификаторы: *, +, {n,}.  
  
     Вместо * используйте {0,9}.  
  
     Вместо + используйте {1,9}.  
  
-   Запрещенные обратные ссылки: \\<число\> или \k\<имя>.  
  
Примеры выражений  
  
||||  
|-|-|-|  
|**Регулярное выражение**|**Данные**|**Совпадения**|  
|Colou?r (?:black&#124;blue&#124;white)|Color black<br /><br /> Color white<br /><br /> Color red|Да<br /><br /> Да<br /><br /> Нет|  
|[a-z0-9]{1,9}@[a-z0-9]{1,9}\\.[a-z]{2,3}|Some1@abc.com<br /><br /> user@host.org<br /><br /> @bad.com|Да<br /><br /> Да<br /><br /> Нет|  
|20\d{2}-(?:0[1-9]&#124;1[0-2])-(?:[0-2][0-9]&#124;30&#124;31)|2015-12-31<br /><br /> 2015-01-09<br /><br /> 1999-12-31|Да<br /><br /> Да<br /><br /> Нет|  
|d.n't\s{0,10}c.r.|Don't     care<br /><br /> D!n'tcor0<br /><br /> Doesn't care|Да<br /><br /> Да<br /><br /> Нет|  
 

## <a name="see-also"></a>См. также  
[Ежедневные мероприятия для защиты облачной среды](daily-activities-to-protect-your-cloud-environment.md)   

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  

## <a name="check-out-this-video"></a>Посмотрите это видео!
[Работа с подсистемой регулярных выражений](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security-Working-with-the-Regex-Engine)    