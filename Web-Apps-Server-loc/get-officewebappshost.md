---
title: Get-OfficeWebAppsHost
TOCTitle: Get-OfficeWebAppsHost
ms:assetid: a9b766a7-a15c-4bbf-9750-31719406d65f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219446(v=office.15)
ms:contentKeyID: 49624498
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsHost

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2013-12-18_

Возвращает список несущих доменов из списка разрешенных доменов для фермы Сервер Office Web Apps.

## Синтаксис

    Get-OfficeWebAppsHost

## Подробное описание

Командлет **Get-OfficeWebAppsHost** возвращает список доменов, для которых Сервер Office Web Apps разрешает запросы файловых операций, таких как получение файла, извлечение метаданных и изменение файла. Этот список, который называют списком разрешенных доменов, — компонент обеспечения безопасности, не позволяющий нежелательным узлам подключаться к ферме Сервер Office Web Apps и выполнять файловые операции без вашего ведома.

Подстановочный знак "\*" используется для любого домена в списке, чтобы также были разрешены запросы ко всем дочерним доменам. Например, если добавить в список домен contoso.com, Сервер Office Web Apps также разрешит запросы к доменам corp.contoso.com и dev.contoso.com. Запросы к другим доменам (например, fabrikam.com) не разрешены.


> [!WARNING]
> Если список разрешенных доменов пуст, Сервер Office Web Apps разрешает запросы файлов для узлов в любом домене. Не оставляйте этот список пустым, если ваша ферма Сервер Office Web Apps доступна из Интернета. В противном случае все смогут использовать вашу ферму Сервер Office Web Apps для просмотра и изменения контента.



## Параметры

## Типы входных данных

## Типы возвращаемых данных

## Пример

\------------------ПРИМЕР 1---------------------

    Get-OfficeWebAppsHost

В этом примере выполняется возвращение доменов из списка разрешенных доменов.

## См. также


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Remove-OfficeWebAppsHost](remove-officewebappshost.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

