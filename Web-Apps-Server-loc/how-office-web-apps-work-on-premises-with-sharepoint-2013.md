---
title: Работа Office Web Apps в локальной среде с SharePoint 2013
TOCTitle: Работа Office Web Apps в локальной среде с SharePoint 2013
ms:assetid: 8480064e-14a4-4b46-ad6b-0c836b192af2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Ff431685(v=office.15)
ms:contentKeyID: 49624490
ms.date: 02/01/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Работа Office Web Apps в локальной среде с SharePoint 2013

_<strong>Применимо к:</strong> Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_<strong>Последнее изменение раздела:</strong> 2016-12-16_

**Сводка**. Сведения об Office Web Apps, получении сервера Office Web Apps и работе этих продуктов на локальных ресурсах вместе с SharePoint 2013.

**Аудитория:** ИТ-специалисты

При использовании вместе с SharePoint Server 2013, Сервер Office Web Apps предоставляет обновленные версии приложений Word Web App, Excel Web App, PowerPoint Web App и OneNote Web App. Пользователи могут просматривать и, в некоторых случаях, редактировать документы Office в библиотеках SharePoint с использованием поддерживаемых веб-браузеров на компьютерах и многих мобильных устройствах, таких как Windows Phone, iPhone, iPad, планшеты Windows 8 и устройства Android.


**Рисунок. Возможности просмотра и редактирования в Office Web Apps на различных типах устройств.**

![Рисунок, на котором показаны возможности просмотра и редактирования в Office Web Apps на различных типах устройств. Выделены возможности, оптимизированные для сенсорных экранов.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "Рисунок, на котором показаны возможности просмотра и редактирования в Office Web Apps на различных типах устройств. Выделены возможности, оптимизированные для сенсорных экранов.")

## Сервер Office Web Apps устанавливается как изолированный сервер

Office Web Apps не устанавливается на тех же серверах, где работает SharePoint 2013. Вместо этого следует развернуть один или несколько физических или виртуальных серверов, где работает Сервер Office Web Apps. Затем следует настроить ферму SharePoint 2013 для использования фермы Сервер Office Web Apps в целях предоставления функциональных возможностей Office Web Apps пользователям, которые создают или открывают файлы Office в библиотеках SharePoint. Дополнительные сведения см. в разделе [Обзор сервера Office Web Apps](office-web-apps-server-overview.md).

## Варианты лицензирования Office Web Apps при использовании SharePoint 2013

Предлагается два способа лицензирования Office Web Apps:

  - **Только просмотр**. По умолчанию Office Web Apps предлагается бесплатно и только с разрешениями на просмотр.

  - **Редактирование и просмотр**. Необходимо приобрести лицензию на редактирования, чтобы воспользоваться функциональными возможностями редактирования в Office Web Apps вместе с SharePoint 2013. Редактирование включается при создании фермы Сервер Office Web Apps.

Если у вашей организации есть лицензии на Office 2013 в рамках программы корпоративного лицензирования, вы можете включить редактирование с использованием Office Web Apps для SharePoint 2013 локально. Это помогает обеспечить пользователям возможности редактирования, предоставляемые Office, при работе из дома или других мест, в которых клиенты Office могут быть не установлены. Лицензии с правом на редактирование для Office Web Apps невозможно приобрести отдельно.

Точные сведения о вашей лицензии см. в условиях лицензионного соглашения на использование программного обеспечения корпорации Майкрософт, которые отображаются при установке Сервер Office Web Apps.

SharePoint 2013 предоставляет новую реализацию лицензий, которая поддерживается для Office Web Apps. Если включить лицензирование SharePoint, а затем включить редактирование Office Web Apps, только пользователи, имеющие соответствующую лицензию, смогут редактировать файлы Office в браузере. Если пользователи не имеют лицензий на редактирование Office Web Apps, поддерживается только просмотр.

Дополнительные сведения о лицензировании в SharePoint 2013 можно найти в статье [Настройка лицензирования в SharePoint Server 2013](https://technet.microsoft.com/ru-ru/library/jj219627\(v=office.15\)). Параметр EditingEnabled, который включает редактирование, описан в статьях [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) и [Set-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/set-officewebappsfarm?view=officewebapps-ps).

Файлы, отправляемые с помощью функции "Поделиться ссылкой" в SharePoint 2013, можно редактировать в Office Web Apps даже при отсутствии лицензии на редактирование и в тех случаях, когда редактирование отключено на уровне фермы серверов Сервер Office Web Apps.

## Использование средств просмотра Office Mobile Viewer для доступа к файлам на сайтах SharePoint

Сервер Office Web Apps предоставляет средства просмотра Office Mobile Viewer, чтобы предоставить доступ к Office Web Apps мобильным пользователям, посещающим сайты SharePoint Server. Эти средства по умолчанию включены, но их может отключить администратор сайта SharePoint Server. Если они включены, пользователи могут перейти на сайт SharePoint Server в браузере на мобильном устройстве, выбрать нужный документ в библиотеке SharePoint Server, после чего он откроется в мобильном браузере.

Дополнительные сведения о работе библиотек SharePoint на мобильных устройствах см. в статьях [What's new for mobile devices in SharePoint 2013](https://technet.microsoft.com/ru-ru/library/fp161352\(v=office.15\)) and [Обзор мобильных устройств и SharePoint Server 2013](https://technet.microsoft.com/ru-ru/library/fp161351\(v=office.15\)). Пользователи могут ознакомиться с принципами работы средств просмотра Office Mobile Viewer на мобильных устройствах, изучив статью [Использование приложений Office Web Apps на телефоне Android, iPhone или Windows Phone](http://go.microsoft.com/fwlink/p/?linkid=271045). Чтобы отключить средства просмотра Office Mobile Viewer в SharePoint 2013, используйте командлет [Remove-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Remove-SPWOPIBinding?view=sharepoint-ps).

## Различия между Excel Web App и службами Excel в SharePoint

У продуктов Excel Web App и Службы Excel в SharePoint много общего, но они не одинаковы. Службы Excel доступен только в выпуске Enterprise SharePoint Server 2013. Excel Web App доступен в SharePoint Server 2013 и SharePoint Foundation 2013. Оба приложения позволяют просматривать книги Excel в браузере, взаимодействовать с данными и анализировать их.

Однако между Excel Web App и Службы Excel в SharePoint есть ряд отличий. Например, Службы Excel поддерживают подключение к внешним данным, модели данных и возможность взаимодействия с элементами, использующими модели данных (такими как отчеты сводной диаграммы, отчеты сводной таблицы и элементы управления временной шкалы). Службы Службы Excel предоставляют большие возможности бизнес-аналитики, чем Excel Web App, но службы Службы Excel не разрешают пользователям создавать и редактировать книги в окне браузера.

Дополнительные сведения об отличиях Excel Web App и Службы Excel см. в статьях [Обзор служб Excel в SharePoint Server 2013](https://technet.microsoft.com/ru-ru/library/ee424405\(v=office.15\)) и [Сравнение служб Excel в SharePoint с приложением Excel Web App](http://go.microsoft.com/fwlink/p/?linkid=255460).

Если в организации решено использовать службы Службы Excel вместо Excel Web App для просмотра книг в браузере, можно использовать командлет Windows PowerShell **New-SPWOPISuppressionSettings** для отключения Excel Web App для книг Excel. Подробнее см. в статье [New-SPWOPISuppressionSetting](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPISuppressionSetting?view=sharepoint-ps).

## См. также


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Планирование Office Web Apps (используется вместе с SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)  
  

[](plan-office-web-apps-used-with-sharepoint-2013.md)

