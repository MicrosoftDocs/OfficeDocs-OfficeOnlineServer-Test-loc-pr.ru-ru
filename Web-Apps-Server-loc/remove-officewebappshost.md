---
title: Remove-OfficeWebAppsHost
TOCTitle: Remove-OfficeWebAppsHost
ms:assetid: d0f7b5c2-da0f-421a-8478-c39b247c3ac5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219453(v=office.15)
ms:contentKeyID: 49624513
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsHost

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2015-03-09_

Удаляет несущий домен из списка разрешенных доменов для фермы Сервер Office Web Apps.

## Синтаксис

    Remove-OfficeWebAppsHost -Domain <String>

## Подробное описание

Командлет **Remove-OfficeWebAppsHost** удаляет указанный домен узла из списка разрешенных доменов. Этот список содержит домены, для которых Сервер Office Web Apps разрешает запросы на выполнение файловых операций.


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
<td><p>Определяет домен узла, который требуется удалить из списка разрешенных доменов.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

## Типы возвращаемых данных

## Пример

\------------------ПРИМЕР 1---------------------

    Remove-OfficeWebAppsHost -domain "contoso.com"

В этом примере домен contoso.com удаляется из списка разрешенных доменов.

## См. также


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Get-OfficeWebAppsHost](get-officewebappshost.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

