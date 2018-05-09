---
title: Get-OfficeWebAppsFarm
TOCTitle: Get-OfficeWebAppsFarm
ms:assetid: 1f0704e1-a41d-40e6-a31b-08b1926ce811
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219434(v=office.15)
ms:contentKeyID: 49624469
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsFarm

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2013-12-18_

Возвращает сведения об объекте OfficeWebAppsFarm, участником которого является текущий сервер.

## Синтаксис

    Get-OfficeWebAppsFarm

## Подробное описание

Командлет **Get-OfficeWebAppsFarm** возвращает сведения об объекте OfficeWebAppsFarm, участником которого является текущий сервер. Этот объект представляет группу серверов, которые работают как один модуль, реализующий возможности редактирования и просмотра документов Office в Интернете. С командлетом **Get-OfficeWebAppsFarm** не используются какие-либо параметры.

## Параметры

## Типы входных данных

## Типы возвращаемых данных

## Пример

\------------------ПРИМЕР 1---------------------

    Get-OfficeWebAppsFarm

В этом примере возвращаются сведения об объекте OfficeWebAppsFarm.

\------------------ПРИМЕР 2---------------------

    (Get-OfficeWebAppsFarm).Machines

В этом примере возвращаются сведения о серверах, входящих в ферму Сервер Office Web Apps. К этим сведениям относятся состояние работоспособности и роли каждого сервера.

## См. также


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

