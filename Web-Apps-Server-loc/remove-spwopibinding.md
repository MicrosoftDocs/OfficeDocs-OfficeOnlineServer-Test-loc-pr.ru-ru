---
title: Remove-SPWOPIBinding
TOCTitle: Remove-SPWOPIBinding
ms:assetid: 52855c21-ee2c-497a-b308-bf5eeabe4bbe
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219438(v=office.15)
ms:contentKeyID: 49624480
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-SPWOPIBinding

 

_**Применимо к:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Последнее изменение раздела:**2015-03-09_

Удаляет привязки приложений, расширений имен файлов и связанных с ними действий в текущей ферме SharePoint, где выполняется этот командлет.

## Синтаксис

    Remove-SPWOPIBinding [[-Identity] <SPWopiBindingPipeBind>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

    Remove-SPWOPIBinding [-Action <String>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-Server <String>] [-WhatIf [<SwitchParameter>]] [-WOPIZone <String>]

    Remove-SPWOPIBinding [-All <SwitchParameter>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **Remove-SPWOPIBinding** удаляет привязки приложений, расширений файлов и связанных с ними действий в текущей ферме SharePoint, где выполняется данный командлет. После выполнения командлета можно при необходимости использовать командлет **New-SPWOPIBinding** для воссоздания привязок. При удалении всех привязок приложения использование Office Web Apps или функции общего доступа по ссылке в SharePoint невозможно для данного приложения. При удалении всех привязок в ферме SharePoint, где выполняется этот командлет, использование Office Web Apps или функции общего доступа по ссылке в SharePoint невозможно для любых приложений в библиотеке SharePoint.

Чтобы запретить использование Office Web Apps в качестве действия по умолчанию при щелчке мышью и сохранить данные об обнаружении привязок, сохранив при этом возможность использования функции общего доступа по ссылке в SharePoint, чтобы отправить ссылки на документ и разрешить получателю использовать Office Web Apps для документов этого типа, рекомендуется использовать вместо этого командлет **New-SPWOPISuppression**.

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
<td><p><strong>Identity</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>Задает привязку.</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает действие, для которого удаляются привязки. Например, действия &quot;view&quot;, &quot;edit&quot; и &quot;embedview&quot;. Чтобы просмотреть список действий, выполните командлет <strong>Get-SPWOPIBinding</strong>. Как правило, этот параметр не используется. Некоторые функции в SharePoint могут быть недоступны при указании определенных действий без указания других.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Удаляет все привязки.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает приложения, для которых удаляются привязки. Можно указать следующие приложения: &quot;Word,&quot; &quot;Excel&quot;, &quot;PowerPoint&quot; или &quot;OneNote&quot;. Чтобы получить список приложений, выполните командлет <strong>Get-SPWOPIBinding</strong>.</p></td>
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
<td><p>Предлагает подтвердить выполнение команды. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает расширения файлов, для которых удаляются привязки. Чтобы получить список расширений файлов, выполните командлет <strong>Get-SPWOPIBinding</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgId</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает программный идентификатор (ProgID) приложения, для которого удаляются привязки. Чтобы получить список программных идентификатор, выполните командлет <strong>Get-SPWOPIBinding</strong>. Этот параметр рекомендуется использовать только для удаления привязок в OneNote.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает имя приложения WOPI (например, Сервер Office Web Apps), для которого удаляются привязки.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Отображает описание команды. При этом сама команда не выполняется. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает зону, для которой удаляются привязки.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

## Типы возвращаемых данных

## Пример

\--------------ПРИМЕР 1-----------------

    Remove-SPWOPIBinding -Application "Excel"

В этом примере показано удаление всех привязок для Excel в текущей ферме SharePoint, где выполняется этот командлет.

\--------------ПРИМЕР 2-----------------

    Remove-SPWOPIBinding -All:$true

В этом примере показано удаление всех привязок в текущей ферме SharePoint, где выполняется этот командлет.

\--------------ПРИМЕР 3-----------------

    Get-SPWOPIBinding -Action "MobileView" | Remove-SPWOPIBinding

В этом примере показано удаление всех привязок для Office Mobile Web Apps в текущей ферме SharePoint, где выполняется этот командлет.

## См. также


[New-SPWOPIBinding](new-spwopibinding.md)  
[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Совместное использование решений Office Web Apps и SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

