---
title: Windows PowerShell для сервера Office Web Apps
TOCTitle: Windows PowerShell для сервера Office Web Apps
ms:assetid: 56bfd3b3-f563-423d-aea0-65b331f73b96
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Ee890080(v=office.15)
ms:contentKeyID: 49624482
ms.date: 01/03/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Windows PowerShell для сервера Office Web Apps

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2016-12-16_

**Сводка.** Поиск статей о командлетах Windows PowerShell OfficeWebApps, которые служат для настройки сервера Office Web Apps.

**Аудитория:** ИТ-специалисты

Сервер Office Web Apps — это новый серверный продукт Office, предоставляющий браузерные версии Word, PowerPoint, Excel и OneNote. Ферма, состоящая из одного сервера Office Web Apps, поддерживает пользователей, которые получают доступ к файлам Office через SharePoint 2013, Lync Server 2013, Exchange Server 2013, общие папки и веб-сайты.

![Логотип Office 2013](images/JJ219456.a106e261-2cd0-43b7-af77-92de7e4b6fb9(Office.15).png "Логотип Office 2013")В следующей таблице приведены и описаны статьи для каждого командлета OfficeWebApps Windows PowerShell для Сервер Office Web Apps.


> [!TIP]
> Если Windows PowerShell не распознает эти командлеты при их выполнении, возможно, вам потребуется импортировать модуль <STRONG>OfficeWebApps</STRONG>. Используйте команду:<BR><CODE>Import-Module -Name OfficeWebApps</CODE>




### Командлеты Windows PowerShell OfficeWebApps

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Статья</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="get-officewebappsfarm.md">Get-OfficeWebAppsFarm</a></p></td>
<td><p>Возвращение сведений об объекте OfficeWebAppsFarm, в который входит текущий сервер.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-officewebappshost.md">Get-OfficeWebAppsHost</a></p></td>
<td><p>Возвращает список несущих доменов из списка разрешенных доменов для фермы Сервер Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-officewebappsmachine.md">Get-OfficeWebAppsMachine</a></p></td>
<td><p>Возвращает подробные сведения о текущем сервере в ферме Сервер Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-officewebappsfarm.md">New-OfficeWebAppsFarm</a></p></td>
<td><p>Создание фермы Сервер Office Web Apps на локальном компьютере.</p></td>
</tr>
<tr class="odd">
<td><p><a href="new-officewebappshost.md">New-OfficeWebAppsHost</a></p></td>
<td><p>Добавление домена узла в список разрешенных доменов для фермы Сервер Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-officewebappsmachine.md">New-OfficeWebAppsMachine</a></p></td>
<td><p>Добавление текущего сервера в ферму Сервер Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><a href="remove-officewebappshost.md">Remove-OfficeWebAppsHost</a></p></td>
<td><p>Удаляет несущий домен из списка разрешенных доменов для фермы Сервер Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><a href="remove-officewebappsmachine.md">Remove-OfficeWebAppsMachine</a></p></td>
<td><p>Удаление текущего сервера из фермы Сервер Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><a href="repair-officewebappsfarm.md">Repair-OfficeWebAppsFarm</a></p></td>
<td><p>Удаляет все серверы, отмеченные как неработоспособные, из фермы Сервер Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><a href="set-officewebappsfarm.md">Set-OfficeWebAppsFarm</a></p></td>
<td><p>Настройка параметров существующей фермы Сервер Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><a href="set-officewebappsmachine.md">Set-OfficeWebAppsMachine</a></p></td>
<td><p>Изменяет параметры текущего сервера в ферме Сервер Office Web Apps.</p></td>
</tr>
</tbody>
</table>


### Другие материалы по Office для ИТ-специалистов

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/Ee855124.22cad0f4-303d-4a40-90a3-fa08e69dfdaf(Office.15).png" title="Значок новых возможностей (поле)" alt="Значок новых возможностей (поле)" /></p></td>
<td><p><strong>Недавно опубликованные материалы</strong></p></td>
<td><p>В следующей статье представлен список новых или недавно обновленных статей, посвященных Сервер Office Web Apps.</p>
<ul>
<li><p><a href="https://technet.microsoft.com/ru-ru/library/ff433481(v=office.15)">Недавно опубликованные материалы по Office Web Apps и сервере Office Web Apps</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><img src="images/JJ219456.6b2d6dfa-7dc8-40fb-8335-af68b575f8cb(Office.15).png" title="Начало работы" alt="Начало работы" /></p></td>
<td><p><strong>Начало работы</strong></p></td>
<td><p>Скачайте Сервер Office Web Apps.</p>
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256561">Веб-сайт Microsoft Volume Licensing Service Center (VLSC)</a></p>
<p>Для загрузки Сервер Office Web Apps необходима лицензия на Office профессиональный плюс 2013, Office стандартный 2013 или Office для Mac 2011, предусмотренная соглашением о корпоративном лицензировании. Загружаемые файлы находятся в разделах на портале VLSC, посвященных продуктам Office.</p></li>
</ul>
<p>Скачайте языковые пакеты для Сервер Office Web Apps.</p>
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=263945">Центр загрузки Майкрософт</a></p></li>
</ul>
<p>Дополнительные сведения о сервере Office Web Apps.</p>
<ul>
<li><p><a href="deploy-the-infrastructure-office-web-apps-server.md">Развертывание инфраструктуры: Office Web Apps Server</a></p></li>
</ul>
<p>По следующим ссылкам вы узнаете, как в продуктах Office используется решение Сервер Office Web Apps, обеспечивающее просмотр и редактирование файлов Office через веб-браузер.</p>
<ul>
<li><p><a href="use-office-web-apps-with-sharepoint-2013.md">Совместное использование решений Office Web Apps и SharePoint 2013</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256902">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256611">Интеграция Office Web Apps Server (Exchange Server 2013)</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><img src="images/JJ219456.6fa793ee-ede9-4476-901c-de96ea37fc3a(Office.15).png" title="Значок беседы" alt="Значок беседы" /></p></td>
<td><p><strong>Отправьте отзыв</strong></p></td>
<td><p>Чтобы отправить отзыв по документации Office 2013Office 365 профессиональный плюс, выберите ссылку <strong>Обратная связь</strong> в нижней части страницы. Это позволит направить ваш отзыв непосредственно специалистам по разработке документации.</p>
<p><img src="images/JJ219456.1863f854-8ce5-40e4-bd40-9bbe16591834(Office.15).png" title="электронная почта" alt="электронная почта" />Чтобы предложить собственные материалы, запросить дополнительную документацию или сообщить об ошибке, свяжитесь с нами по адресу <a href="mailto:feedork@microsoft.com">feedork@microsoft.com</a>.</p></td>
</tr>
</tbody>
</table>


## Обучающие и другие материалы по Office


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Download</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/evalcenter/hh973391">Office 365 профессиональный плюс</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/p/?linkid=507653">Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/evalcenter/ee390818.aspx">Office 2013</a></p></li>
<li><p><a href="https://code.msdn.microsoft.com/office/">Примеры кода для Office</a></p></li>
<li><p><a href="https://gallery.technet.microsoft.com/office/">Сценарии и примеры файлов для Office</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/office/aa905351">Загрузки для разработчика Office</a></p></li>
<li><p><a href="http://www.microsoft.com/ru-ru/download/office.aspx?q=office">Загрузки для Office</a></p></li>
<li><p><a href="http://www.microsoft.com/ru-ru/download/search.aspx?q=office+365">Загрузки для Office 365</a></p></li>
</ul></td>
<td><p><strong>Практические руководства</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/ru-ru/library/jj220060.aspx">Создание приложений для Office</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/library/cc178982.aspx">Развертывание Office 2013</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/library/cc179068.aspx">Управление Office 2013</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/office/ff381682.aspx">Подготовка и обучение пользователей Office 2010</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/office/aa905496.aspx">Пакеты SDK Office</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/office/aa905375">Обучение разработчиков Office</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/msdn/ru-ru/office/media/video/video.html?cid=odc%26from=mscomodc">Видео для разработчиков Office</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/msdn/ru-ru/office/media/video/video.html?cid=o365%26from=mscomo365">Видео для разработчиков Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/office/ff519671">Обучение ИТ-специалистов по Office</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/technet/ru-ru/office/media/video/video.html?cid=otc%26from=mscomotc">Видео об Office для ИТ-специалистов</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/technet/ru-ru/office/media/video/video.html?cid=o365%26from=mscomo365">Видео об Office 365 для ИТ-специалистов</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/openspecifications/">Открытые спецификации</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/library/cc307282(v=office.12).aspx">Протоколы Office</a></p></li>
</ul></td>
<td><p><strong>Sites</strong></p>
<ul>
<li><p><a href="https://msdn.microsoft.com/ru-ru/office">Разработчики Office</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/office">ИТ-специалисты по Office</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/office/hh506337">Разработчики Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/hh912691">ИТ-специалисты по Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/library/cc303401.aspx">Набор ресурсов для Office 2013</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/sharepoint">Разработчики SharePoint</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/sharepoint">ИТ-специалисты по SharePoint</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/vstudio/aa718325">Разработчики Visual Studio</a></p></li>
<li><p><a href="http://office.microsoft.com/">Office.com</a></p></li>
</ul></td>
<td><p><strong>Help</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/ru-ru/office/ee748587.aspx">Обновления Office</a></p></li>
<li><p><a href="https://blogs.msdn.com/b/officeapps">Блог, посвященный приложениям для Office и SharePoint</a></p></li>
<li><p><a href="https://social.msdn.microsoft.com/forums/ru-ru/category/officedev%2coldevelopment%2csharepoint2010%2csharepoint%2cprojectserver2010%2cprojectprofessional2010%2cuc/">Форумы: Office для разработчиков</a></p></li>
<li><p><a href="https://answers.microsoft.com/ru-ru/msoffice">Форумы: Office 365</a></p></li>
<li><p><a href="https://social.technet.microsoft.com/wiki/ru-ru/">TechNet Wiki</a></p></li>
<li><p><a href="https://stackoverflow.com/search?q=office">Office на сайте StackOverflow</a></p></li>
<li><p><a href="https://mvp.microsoft.com/ru-ru/mvp/search-mvp.aspx?kw=office">Специалисты по Office со статусом MVP</a></p></li>
<li><p><a href="https://technet.microsoft.com/ru-ru/ms772425">Поддержка для ИТ-специалистов по Office</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ru-ru/office/aa905515">Техническая поддержка для разработчиков Office</a></p></li>
</ul></td>
</tr>
</tbody>
</table>


[](use-office-web-apps-with-sharepoint-2013.md)

