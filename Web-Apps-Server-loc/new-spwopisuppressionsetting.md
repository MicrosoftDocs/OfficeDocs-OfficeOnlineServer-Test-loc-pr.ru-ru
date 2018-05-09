---
title: New-SPWOPISuppressionSetting
TOCTitle: New-SPWOPISuppressionSetting
ms:assetid: 7e6bb8f5-3124-4568-80c6-02cae46b803b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219443(v=office.15)
ms:contentKeyID: 49624489
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-SPWOPISuppressionSetting

 

_**Применимо к:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Последнее изменение раздела:**2015-03-09_

Командлет **New-SPWOPISuppressionSetting** выполняет отключение Office Web Apps для действия, расширения файла или программного идентификатора, заданного в текущей ферме SharePoint.

## Синтаксис

    New-SPWOPISuppressionSetting [-Action <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **New-SPWOPISuppressionSetting** выполняет отключение Office Web Apps для действия, расширения файла или программного идентификатора (ProgID), заданного в текущей ферме SharePoint. Командлет выполняет эту операцию, не удаляя сведения об обнаружении и не блокируя для пользователей возможность использовать функции общего доступа по ссылке SharePoint, чтобы отправлять ссылки на документ и предоставлять получателю возможности использовать Office Web Apps для документов этого типа. Выполнение этого командлета рекомендуется в том случае, если нужно использовать службы Службы Excel для просмотра рабочих книг Excel вместо приложения WOPI (например, сервер под управлением Сервер Office Web Apps).

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
<td><p>Задает действие блокировки для данного расширения или программного идентификатора (ProgID). Например, &quot;view&quot;, &quot;edit&quot; и &quot;embedview&quot;. Чтобы получить полный список действий, выполните командлет <strong>Get-SPWOPIBinding</strong>.</p></td>
</tr>
<tr class="even">
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
<tr class="odd">
<td><p><strong>Confirm</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Предлагает подтвердить выполнение команды. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Extension</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает расширение файла для блокировки. Выполните командлет Get-SPWOPIBinding, чтобы получить список расширений файлов, поддерживаемых приложением WOPI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает программный идентификатор (ProgID) приложения для блокировки. Выполните командлет Get-SPWOPIBinding, чтобы получить список программных идентификаторов, поддерживаемых приложением WOPI.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Отображает описание команды. При этом сама команда не выполняется. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

## Типы возвращаемых данных

## Пример

\--------------ПРИМЕР 1-----------------

    New-SPWOPISuppressionSetting -Extension "XLSX" -Action "view"

    New-SPWOPISuppressionSetting -Extension "XLS" -Action "view"

В этом примере показано отключение возможности использования Office Web Apps для просмотра рабочих книг Excel с расширениями файлов XLSX или XLS.

## См. также


[Get-SPWOPISuppressionSetting](get-spwopisuppressionsetting.md)  
[Remove-SPWOPISuppressionSetting](remove-spwopisuppressionsetting.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Совместное использование решений Office Web Apps и SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

