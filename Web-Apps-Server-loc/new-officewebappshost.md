---
title: New-OfficeWebAppsHost
TOCTitle: New-OfficeWebAppsHost
ms:assetid: f1d523ab-45c6-4e3c-b274-22c0d229a6a0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219459(v=office.15)
ms:contentKeyID: 49624523
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsHost

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2015-03-09_

Добавляет домен узла в список разрешенных доменов для фермы Сервер Office Web Apps.

## Синтаксис

    New-OfficeWebAppsHost -Domain <String>

## Подробное описание

Командлет **New-OfficeWebAppsHost** добавляет домен узла в список доменов, для которых Сервер Office Web Apps разрешает запросы файловых операций, таких как получение файла, извлечение метаданных и изменение файла. Этот список, который называют списком разрешенных доменов, — компонент обеспечения безопасности, не позволяющий нежелательным узлам подключаться к ферме Сервер Office Web Apps и выполнять файловые операции без вашего ведома.


> [!TIP]
> Вы можете добавлять в список домены любого типа, включая общедоступные домены, а также домены пула, фермы и Active Directory. Просто убедитесь, что домен, к которому вы предоставляете доступ, отвечает требованиям безопасности.



Подстановочный знак "\*" используется для любого домена, добавленного в разрешенный список, чтобы также были разрешены запросы ко всем дочерним доменам. Например, если добавить в список домен contoso.com, Сервер Office Web Apps также разрешит запросы к доменам corp.contoso.com и dev.contoso.com. Запросы к другим доменам (например, fabrikam.com) не разрешены.


> [!WARNING]
> Если список разрешенных доменов пуст, Сервер Office Web Apps разрешает запросы файлов для узлов в любом домене. Не оставляйте этот список пустым, если ваша ферма Сервер Office Web Apps доступна из Интернета. В противном случае все смогут использовать вашу ферму Сервер Office Web Apps для просмотра и изменения контента.



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
<th>Обязательность</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Domain</strong></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет домен, добавляемый в список разрешенных доменов. Не указывайте символ звездочки и не начинайте домен с точки.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

## Типы возвращаемых данных

## Пример

\------------------ПРИМЕР 1---------------------

    New-OfficeWebAppsHost -domain "contoso.com"

В этом примере домен contoso.com добавляется в список разрешенных доменов.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Нельзя одновременно добавить несколько несущих доменов в список разрешений. Вам следует запустить командлет New-OfficeWebAppsHost для каждого несущего домена, который требуется добавить в список разрешений.</td>
</tr>
</tbody>
</table>


## См. также


[Get-OfficeWebAppsHost](get-officewebappshost.md)  
[Remove-OfficeWebAppsHost](remove-officewebappshost.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

