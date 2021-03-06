---
title: "Устранение неполадок с развертыванием Docker для Cloud Discovery | Microsoft Docs"
description: "Этот раздел описывает процесс изменения конфигурации контейнера Docker для Cloud Discovery на базе платформы Cloud App Security."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 776e834f-3c20-4d5f-9fab-4c5b975edb06
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b994661f0f875db100a0aa2eb293b88e637b89cb
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2018
---
# <a name="troubleshooting-the-cloud-app-security-cloud-discovery-docker"></a>Устранение неполадок с развертыванием Docker для Cloud Discovery

## <a name="changing-the-ftp-password"></a>Изменение FTP-пароля


1. Подключитесь к узлу сборщика журналируемых данных.

2.  Выполните команду `docker exec -it <collector name> pure-pw passwd <ftp user>`.

    1. Введите новый пароль.
    2. Введите новый пароль еще раз для подтверждения.
 
3.  Выполните `docker exec -it <collector name> pure-pw mkdb`, чтобы применить изменения.


  ![Изменение FTP-пароля](./media/ftp-connect.png)

## <a name="customize-certificate-files"></a>Настройка файлов сертификатов

Выполните эти действия для настройки файлов сертификата, которые используются для безопасного подключения к Cloud Discovery с использованием Docker.

1.  Откройте FTP-клиент и подключитесь к сборщику журналируемых данных.

  ![Подключение к FTP-клиенту](./media/ftp-connect.png)

2.  Перейдите к каталогу `ssl_update`.
3.  Отправьте файлы нового сертификата в каталог `ssl_update` (имена являются обязательными).

    ![Изменение FTP-пароля](./media/new-certs.png)

    1.  Для FTP требуется только один файл, содержащий данные ключа и сертификата (в этом порядке), с именем **pure-ftpd.pem**.
    
    2.  Для системного журнала требуются три файла: **ca.pem**, **server-key.pem** and **server-cert.pem**. Если хотя бы один из этих файлов отсутствует, обновление не будет выполнено.

4.  В терминале выполните команду `docker exec -t <collector name> update_certs`. Вы получите приблизительно такой же результат, как и на следующем снимке экрана.

    ![Изменение FTP-пароля](./media/update-certs.png)

## <a name="see-also"></a>См. также
[Развертывание Cloud Discovery](set-up-cloud-discovery.md)

[Клиенты с поддержкой Premier также могут выбрать Cloud App Security непосредственно на портале Premier.](https://premier.microsoft.com/)

