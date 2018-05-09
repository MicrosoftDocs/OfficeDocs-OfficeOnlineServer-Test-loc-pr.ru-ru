---
title: Get-SPWOPIBinding
TOCTitle: Get-SPWOPIBinding
ms:assetid: b757301b-f6c5-43a5-a8ca-2ef33ede0ae8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219450(v=office.15)
ms:contentKeyID: 49624507
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-SPWOPIBinding

 

_**Применимо к:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Последнее изменение раздела:**2015-03-09_

Возвращает список привязок, созданных с помощью **New-SPWOPIBinding** в текущей ферме SharePoint, где выполняется данный командлет.

## Синтаксис

    Get-SPWOPIBinding [-Action <String>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Extension <String>] [-ProgId <String>] [-Server <String>] [-WOPIZone <String>]

## Подробное описание

**Get-SPWOPIBinding** возвращает список привязок, созданных с помощью **New-SPWOPIBinding** в текущей ферме SharePoint, где выполняется этот командлет. Результаты включают действия, приложения, типы файлов и зоны, настроенные для приложения WOPI (например, сервер под управлением Сервер Office Web Apps).

Командная консоль SharePoint

## Параметры


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр</th>
<th>Обязательный?</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Action</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает действие, для которого возвращаются привязки.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает приложение, для которого возвращаются привязки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Управляет объектами в целях надлежащего удаления. При использовании таких объектов, как <strong>SPWeb</strong> и <strong>SPSite</strong>, может расходоваться много памяти. Для их использования в скриптах Windows PowerShell требуется надлежащее управление памятью. Вы можете назначать объекты <strong>SPAssignment</strong> переменной, а также удалять ненужные объекты, чтобы освободить память. Объекты <strong>SPWeb</strong>, <strong>SPSite</strong> и <strong>SPSiteAdministration</strong> удаляются автоматически, если не используется коллекция назначений или параметр <strong>Global</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>При использовании параметра <strong>Global</strong> все объекты содержатся в глобальном хранилище. Если объекты не используются сразу или удаляются с помощью команды <strong>Stop-SPAssignment</strong>, может возникнуть нехватка памяти.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>Extension</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает расширения файлов, для которых возвращаются привязки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает программный идентификатор (ProgID) приложения, для которого возвращаются привязки.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает имя приложения WOPI (например, сервер под управлением Сервер Office Web Apps), для которого возвращаются привязки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает зону, для которой возвращаются привязки.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

## Типы возвращаемых данных

## Пример

\--------------ПРИМЕР 1-----------------

    Get-SPWOPIBinding -Server "Server.corp.Contoso.com"

В этом примере показано, как возвращается список привязок, созданных в текущей ферме SharePoint, где выполняется этот командлет для приложения WOPI "Server.corp.Contoso.com." В качестве приложения WOPI может выступать сервер под управлением Сервер Office Web Apps.

\--------------ПРИМЕР 2-----------------

    Get-SPWOPIZone | Get-SPWOPIBinding

В этом примере показано, как возвращается список привязок, созданных в текущей ферме SharePoint, где выполняется этот командлет для зоны, настроенной для приложения WOPI.

## См. также


[New-SPWOPIBinding](new-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Совместное использование решений Office Web Apps и SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

