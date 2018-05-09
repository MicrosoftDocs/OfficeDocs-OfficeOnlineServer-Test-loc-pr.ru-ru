---
title: New-OfficeWebAppsMachine
TOCTitle: New-OfficeWebAppsMachine
ms:assetid: b0385c4e-61fc-4607-a48c-64d8f4e80651
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219449(v=office.15)
ms:contentKeyID: 49624506
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsMachine

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2015-03-09_

Добавление текущего сервера в ферму Сервер Office Web Apps.

## Синтаксис

    New-OfficeWebAppsMachine [-MachineToJoin] <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **New-OfficeWebAppsMachine** добавляет текущий сервер в существующую ферму Сервер Office Web Apps и при необходимости задает новому серверу одну или несколько ролей.

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
<td><p><strong>MachineToJoin</strong></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет имя сервера, который уже входит в ферму Сервер Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Предлагает подтвердить выполнение команды. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Предполагает, что ответ на любой запрос — «Да».</p></td>
</tr>
<tr class="even">
<td><p><strong>Roles</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String[]</p></td>
<td><p>Определяет одну или несколько разделенных запятыми ролей, назначаемых новому серверу. Если роли не указаны, то серверу назначаются все роли.</p>
<p>Доступны следующие типы ролей:</p>
<p><strong>FrontEnd</strong></p>
<p><strong>WordBackEnd</strong></p>
<p><strong>ExcelBackEnd</strong></p>
<p><strong>PowerPointBackEnd</strong></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Рекомендуется, чтобы на всех серверах в ферме Сервер Office Web Apps были запущены все роли. Назначение ролей не будет приносить пользы, если ферма Сервер Office Web Apps содержит меньше 50 серверов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
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

\------------------ПРИМЕР 1---------------------

    New-OfficeWebAppsMachine -MachineToJoin server1.contoso.com

В этом примере текущий сервер добавляется в ферму Сервер Office Web Apps, которая реализована на сервере server1.contoso.com.

## См. также


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

