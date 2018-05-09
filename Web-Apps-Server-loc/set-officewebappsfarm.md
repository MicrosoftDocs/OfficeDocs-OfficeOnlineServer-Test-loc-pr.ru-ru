---
title: Set-OfficeWebAppsFarm
TOCTitle: Set-OfficeWebAppsFarm
ms:assetid: 6b0b434f-5d19-4e63-9296-cf104b2f3da8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219442(v=office.15)
ms:contentKeyID: 49624488
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-OfficeWebAppsFarm

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2015-03-09_

Настройка параметров существующей фермы Сервер Office Web Apps.

## Синтаксис

    Set-OfficeWebAppsFarm [-AllowCEIP <SwitchParameter>] [-AllowHttp <SwitchParameter>] [-AllowHttpSecureStoreConnections <SwitchParameter>] [-CacheLocation <String>] [-CacheSizeInGB <Nullable>] [-CertificateName <String>] [-ClipartEnabled <SwitchParameter>] [-Confirm [<SwitchParameter>]] [-DocumentInfoCacheSize <Nullable>] [-EditingEnabled <SwitchParameter>] [-ExcelAllowExternalData <SwitchParameter>] [-ExcelConnectionLifetime <Nullable>] [-ExcelExternalDataCacheLifetime <Nullable>] [-ExcelPrivateBytesMax <Nullable>] [-ExcelRequestDurationMax <Nullable>] [-ExcelSessionTimeout <Nullable>] [-ExcelWarnOnDataRefresh <SwitchParameter>] [-ExcelWorkbookSizeMax <Nullable>] [-ExternalURL <String>] [-FarmOU <String>] [-Force <SwitchParameter>] [-InternalURL <String>] [-LogLocation <String>] [-LogRetentionInDays <Nullable>] [-LogVerbosity <String>] [-MaxMemoryCacheSizeInMB <Nullable>] [-MaxTranslationCharacterCount <Nullable>] [-OpenFromUncEnabled <SwitchParameter>] [-OpenFromUrlEnabled <SwitchParameter>] [-OpenFromUrlThrottlingEnabled <SwitchParameter>] [-PicturePasteDisabled <SwitchParameter>] [-Proxy <String>] [-RecycleActiveProcessCount <Nullable>] [-RemovePersonalInformationFromLogs <SwitchParameter>] [-RenderingLocalCacheLocation <String>] [-SSLOffloaded <SwitchParameter>] [-TranslationEnabled <SwitchParameter>] [-TranslationServiceAddress <String>] [-TranslationServiceAppId <String>] [-WhatIf [<SwitchParameter>]]

## Подробное описание

Командлет **Set-OfficeWebAppsFarm** настраивает параметры существующей фермы Сервер Office Web Apps.

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
<td><p><strong>AllowCEIP</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Включает отчеты программы улучшения качества программного обеспечения (CEIP) на всех серверах в ферме Сервер Office Web Apps.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Чтобы это изменение вступило в силу, следует перезапустить каждый сервер в ферме Сервер Office Web Apps.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>AllowHttp</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Указывает, что сайты IIS должны быть настроены для использования порта 80 для доступа по протоколу HTTP. Используйте параметр <strong>AllowHTTP</strong> только в средах, в которых все компьютеры применяют IPSEC (полное шифрование), или в тестовых средах без конфиденциальных файлов.</p>
<p>Включается автоматически при включении параметра <strong>SSLOffloaded</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо перезапустить все серверы в ферме, чтобы это изменение вступило в силу.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHttpSecureStoreConnections</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Указывает, что подключения Secure Store могут выполняться с помощью подключений, не использующих протокол SSL (например, HTTP). Значение по умолчанию: <strong>False</strong>.</p>
<p>Используйте <strong>AllowHTTPSecureStoreConnections</strong> только в средах, где для всех компьютеров требуется IPSEC (полное шифрование), либо в тестовых средах без конфиденциальных файлов.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheLocation</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет расположение глобального кэша диска, используемого для хранения файлов сформированных изображений. Расположение по умолчанию: <strong>%programdata%\Microsoft\OfficeWebApps\Working\d\</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheSizeInGB</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Определяет максимальный размер глобального кэша диска в гигабайтах.</p>
<p>Типом должно быть целое значение в диапазоне от <strong>0</strong> до любого положительного целого числа. Значение по умолчанию: <strong>15</strong> ГБ.</p></td>
</tr>
<tr class="even">
<td><p><strong>CertificateName</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет понятное имя сертификата, используемого Сервер Office Web Apps для создания привязок HTTPS.</p>
<p>Если указанный сертификат не найден или срок его действия истек, или если заданное значение связано с несколькими сертификатами, в журнал записывается ошибка, а ферма не создается.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Это значение используется на каждом сервере, присоединяемом к ферме Сервер Office Web Apps. Поэтому на каждом сервере в ферме должен быть сертификат с таким понятным именем.</td>
</tr>
</tbody>
</table>

</div>
<p>Не требуется указывать параметр <strong>CertificateName</strong>, если вы используете параметр <strong>AllowHttp</strong> или <strong>SSLOffloaded</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо перезапустить все серверы в ферме, чтобы это изменение вступило в силу.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>ClipartEnabled</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Включает поддержку вставки картинок из Office.com в документы Office. Для этой функции требуется связь сервера с Интернетом, настроенная напрямую или через прокси-сервер, заданный в параметре <strong>Proxy</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Предлагает подтвердить выполнение команды. Чтобы получить дополнительные сведения, введите следующую команду: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DocumentInfoCacheSize</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Определяет максимальное число записей преобразования документа, которые хранятся в кэше памяти.</p>
<p>Значение по умолчанию — <strong>5000</strong> записей.</p></td>
</tr>
<tr class="even">
<td><p><strong>EditingEnabled</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Включает поддержку редактирования в браузере. Значение по умолчанию: <strong>False</strong>. Значение <strong>True</strong> задается только при наличии соответствующей лицензии на использование возможностей редактирования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelAllowExternalData</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Включает обновление поддерживаемых внешних данных в книгах Excel Web App, содержащих подключения к внешним данным. Значение по умолчанию: <strong>True</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelConnectionLifetime</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Задает продолжительность (в секундах) подключений к внешним данным для Excel Web App. Значение по умолчанию: <strong>1800</strong> секунд.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelExternalDataCacheLifetime</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Задает продолжительность (в секундах) времени существования кэша внешних данных в Excel Web App. Значение по умолчанию: <strong>300</strong> секунд.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelPrivateBytesMax</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Определяет максимальное число байтов исключительного пользования, применяемое Excel Web App, в мегабайтах. Если значение равно <strong>-1</strong>, под байты исключительного пользования по умолчанию выделяется 50 процентов физической памяти компьютера.</p>
<p>Типом должно быть значение <strong>-1</strong> или любое положительное целое число. Значение по умолчанию: <strong>-1.</strong></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо перезапустить все серверы в ферме, чтобы это изменение вступило в силу.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelRequestDurationMax</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Указывает максимальную длительность одного запроса в сеансе (сек). В случае превышения этого значения время ожидания запроса истекает.</p>
<p>Типом должно быть значение <strong>-1</strong> (без ограничений) или целое число от <strong>1</strong> до <strong>2 073 600</strong>. Значение по умолчанию: <strong>300</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelSessionTimeout</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Время (в секундах), в течение которого сеанс остается активным в приложении Excel Web App при отсутствии действий со стороны пользователя. Допустимые значения указаны ниже.</p>
<p><strong>-1</strong> Длительность сеанса не ограничивается.</p>
<p><strong>0</strong> Длительность сеанса ограничивается одним запросом.</p>
<p>От <strong>1</strong> до <strong>2 073 600</strong> Сеанс остается активным от 1 секунды до 24 дней. Значение по умолчанию: <strong>450</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelWarnOnDataRefresh</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Отключает или включает диалоговое окно, отображаемое при обновлении данных в Excel Web App.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelWorkbookSizeMax</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Указывает наибольший размер книги, при котором ее можно загрузить (МБ).</p>
<p>Тип значения: целое число в диапазоне от <strong>1</strong> до <strong>2000</strong>. Значение по умолчанию: <strong>10</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalURL</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет корневой URL-адрес, используемый клиентами для доступа к ферме Сервер Office Web Apps из Интернета. При использовании многосерверной фермы Сервер Office Web Apps с балансировкой нагрузки внешний URL-адрес привязан к IP-адресу внешней подсистемы балансировки нагрузки.</p>
<p>Для фермы Сервер Office Web Apps требуется, по крайней мере, один URL-адрес, который задается с помощью параметра <strong>ExternalURL</strong> или <strong>InternalURL</strong>. Можно также задать и внутренний, и внешний URL-адрес.</p></td>
</tr>
<tr class="even">
<td><p><strong>FarmOU</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет имя подразделения Active Directory, в которое должны входить серверы для присоединения к ферме Сервер Office Web Apps. Используйте этот параметр для предотвращения присоединения несанкционированных серверов (т. е. серверов, не входящих в это подразделение) к ферме Сервер Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет все запросы, отвечая «Да».</p></td>
</tr>
<tr class="even">
<td><p><strong>InternalURL</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет корневой URL-адрес, который должен использоваться клиентами для доступа к ферме Сервер Office Web Apps из интрасети.</p>
<p>Для фермы Сервер Office Web Apps требуется, по крайней мере, один URL-адрес. Он задается с помощью параметра <strong>ExternalURL</strong> или <strong>InternalURL</strong>. Можно также задать и внутренний, и внешний URL-адрес.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LogLocation</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет расположение на локальном компьютере, в котором хранятся журналы активности.</p>
<p>Данное расположение применяется на всех серверах в ферме и его нельзя настроить для каждого из них отдельно. Расположение по умолчанию: <strong>%programdata%\Microsoft\OfficeWebApps\Data\Logs\ULS\.</strong></p>
<p>Обязательно освободите достаточно места на диске, на котором хранятся журналы.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо перезапустить все серверы в ферме, чтобы это изменение вступило в силу.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>LogRetentionInDays</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Определяет период хранения записей журнала в днях. Записи, срок хранения которых превышает заданный, удаляются.</p>
<p>Тип значения: целое число в диапазоне от <strong>0</strong> до <strong>365</strong>. Значение по умолчанию: <strong>7</strong> дней.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо перезапустить все серверы в ферме, чтобы это изменение вступило в силу.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>LogVerbosity</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет объем информации, хранимой в файлах журналов трассировки. Доступны следующие значения:</p>
<p><strong>VerboseEX</strong> — запись сведений низкого уровня в журнал трассировки. Это полезно для трассировок большого объема.</p>
<p><strong>Verbose</strong> — запись сведений низкого уровня в журнал трассировки.</p>
<p><strong>Medium</strong> — запись сведений среднего уровня в журнал трассировки.</p>
<p><strong>High</strong> — запись сведений высокого уровня в журнал трассировки.</p>
<p><strong>Monitorable</strong> — запись сведений трассировки, представляющих необычный путь к коду и действия, которые должны отслеживаться.</p>
<p><strong>Unexpected</strong> — запись сведений трассировки, представляющих непредвиденный путь к коду и действия, которые должны отслеживаться.</p>
<p><strong>None</strong> — трассировки не записываются в файл журнала.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если для параметра <strong>LogVerbosity</strong> в течение длительного времени используется низкий уровень сведений, это может значительно ухудшить производительность системы.</td>
</tr>
</tbody>
</table>

</div>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо перезапустить все серверы в ферме, чтобы это изменение вступило в силу.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>MaxMemoryCacheSizeInMB</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Определяет максимальный объем памяти в мегабайтах, который может использовать кэш отображения.</p>
<p>Типом должно быть целое значение в диапазоне от <strong>0</strong> до любого положительного целого числа. Значение по умолчанию: <strong>1024</strong> МБ.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxTranslationCharacterCount</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Задает максимальное число знаков, которое может содержать документ, чтобы его можно было перевести.</p>
<p>Типом должно являться целое значение. Можно задать значение 0, указывающее на отсутствие такого ограничения, или же значения в диапазоне <strong>2000</strong>–<strong>2 000 000</strong>. Значение по умолчанию: <strong>125 000</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUncEnabled</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Отключает или включает возможность использования средств просмотра Online Viewer для просмотра файлов Office по UNC-пути.</p>
<p>Чтобы разрешить в средствах просмотра Online Viewer отображение файлов в UNC-путях, следует сначала задать для параметра OpenFromUrlEnabled значение True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OpenFromUrlEnabled</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Включает или отключает возможность использования средств Online Viewer для просмотра файлов Office по URL-адресу или UNC-пути.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUrlThrottlingEnabled</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Регулирует число URL-запросов &quot;Открыть из&quot; с любого заданного сервера в течение определенного периода времени. Значения регулировки по умолчанию, которые нельзя настроить, позволяют гарантировать, что ферма серверов Office Web Apps не сможет переполнить отдельный сервер запросами содержимого, которое будет просматриваться в средствах просмотра Online Viewer.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PicturePasteDisabled</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Отключает для пользователей возможность вставлять изображения с веб-страницы в Office Web Apps. Значение по умолчанию: <strong>False</strong>. Если параметру <strong>OpenFromURLEnabled</strong> присвоено значение <strong>True</strong>, а для параметра <strong>PicturePasteDisabled</strong> не задано значение <strong>False</strong>, пользователи могут вставлять изображения в Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><strong>Proxy</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет URL-адрес прокси-сервера, который разрешает HTTP-запросы на внешние сайты. Обычно этот параметр задается вместе с параметрами <strong>ClipartEnabled</strong> и <strong>TranslationEnabled</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecycleActiveProcessCount</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Nullable</p></td>
<td><p>Определяет число файлов, которые может отобразить один процесс Word или PowerPoint до его перезапуска.</p>
<p>Тип значения: целое число в диапазоне от <strong>1</strong> до <strong>1000</strong>. Значение по умолчанию: <strong>5</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо перезапустить все серверы в ферме, чтобы это изменение вступило в силу.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>RemovePersonalInformationFromLogs</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Обеспечивает наилучшую очистку персональных данных из журнала Сервер Office Web Apps. Заменяет значения хэш-функцией SHA256. Может проводить очистку следующих данных.</p>
<ul>
<li><p>Имена документов и URL-адреса</p></li>
<li><p>IP-адреса</p></li>
<li><p>Адреса электронной почты</p></li>
<li><p>Имена пользователей</p></li>
</ul>
<p>Значение по умолчанию: <strong>False</strong>. Учтите, что включение этого параметра не гарантирует того, что персональные данные не будут записываться в журналы Сервер Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RenderingLocalCacheLocation</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Определяет расположение временного кэша, используемого службами просмотра Word и PowerPoint.</p>
<p>Расположение по умолчанию: <strong>%programdata%\Microsoft\OfficeWebApps\Working\waccache\</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SSLOffloaded</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Указывает серверам в ферме Сервер Office Web Apps, что SSL выгружен в подсистему балансировки нагрузки. Если параметр <strong>SSLOffloaded</strong> включен, веб-приложения привязаны к порту 80 (HTTP) на локальном сервере. Однако HTML-код, ссылающийся на другие ресурсы, например CSS и изображения, использует URL-адреса HTTPS для этих ссылок.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо перезапустить все серверы в ферме, чтобы это изменение вступило в силу.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationEnabled</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Включает поддержку автоматического перевода документа с помощью Microsoft Translator, интерактивной службы, переводящей текст с разных языков. Переведенный файл отображается в Word Web App. Так как Microsoft Translator — это интерактивная служба, необходимо включить связь сервера с Интернетом напрямую или через прокси-сервер, указанный в параметре <strong>Proxy</strong>.<br />
Служба Microsoft Translator может собирать данные для улучшения качества перевода.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>TranslationServiceAddress</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Указывает URL-адрес сервера переводов, на который отправляются запросы переводов. Значение по умолчанию: интернет-служба Microsoft Translator. Обычно этот параметр не используется (за исключением случая, когда требуется изменить службы перевода).</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Чтобы это изменение вступило в силу, следует перезапустить каждый сервер в ферме Сервер Office Web Apps.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationServiceAppId</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Указывает идентификатор приложения для службы перевода. Значение по умолчанию: идентификатор общедоступного приложения для Office Web Apps. Обычно этот параметр не используется (за исключением случая, когда с Microsoft Translator согласовано предоставление дополнительных служб и был получен соответствующий идентификатор частного приложения).</p></td>
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

    Set-OfficeWebAppsFarm -ClipartEnabled:$true

В этом примере разрешается вставка картинок с сайта Office.com.

\------------------ПРИМЕР 2---------------------

    Set-OfficeWebAppsFarm -EditingEnabled:$true

В этом примере включаются возможности редактирования для Office Web Apps.

\------------------ПРИМЕР 3---------------------

    Set-OfficeWebAppsFarm -OpenFromUncEnabled:$false

В этом примере отключается возможность просматривать любой файл Office по UNC-пути.

## См. также


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание инфраструктуры: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

