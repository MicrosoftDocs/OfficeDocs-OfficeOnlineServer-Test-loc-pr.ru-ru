---
title: Set-OfficeWebAppsMachine
TOCTitle: Set-OfficeWebAppsMachine
ms:assetid: aeba2638-be88-4030-80fe-7e4bcd30309b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219448(v=office.15)
ms:contentKeyID: 49624505
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-OfficeWebAppsMachine

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2015-03-09_

Изменяет параметры текущего сервера в ферме Сервер Office Web Apps.

## Синтаксис

    Set-OfficeWebAppsMachine [-Confirm [<SwitchParameter>]] [-Master <String>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **Set-OfficeWebAppsMachine** меняет параметры текущего сервера в ферме Сервер Office Web Apps. К этим параметрам относятся роли текущего сервера и выделенный основной сервер фермы.

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
<td><p><strong>Confirm</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Предлагает подтвердить выполнение команды. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Master</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p></p>
<p>Определяет сервер, на котором хранятся основные файлы конфигурации фермы.</p>
<p>Если локальный сервер задан как основной, необходимо выполнить командлет <strong>Set-OfficeWebAppsMachine -Master</strong> на всех остальных серверах в ферме Сервер Office Web Apps, чтобы указать для них новый основной сервер.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roles</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String[]</p></td>
<td><p>Определяет список разделенных запятыми ролей, назначаемых локальному серверу.</p>
<p>Доступны следующие типы ролей:</p>
<p><strong>All</strong></p>
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

\------------------ПРИМЕР 1---------------------

    (Get-OfficeWebAppsFarm).Machines

В этом примере показаны роли каждого сервера в ферме Сервер Office Web Apps.

\------------------ПРИМЕР 2---------------------

    Set-OfficeWebAppsMachine -Roles FrontEnd

В этом примере текущий сервер настраивается как интерфейсный веб-сервер.

\------------------ПРИМЕР 3---------------------

    Set-OfficeWebAppsMachine -Roles All

В этом примере текущий сервер настраивается для размещения всех ролей.

## См. также


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

