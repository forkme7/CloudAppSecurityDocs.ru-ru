---
title: "Интеграция Azure Information Protection с Cloud App Security | Microsoft Docs"
description: "В этой статье приведены сведения о том, как использовать теги Azure Information Protection в Cloud App Security для более эффективного использования облачных приложений в вашей организации."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/19/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 81ee0b71e6e66d102edf41269197d955b16fbeb4
ms.sourcegitcommit: 0d4748ea2a71e6ee2b0fa1c0498d9219bfbda29a
translationtype: HT
---
# <a name="azure-information-protection-integration"></a>Интеграция Azure Information Protection

Cloud App Security позволяет исследовать файлы и задавать политики на основе меток классификации в Azure Information Protection. Это дает вам большую осведомленность о конфиденциальных данных в облаке и позволяет более эффективно управлять ими. Процесс интеграции Azure Information Protection с Cloud App Security прост: нужно установить всего один флажок. 

Благодаря интеграции Azure Information Protection с Cloud App Security вы сможете максимально эффективно использовать возможности обеих служб и защищать файлы в облаке; вы также получаете доступ к следующим полезным возможностям:
- возможность централизованно просматривать все классифицированные файлы;
- возможность выполнять исследования согласно уровню классификации и оценивать уровни рисков для конфиденциальных данных в облачных приложениях;
- возможность создавать политики, гарантирующие правильную обработку классифицированных файлов.

> [!NOTE] 
> Для включения этой функции вам необходимы лицензия Cloud App Security и лицензия Azure Information Protection Premium P1 или P2. Если у вас есть обе лицензии, Cloud App Security будет синхронизировать метки организации из службы Azure Information Protection.

## <a name="how-it-works"></a>Принцип работы
Возможно, вы знакомы с метками классификации файлов [Azure Information Protection](https://docs.microsoft.com/information-protection/). Теги классификации Azure Information Protection видны в Cloud App Security. После интеграции службы Cloud App Security с Azure Information Protection эта служба сканирует файлы следующим образом:
1. Cloud App Security извлекает список всех меток классификации, используемых в вашем клиенте. Чтобы список оставался актуальным, это следует делать каждый час.
2. Затем Cloud App Security проверяет файлы на наличие меток классификации следующим образом. a. Если включено автоматическое сканирование (см. ниже), все новые или измененные файлы будут добавляться в очередь сканирования.
    b. Если настроена политика обработки файлов (см. ниже) для поиска меток классификации, эти файлы будут добавляться в очередь сканирования меток классификации.
3. Как отмечалось выше, эти проверки обрабатывают метки классификации, обнаруженные в ходе первоначального сканирования, выполняемого Cloud App Security, чтобы найти метки классификации, используемые в клиенте. Внешние метки (метки классификации, заданные внешней стороной, по отношению к клиенту) добавляются в список меток классификации. Если наличие этих меток проверять не требуется, установите флажок **Only scan files for Azure Information Protection classification labels from this tenant** (Сканировать файлы на наличие меток классификации Azure Information Protection только от этого клиента) (см. ниже).
4. После включения Azure Information Protection в Cloud App Security все новые файлы, добавляемые в Office 365, также будут сканироваться на наличие меток классификации.

## <a name="how-to-integrate-azure-information-protection-with-cloud-app-security"></a>Как интегрировать Azure Information Protection с Cloud App Security
  
### <a name="enable-azure-information-protection"></a>Включение Azure Information Protection

Чтобы интегрировать Azure Information Protection с Cloud App Security, нужно включить автоматическое сканирование для поиска меток классификации Azure Information Protection в файлах Office 365, при этом политику создавать не требуется. После включения этой функции файлы, существующие в вашей облачной среде и имеющие метки классификации Azure Information Protection, появятся в Cloud App Security.

Включение Cloud App Security для сканирования файлов с проверкой содержимого на наличие меток классификации

1. В Cloud App Security в меню-шестеренке "Параметры" выберите страницу **Общие параметры**.
2. В Azure Information Protection выберите пункт **Автоматически сканировать файлы на наличие меток классификации Azure Information Protection**. 

После включения Azure Information Protection станут видны файлы с метками классификации, по которым их можно будет фильтровать в Cloud App Security.

 ![включение Azure Information Protection](./media/enable-azip.png)

> [!NOTE] 
> Автоматическое сканирование будет сканировать существующие файлы только после повторного их изменения. Чтобы проверить существующие файлы на наличие меток классификации Azure Information Protection, необходима по крайней мере одна **политика изучения содержимого файлов**. Если таковых нет, создайте **политику обработки файлов**, удалите все стандартные фильтры и установите флажок **Content inspection** (Изучение содержимого). В разделе **Content inspection** (Изучение содержимого) щелкните **Include files that match a preset expression** (Включать файлы, соответствующие предварительно заданному значению), выберите такое значение и сохраните политику. Будет включено изучение содержимого, в рамках которого будут автоматически обнаруживаться метки классификации Azure Information Protection.

### <a name="set-internal-and-external-tags"></a>Задание внутренних и внешних тегов
По умолчанию Cloud App Security будет сканировать метки классификации, которые были определены в вашей организации, а также внешние метки, которые были определены другими организациями. 

Чтобы игнорировать метки классификаций других организаций, на портале Cloud App Security в разделе **Общие параметры**, **Azure security settings** (Параметры безопасности Azure) выберите пункт **Ignore Azure Information Protection classification labels from other tenants** (Игнорировать метки классификации Azure Information Protection от других клиентов).
 
![игнорировать метки](./media/azip-ignore.png)

### <a name="control-file-exposure"></a>Управление видимостью файлов
- Если это — документ, отмеченный меткой классификации Azure Information Protection:

![пример окна Azure Information Protection](./media/azip-screen.png)

- Вы сможете увидеть этот файл в Cloud App Security на странице **Файлы**, отфильтровав содержимое по метке классификации.

![Cloud App Security по сравнению с Azure Information Protection](./media/cas-compared-azip.png)

- Дополнительные сведения об этих файлах и их метках классификации находятся в контейнере файлов.

- На странице **Файлы** щелкните нужный файл, чтобы посмотреть, есть ли у него метки классификации.

![контейнер файлов](./media/azip-file-drawer.png)

- Щелкните метку классификации, чтобы ознакомиться с дополнительными сведениями или отобразить полный список меток классификации.
 
![список тегов](./media/azip-tags-list.png)

- Затем можно создать политики обработки файлов в Cloud App Security, которые не должны предоставляться определенным лицам, и файлов, которые были отмечены и недавно изменены.
- Кроме того, вы можете активировать оповещения о действиях, связанных с конфиденциальными файлами.

![Теги Azure Information Protection в Cloud App Security](./media/azip-tags-in-cas.png)

> ![Примечание] Метки защиты идентификации Azure, отключенные в файле, будут отображаться как отключенные в Cloud App Security. Удаленные метки не отображаются.
> **Политика 1 — конфиденциальные данные на компьютере с доступом извне:**

1.    Создайте политику файла.
2.    Задайте название, уровень серьезности и категорию политики.
3.    Добавьте следующие фильтры для поиска всех конфиденциальных данных на компьютере с доступом извне:

![политика конфиденциальности](./media/azip-confidentiality-policy.png) 

**Политика 2 — защищенные данные SharePoint, которые недавно были изменены, за исключением папки "Финансы":**

1.    Создайте политику файла.
2.    Задайте название, уровень серьезности и категорию политики.
3.    Добавьте следующие фильтры для поиска всех защищенных данных, которые были недавно изменены, и исключите папку "Финансы" в поле для выбора папки: 
 
![политика защищенных данных](./media/azip-restricted-data-policy.png) 

Также можно настроить уведомления, оповещения пользователя или немедленно принимать какие-либо меры по этим политикам.
Ознакомьтесь с дополнительными сведениями о [действиях управления](governance-actions.md).

Ознакомьтесь с дополнительными сведениями об [Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-information-protection) и изучите [Руководство по началу работы с Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/get-started/infoprotect-quick-start-tutorial).

 
## <a name="see-also"></a>См. также  
[Управление облачными приложениями с помощью политик](control-cloud-apps-with-policies.md)   
[Для получения технической поддержки посетите страницу службы технической поддержки Cloud App Security.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)  
  
