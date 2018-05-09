---
title: Видео. Настройка Office Web Apps для SharePoint 2013
TOCTitle: Видео. Настройка Office Web Apps для SharePoint 2013
ms:assetid: 0c02633f-3839-448b-ae83-24f24c254179
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn455088(v=office.15)
ms:contentKeyID: 59152170
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Видео. Настройка Office Web Apps для SharePoint 2013

 

_**Применимо к:**Office Web Apps, Office Web Apps Server, SharePoint Foundation 2013, SharePoint Server 2013_

_**Последнее изменение раздела:**2016-12-16_

**Сводка**. Описание девяти шагов для настройки работы фермы сервера Office Web Apps с SharePoint 2013.

Настройка Office Web Apps для SharePoint 2013 — довольно простой процесс. В этом видео показано, как установить Сервер Office Web Apps и настроить SharePoint 2013 для использования Сервер Office Web Apps в тестовой среде.


**Посмотреть видео "Настройка Office Web Apps для SharePoint 2013".**

> [!VIDEO https://www.microsoft.com/ru-ru/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

В этом видео рассматриваются процедуры, выполняемые на двух серверах: на сервере с Сервер Office Web Apps и сервере с SharePoint 2013. Это должны быть отдельные серверы, как описано в статье [Требования к конфигурации, программному и аппаратному обеспечению для сервера Office Web Apps](plan-office-web-apps-server.md).

**В видео показано, как выполнить на сервере с Сервер Office Web Apps следующие задачи.**

1\. Открыть командную строку Windows PowerShell и установить необходимые роли и службы для Сервер Office Web Apps. См. раздел [Подготовка серверов к использованию сервера Office Web Apps](deploy-office-web-apps-server.md). Это необходимо, так как Сервер Office Web Apps не установится, если нужные роли и службы отсутствуют.  
2\. Установить программное обеспечение Сервер Office Web Apps, скачав его на веб-сайте [Volume Licensing Service Center (VLSC)](http://go.microsoft.com/fwlink/p/?linkid=256561). Чтобы можно было скачать Сервер Office Web Apps, необходима лицензия на Office профессиональный плюс 2013, Office стандартный 2013 или Office для Mac 2011, предусмотренная соглашением о корпоративном лицензировании. Загружаемые файлы находятся в разделах на портале VLSC, посвященных продуктам Office.  
3\. Создать ферму Сервер Office Web Apps с помощью команды [New-OfficeWebAppsFarm](new-officewebappsfarm.md).  
4\. Убедиться, что ферма Сервер Office Web Apps успешно создана, открыв окно браузера и перейдя по адресу http://*имя\_сервера*/hosting/discovery.

**В видео показано, как выполнить на сервере с SharePoint 2013 следующие задачи.**

5\. Открыть Командная консоль SharePoint 2013.  
6\. Создать привязку между Сервер Office Web Apps и SharePoint 2013 с помощью командлета [New-SPWOPIBinding](new-spwopibinding.md). Это позволяет настроить взаимодействие между сервером с SharePoint 2013 и сервером с Сервер Office Web Apps.  
7\. Просмотреть зону WOPI SharePoint 2013 с помощью [Get-SPWOPIZone](get-spwopizone.md). Этот шаг подчеркивает, что два сервера используют разные зоны WOPI: SharePoint 2013 использует internal-https, а Сервер Office Web Apps — internal-http. Необходимо применять правильные зоны, чтобы компонент Office Web Apps работал правильно.  
8\. Изменить зону WOPI для SharePoint 2013 с помощью [Set-SPWOPIZone](set-spwopizone.md) на internal-http.  
9\. Проверить работоспособность Office Web Apps, открыв документ Office в библиотеке документов SharePoint 2013.

Подробнее о каждом из этих шагов см. в соответствующих разделах статей [Развертывание сервера Office Web Apps](deploy-office-web-apps-server.md) и [Настройка Office Web Apps для SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md).

  - [Подготовка серверов для запуска сервера Office Web Apps](deploy-office-web-apps-server.md)

  - [Развертывание фермы Office Web Apps Server, состоящей из отдельного сервера, в тестовой среде](deploy-office-web-apps-server.md)

  - [Подготовка к настройке SharePoint 2013 для использования сервера Office Web Apps](configure-office-web-apps-for-sharepoint-2013.md)

  - [Настройка SharePoint 2013 для использования сервера Office Web Apps в тестовой среде посредством протокола HTTP](configure-office-web-apps-for-sharepoint-2013.md)

## См. также


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Планирование Office Web Apps (используется вместе с SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)  
[Работа Office Web Apps в локальной среде с SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

