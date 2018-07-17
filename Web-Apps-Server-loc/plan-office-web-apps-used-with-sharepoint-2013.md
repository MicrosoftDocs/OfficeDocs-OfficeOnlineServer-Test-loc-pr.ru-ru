﻿---
title: Планирование Office Web Apps (используется вместе с SharePoint 2013)
TOCTitle: Планирование Office Web Apps
ms:assetid: 3bd0a617-5f12-4a7e-bb75-b15c86c7e504
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Ff431682(v=office.15)
ms:contentKeyID: 49624478
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Планирование Office Web Apps (используется вместе с SharePoint 2013) 

_<strong>Применимо к:</strong> Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_<strong>Последнее изменение раздела:</strong> 2016-12-16_

**Сводка**. Общие рекомендации по планированию Office Web Apps при локальном использовании с SharePoint 2013.

**Аудитория:** ИТ-специалисты

При планировании локального использования Office Web Apps с SharePoint 2013следует обратить внимание на поддержку браузера, требования к проверке подлинности SharePoint и вопросы лицензирования для просмотра и редактирования файлов Office с помощью Office Web Apps. Далее следует определить, будет ли SharePoint 2013 использовать веб-браузер или клиентское приложение при открытии файлов Office из библиотеки документов SharePoint 2013.

> [!IMPORTANT]
> Эта статья входит в раздел <a href="content-roadmap-for-office-web-apps-server.md">План содержимого для сервера Office Web Apps</a>. Используйте этот обзор в качестве отправной точки для поиска статей, загружаемых файлов и видеозаписей, рассказывающих о том, как развертывать и управлять Сервер Office Web Apps.<br />
<strong>Необходима справка по Office Web Apps для настольного компьютера или мобильного устройства?</strong> Чтобы найти эти сведения, можно выполнить поиск по ключевым словам &quot;Office Web Apps&quot; на веб-сайте <a href="http://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</a>.


В этой статье

  - Планирование Office Web Apps

  - Поддержка браузера в Office Web Apps

  - Требования к проверке подлинности SharePoint для Office Web Apps

  - Лицензирование Office Web Apps для редактирования файлов Office

  - Рекомендации для клиентов, развернувших Office Web Apps с SharePoint 2010

  - Используемый по умолчанию способ открытия документов из библиотеки документов SharePoint 2013

## Планирование Office Web Apps

В этой статье приводится часть рекомендаций по общему планированию локального развертывания Сервер Office Web Apps в вашей организации. В процессе планирования Сервер Office Web Apps необходимо учитывать, помимо прочего, требования к оборудованию, программному обеспечению, виртуализации, масштабированию и топологии фермы, а также к обеспечению безопасности. После принятия соответствующих решений вы можете приступить к планированию конфигурации функций Office Web Apps, относящихся к SharePoint 2013. Если вы еще не знакомы с требованиями и рекомендациями по планированию Сервер Office Web Apps, изучите статьи [Обзор сервера Office Web Apps](office-web-apps-server-overview.md) и [Планирование сервера Office Web Apps](plan-office-web-apps-server.md).

## Поддержка браузера в Office Web Apps

Office Web Apps поддерживает те же браузеры, что и SharePoint 2013. Подробнее см. в статье [Планирование поддержки браузеров в SharePoint 2013](https://technet.microsoft.com/ru-ru/library/cc263526\(v=office.15\)).

## Требования к проверке подлинности SharePoint для Office Web Apps

Office Web Apps может работать только с веб-приложениями SharePoint 2013, использующими проверку подлинности на основе утверждений. Функции визуализации и редактирования Office Web Apps не работают в веб-приложениях SharePoint 2013 с классическим режимом проверки подлинности. При переносе веб-приложений SharePoint 2010 с классическим режимом проверки подлинности в SharePoint 2013 для обеспечения их работы с Office Web Apps необходимо выполнить переход на проверку подлинности на основе утверждений. Подробнее см. в статье [Настройка проверки подлинности на основе утверждений для веб-приложения с классическим режимом проверки подлинности в SharePoint 2013](https://technet.microsoft.com/ru-ru/library/gg251985\(v=office.15\)).

## Лицензирование Office Web Apps для редактирования файлов Office

Клиенты-организации, получившие лицензии на Office 2013 в рамках программы корпоративного лицензирования, могут включить редактирование с использованием Office Web Apps для SharePoint 2013 локально. Так пользователи смогут редактировать документы в Office при работе дома или где-то еще — там, где клиенты Office могут быть не установлены.

Точные сведения о вашей лицензии указаны в условиях лицензионного соглашения на использование программного обеспечения корпорации Майкрософт, которые отображаются при установке Сервер Office Web Apps. Дополнительные сведения об особенностях лицензирования в SharePoint 2013 см. в статье [Настройка лицензирования в SharePoint Server 2013](https://technet.microsoft.com/ru-ru/library/jj219627\(v=office.15\)).

## Рекомендации для клиентов, использующих способ переподключения баз данных для обновления от SharePoint 2010

При установке Office Web Apps вместе с SharePoint 2010 приложения Office Web Apps не будут доступны после обновления до SharePoint 2013. Необходимо развернуть сервер Сервер Office Web Apps, а затем подключить к нему SharePoint 2013 после обновления баз данных контента. Обновления семейств веб-сайтов ждать не нужно, поскольку сервер Сервер Office Web Apps поддерживает для семейств сайтов режимы 2010 и 2013 в SharePoint 2013. Подробнее о способе переподключения баз данных см. в статье [Обзор процесса обновления до SharePoint 2013](https://technet.microsoft.com/ru-ru/library/cc262483\(v=office.15\)).

## Используемый по умолчанию способ открытия документов из библиотеки документов SharePoint 2013

Вы можете настроить открытие файлов Word, PowerPoint, Excel и OneNote в установленном клиентском приложении или браузере. По умолчанию после настройки SharePoint 2013 для работы с Сервер Office Web Apps файлы Office открываются в браузере. Изменить настройки по умолчанию для непосредственного открытия файлов в клиентских приложениях можно двумя способами:

  - **Для фермы SharePoint 2013**. В ферме SharePoint 2013 вы можете настроить способ открытия по умолчанию для каждого типа файла с помощью командлетов [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps) и [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps)Windows PowerShell.

  - **Для семейств сайтов и библиотек документов**. Пользователи и администраторы семейств веб-сайтов могут настраивать открытие файлов Office в установленных клиентских приложениях. Пользователи изменяют соответствующие настройки в свойствах библиотеки документов, а администраторы семейства веб-сайтов — в центре администрирования семейства или с помощью командлета Install-SPFeature, который устанавливает компонент OpenInClient. Подробнее см. в статье [Install-SPFeature](https://technet.microsoft.com/ru-ru/library/ff607825\(v=office.15\)).

## См. также


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Работа Office Web Apps в локальной среде с SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  


[Настройка SharePoint 2013 Preview для использования предварительной версии сервера Office Web Apps Server Preview в тестовой среде на базе протокола HTTP](configure-office-web-apps-for-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

