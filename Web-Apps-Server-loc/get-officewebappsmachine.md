---
title: Get-OfficeWebAppsMachine
TOCTitle: Get-OfficeWebAppsMachine
ms:assetid: 02fadf5e-0382-4e73-8d07-e67d088b1a02
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219432(v=office.15)
ms:contentKeyID: 49624466
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsMachine

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2013-12-18_

Возвращает подробные сведения о текущем сервере в ферме Сервер Office Web Apps.

## Синтаксис

    Get-OfficeWebAppsMachine

## Подробное описание

Командлет **Get-OfficeWebAppsMachine** возвращает подробные сведения о текущем сервере в ферме Сервер Office Web Apps. Среди них доступны сведения о ролях и состоянии работоспособности текущего сервера, а также имя главного сервера фермы.

## Параметры

## Типы входных данных

## Типы возвращаемых данных

## Пример

\------------------ПРИМЕР 1---------------------

    Get-OfficeWebAppsMachine

В этом примере возвращаются подробные сведения о текущем сервере в ферме Сервер Office Web Apps.

\------------------ПРИМЕР 2---------------------

    (Get-OfficeWebAppsFarm).Machines

В этом примере возвращаются подробные сведения обо всех серверах в ферме Сервер Office Web Apps.

## См. также


[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

