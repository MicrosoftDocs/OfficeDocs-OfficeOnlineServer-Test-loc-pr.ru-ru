---
title: Update-SPWOPIProofKey
TOCTitle: Update-SPWOPIProofKey
ms:assetid: fe7f3a87-082e-4a43-a5f3-7be41d8e91a3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219460(v=office.15)
ms:contentKeyID: 49624524
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Update-SPWOPIProofKey

 

_**Применимо к:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Последнее изменение раздела:**2015-03-09_

Обновляет открытый ключ, используемый для подключения к приложению WOPI в текущей ферме SharePoint, где выполняется данный командлет.

## Синтаксис

    Update-SPWOPIProofKey [-AssignmentCollection <SPAssignmentCollection>] [-ServerName <String>]

## Подробное описание

Командлет **Update-SPWOPIProofKey** обновляет открытый ключ, используемый для подключения к приложению WOPI (это может быть сервер под управлением Сервер Office Web Apps) в текущей ферме SharePoint, где выполняется данный командлет. Этот командлет рекомендуется использовать при рассинхронизации ключей в ферме SharePoint и приложении WOPI. Если ключи не синхронизированы, документы могут не открываться в браузере, и в журналах единой службы ведения журналов (ULS) регистрируется сообщение "Недействительная подпись для файла…" или "Недействительная подпись для папки...".

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
<td><p><strong>ServerName</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Указывает приложение WOPI, из которого получается ключ. Это приложение может быть сервером под управлением Сервер Office Web Apps. Если этот параметр не задан, выполняется обновление открытых ключей для всех приложений WOPI, подключенных к текущей ферме SharePoint.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

## Типы возвращаемых данных

## Пример

\--------------ПРИМЕР-----------------

    Update-SPWOPIProofKey -ServerName "Server.corp.Contoso.com"

В этом примере показано получение текущего открытого ключа от приложения WOPI (например, сервер под управлением Сервер Office Web Apps) и обновление ключа, сохраненного в ферме SharePoint.

## См. также


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Совместное использование решений Office Web Apps и SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

