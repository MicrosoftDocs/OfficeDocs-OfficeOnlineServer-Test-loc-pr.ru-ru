---
title: Set-SPWOPIZone
TOCTitle: Set-SPWOPIZone
ms:assetid: bc751cc4-8ac8-45f7-b6ea-da6fcb5473ac
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219451(v=office.15)
ms:contentKeyID: 49624508
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIZone

 

_**Применимо к:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Последнее изменение раздела:**2015-03-09_

Выполняет настройку зоны, используемой текущей фермой SharePoint для перехода в браузере к приложению WOPI.

## Синтаксис

    Set-SPWOPIZone [[-Zone] <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **Set-SPWOPIZone** выполняет настройку зоны, используемой текущей фермой SharePoint для перехода в браузере к приложению WOPI (например, сервер под управлением Сервер Office Web Apps). Страница SharePoint Server в браузере служит для создания фрейма, содержащего страницу приложения WOPI. Зона URL-адреса страницы приложения WOPI определяется именно этой настройкой.

Если зона не задана, по умолчанию используется значение “internal-HTTPS.” При выборе зоны, не поддерживаемой приложением WOPI, произойдет сбой в работе Office Web Apps. Протокол HTTP допускается использовать только при работе в полностью защищенной сети, где используется шифрование IPSEC (полное шифрование) или в среде тестирования, не содержащей конфиденциальных данных.

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
<td><p><strong>Zone</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает зону. Чтобы получить список зон, поддерживаемых приложением WOPI, выполните командлет <strong>Get-SPWOPIBinding</strong>.</p>
<p>При использовании фермы SharePoint, которая одновременно является внешней и внутренней, укажите внешнюю ферму. Если используемая ферма SharePoint является только внутренней, укажите внутреннюю ферму. Протокол HTTP допускается использовать только при работе в полностью защищенной сети, где используется шифрование IPSEC (полное шифрование) или в среде тестирования, не содержащей конфиденциальных данных. Доступны следующие параметры:</p>
<p>- Internal-HTTP</p>
<p>- Internal-HTTPS</p>
<p>- External-HTTP</p>
<p>- External-HTTPS</p></td>
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
<td><p>Предлагает подтвердить выполнение команды. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong>.</p></td>
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

\--------------ПРИМЕР-----------------

    Set-SPWOPIZone -Zone "external-https"

В этом примере показана настройка для текущей фермы SharePoint использования внешних подключений по протоколу HTTPS к приложению WOPI (например, сервер под управлением Сервер Office Web Apps).

## См. также


[Get-SPWOPIZone](get-spwopizone.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Совместное использование решений Office Web Apps и SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

