---
title: New-SPWOPIBinding
TOCTitle: New-SPWOPIBinding
ms:assetid: 696f01b4-a144-431b-9bae-1c3ede78609d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219441(v=office.15)
ms:contentKeyID: 49624486
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-SPWOPIBinding

 

_**Применимо к:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Последнее изменение раздела:**2015-03-09_

Создает новую привязку для связи расширений имен файлов или приложений с действиями в текущей ферме SharePoint, где выполняется этот командлет.

## Синтаксис

    New-SPWOPIBinding -ServerName <String> [-Action <String>] [-AllowHTTP <SwitchParameter>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-FileName <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **New-SPWOPIBinding** используется для связи расширений файлов или приложений с действиями в текущей ферме SharePoint, где выполняется этот командлет. Каждая привязка позволяет использовать приложение WOPI для просмотра или редактирования файлов в библиотеке SharePoint. Например, если документ Word отображается в списке документов SharePoint, в списке SharePoint отобразятся доступные параметры просмотра или редактирования документа в зависимости от действий, связанных с Word в этой ферме SharePoint.

Чтобы использовать такие приложения WOPI, как, например, сервер под управлением Сервер Office Web Apps, для Office Web Apps, необходимо выполнить этот командлет в ферме SharePoint. После этого можно будет использовать Office Web Apps.

Если командлет **New-SPWOPIBinding** выполняется для приложения или расширения файла, для которого уже существует привязка (или связь), произойдет сбой при выполнении командлета.

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
<td><p><strong>ServerName</strong></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает имя или полное доменное имя приложения WOPI (например, сервера под управлением Сервер Office Web Apps).</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает действие для привязки. Например, “view”, “edit” и “embedview”. Чтобы просмотреть список действий, поддерживаемых приложением WOPI, выполните командлет <strong>Get-SPWOPIBinding</strong>. Как правило, этот параметр не рекомендуется использовать. Некоторые функции в SharePoint могут быть недоступны при указании определенных действий без указания других.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHTTP</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Указывает, может ли командлет использовать протокол HTTP для обнаружения поддерживаемых приложением WOPI функций. Если задано значение True, сведения об обнаружении из приложения WOPI будут отправлены через незащищенное соединение.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает приложения для привязки. Можно указать следующие приложения: “Word”, “Excel”, “PowerPoint” или “OneNote”. Чтобы получить список приложений, поддерживаемых приложением WOPI, выполните командлет <strong>Get-SPWOPIBinding</strong>.</p></td>
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
<td><p><strong>Confirm</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Предлагает подтвердить выполнение команды. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает расширения файлов для привязки. Чтобы получить список расширений файлов, поддерживаемых приложением WOPI, выполните командлет <strong>Get-SPWOPIBinding</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileName</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает путь файла XML, который содержит сведения об обнаружении для приложения WOPI. Можно загрузить сведения об обнаружении из XML-файла вместо того, чтобы запрашивать их непосредственно из приложения WOPI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает программный идентификатор (ProgID) для привязки приложения. Чтобы получить список программных идентификаторов, поддерживаемых приложением WOPI, выполните командлет <strong>Get-SPWOPIBinding</strong>. Этот параметр рекомендуется использовать только для связи действия с папкой OneNote.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Отображает описание команды. При этом сама команда не выполняется. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## Типы входных данных

## Типы возвращаемых данных

## Пример

\--------------ПРИМЕР 1-----------------

    New-SPWOPIBinding -ServerName "Server.corp.Contoso.com"

В этом примере показано создание привязок для всех приложений и расширений файлов, поддерживаемых приложением WOPI, в текущей ферме SharePoint, где выполняется данный командлет.

\--------------ПРИМЕР 2-----------------

    New-SPWOPIBinding -ServerName "Server.corp.Contoso.com" -Application "Excel"

В этом примере показана связь Excel со всеми действиями, поддерживаемыми приложением WOPI для Excel в текущей ферме SharePoint, где выполняется данный командлет.

## См. также


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Совместное использование решений Office Web Apps и SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

