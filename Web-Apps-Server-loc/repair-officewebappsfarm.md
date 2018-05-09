---
title: Repair-OfficeWebAppsFarm
TOCTitle: Repair-OfficeWebAppsFarm
ms:assetid: 083d8e25-ce82-4884-9bbc-06375185011c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219433(v=office.15)
ms:contentKeyID: 49624468
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Repair-OfficeWebAppsFarm

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2015-03-09_

Удаляет все серверы, отмеченные как неработоспособные, из фермы Сервер Office Web Apps.

## Синтаксис

    Repair-OfficeWebAppsFarm [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **Repair-OfficeWebAppsFarm** удаляет все серверы, отмеченные как неработоспособные, из фермы Сервер Office Web Apps. Данный командлет обновляет топологию фермы, но не очищает службы и веб-приложения на удаляемых серверах. Поэтому рекомендуется выполнять командлет **Remove-OfficeWebAppsMachine** на неработоспособных серверах, чтобы они были полностью удалены из фермы. Используйте командлет **Repair-OfficeWebAppsFarm**, только если на неработоспособных серверах произошел сбой и вы не можете запустить командлет **Remove-OfficeWebAppsMachine** непосредственно на них.

Если имеется несколько неработоспособных серверов, перед удалением каждого сервера отображается запрос. Если неработоспособных серверов нет, командлет не выполняет никаких действий.

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
<td><p><strong>Force</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Предполагает, что ответ на любой запрос — &quot;Да&quot;.</p></td>
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

    (Get-OfficeWebAppsFarm).Machines

В этом примере отображается состояние работоспособности всех серверов в ферме Сервер Office Web Apps.

\------------------ПРИМЕР 2---------------------

    Repair-OfficeWebAppsFarm

В этом примере все неработоспособные серверы удаляются из фермы Сервер Office Web Apps.

## См. также


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

