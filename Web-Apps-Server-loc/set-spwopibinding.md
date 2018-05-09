---
title: Set-SPWOPIBinding
TOCTitle: Set-SPWOPIBinding
ms:assetid: e373528f-e69b-4e25-9df4-3a5f80ab64ac
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219454(v=office.15)
ms:contentKeyID: 49624515
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIBinding

 

_**Применимо к:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Последнее изменение раздела:**2015-03-09_

Обновляет действие по умолчанию при щелчке мышью для приложения или привязки расширения имени файла.

## Синтаксис

    Set-SPWOPIBinding [-Identity] <SPWopiBindingPipeBind> -DefaultAction <SwitchParameter> [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **Set-SPWOPIBinding** обновляет действие по умолчанию при щелчке мышью для приложения или привязки расширения файла. Например, можно по умолчанию задать в качестве действия при щелчке мышью просмотр документа Word в библиотеке SharePoint. Для этого необходимо задать для действия по умолчанию значение True для привязок "view"-"Word".

Как правило, используют результат выполнения команды **Get-SPWOPIBinding** в качестве значения свойства -Identity этой команды. Дополнительные сведения см. в разделе [Get-SPWOPIBinding](get-spwopibinding.md).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Можно установить только те привязки, которые были созданы с помощью команды <strong>New-SPWOPIBinding</strong>. Чтобы переопределить встроенную привязку, например действие, выполненное во время просмотра документа Word в библиотеке SharePoint, создайте новую привязку с помощью <strong>New-SPWOPIBinding</strong> и назначьте другое действие. Дополнительные сведения см. в разделе <a href="new-spwopibinding.md">New-SPWOPIBinding</a>.</td>
</tr>
</tbody>
</table>


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
<td><p>Обязательный</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>Задает привязку. Как правило, используют результат выполнения команды <strong>Get-SPWOPIBinding</strong> в качестве значения свойства -Identity.</p></td>
</tr>
<tr class="even">
<td><p><strong>DefaultAction</strong></p></td>
<td><p>Обязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Указывает, нужно ли задавать привязку как действие по умолчанию при щелчке мышью для приложения или расширения файла в привязке.</p></td>
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

</div>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Предлагает подтвердить выполнение команды. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
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

\--------------ПРИМЕР-----------------

    Get-SPWOPIBinding -Action "view" -Application "Word"| Set-SPWOPIBinding -DefaultAction

В этом примере показано настройка в качестве действия по умолчанию при щелчке мышью просмотра документа Word в библиотеке SharePoint. Чтобы проверить, настроено ли это действие по умолчанию в Word, выполните командлет **Get-SPWOPIBinding –Action “view” –Application “Word”**. Для параметра **IsDefaultAction** задано значение True.

## См. также


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  
[New-SPWOPIBinding](new-spwopibinding.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Совместное использование решений Office Web Apps и SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

