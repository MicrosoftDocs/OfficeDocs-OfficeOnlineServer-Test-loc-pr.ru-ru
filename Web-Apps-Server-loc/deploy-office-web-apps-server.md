---
title: Развертывание сервера Office Web Apps
TOCTitle: Развертывание сервера Office Web Apps
ms:assetid: e4d51dc4-6460-437d-aa8e-0ae4d3aa8cc5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ219455(v=office.15)
ms:contentKeyID: 49624516
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Развертывание сервера Office Web Apps

 

_**Применимо к:**Office Web Apps Server_

_**Последнее изменение раздела:**2017-10-05_

**Сводка**. Узнайте, как развернуть Сервер Office Web Apps в локальной среде для использования в SharePoint 2013 и Lync Server 2013.

**Аудитория:** ИТ-специалисты

Обратите внимание, что в этой статье описано, как установить Сервер Office Web Apps для компании. Справку по установке Office или Office Web Apps для личного использования см. на сайте <https://support.office.com>.

Чтобы развернуть [сервер Office Web Apps](office-web-apps-server-overview.md), требуется установить некоторые необходимые компоненты и выполнить несколько команд Windows PowerShell, но, в целом, сам процесс довольно прост. В этой статье описывается подготовка серверов, а также команды Windows PowerShell для настройки фермы Сервер Office Web Apps.

В этой статье

  - Посмотрите видео, чтобы узнать, как это делается

  - Изучите эти ресурсы, прежде чем начать

  - Подготовка серверов для запуска сервера Office Web Apps

  - Развертывание фермы сервера Office Web Apps

  - Сообщения об ошибке "500 Исключения веб-службы" и "500.21 — внутренняя ошибка сервера"

## Посмотрите видео, чтобы узнать, как это делается

Посмотрите следующее видео, чтобы узнать, как настроить Сервер Office Web Apps в тестовой среде. Вы также узнаете, как настроить SharePoint 2013 для использования Сервер Office Web Apps.

**Настройка фермы сервера Office Web Apps в тестовой среде**

> [!VIDEO https://www.microsoft.com/ru-ru/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

## Изучите эти ресурсы, прежде чем начать

Перед началом работы обязательно ознакомьтесь со следующими ресурсами:

  - Подробнее о требованиях к оборудованию и программному обеспечению см. в [рекомендациях по планированию](plan-office-web-apps-server.md).

  - По умолчанию в Сервер Office Web Apps можно просматривать файлы Office, но невозможно редактировать их. Чтобы редактировать файлы, необходима лицензия на редактирование, о которой можно прочитать в статьях [Планирование Office Web Apps (используется вместе с SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md) и [Настройка лицензирования в SharePoint Server 2013](https://technet.microsoft.com/ru-ru/library/jj219627\(v=office.15\)).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для работы во всех наборах Наборы приложений Office 2013 можно использовать мышь, сочетания клавиш и сенсорные жесты. Дополнительные сведения об использовании сочетаний клавиш и сенсорных жестов в службах и продуктах Office см. в следующих статьях: <a href="https://go.microsoft.com/fwlink/p/?linkid=249150">Сочетания клавиш</a>, <a href="https://go.microsoft.com/fwlink/p/?linkid=253163">Справочник по сенсорному управлению в Office</a>.</td>
</tr>
</tbody>
</table>


## Подготовка серверов для запуска сервера Office Web Apps

Выполните следующие процедуры на всех серверах, где будет работать сервер Сервер Office Web Apps.

**Рисунок. Действия для подготовки серверов для сервера Office Web Apps**

![Три основных шага для подготовки серверов для сервера Office Web Apps.](images/JJ219455.af2a4690-4f8b-42c3-aab5-f7066bc0a936(Office.15).gif "Три основных шага для подготовки серверов для сервера Office Web Apps.") 

## Шаг 1. Установите необходимое программное обеспечение для сервера Office Web Apps

Предварительные требования для Windows Server 2008 R2, Windows Server 2012 и Windows Server 2012 R2 слегка отличаются. Выберите соответствующую процедуру ниже, чтобы установить правильные необходимые компоненты для вашей операционной системы.

**В Windows Server 2008 R2**

1.  Установите следующее программное обеспечение:
    
      - [Windows Server 2008 R2 с пакетом обновления 1](http://go.microsoft.com/fwlink/p/?linkid=252370)
    
      - [.NET Framework 4.5](https://go.microsoft.com/fwlink/p/?linkid=256560)
    
      - [Windows PowerShell 3.0](https://go.microsoft.com/fwlink/p/?linkid=244693)
    
      - [Обновление платформы для Windows 7 с пакетом обновления 1 (SP1) и Windows Server 2008 R2 с пакетом обновления 1 (SP1) (KB2670838)](https://go.microsoft.com/fwlink/p/?linkid=293629)

2.  Откройте командную строку Windows PowerShell в качестве администратора и выполните следующие команды, чтобы установить необходимые роли и службы.
    
        Import-Module ServerManager
    
    Затем выполните команду.
    
        Add-WindowsFeature Web-Server,Web-WebServer,Web-Common-Http,Web-Static-Content,Web-App-Dev,Web-Asp-Net,Web-Net-Ext,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,Web-Security,Web-Windows-Auth,Web-Filtering,Web-Stat-Compression,Web-Dyn-Compression,Web-Mgmt-Console,Ink-Handwriting,IH-Ink-Support,NET-Framework,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-Win-CFAC
    
    При получении запроса перезагрузите сервер.

**В Windows Server 2012**

1.  Откройте командную строку Windows PowerShell в качестве администратора и выполните следующую команду, чтобы установить необходимые роли и службы.
    
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    
    При получении запроса перезагрузите сервер.

**В Windows Server 2012 R2**

1.  Установите такое программное обеспечение:
    
      - [.NET Framework 4.5.2](https://go.microsoft.com/fwlink/p/?linkid=510096)

2.  Войдя под учетными данными администратора, откройте командную строку Windows PowerShell и выполните приведенную ниже команду, чтобы установить необходимые роли и службы.
    
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    
    При получении запроса перезагрузите сервер.

## Шаг 2. Установка сервера Office Web Apps и связанных обновлений

Выполните следующие действия на всех серверах, где будет работать Сервер Office Web Apps.

1.  Скачайте Сервер Office Web Apps на веб-сайте [Volume Licensing Service Center (VLSC)](https://go.microsoft.com/fwlink/p/?linkid=256561). Чтобы скачать Сервер Office Web Apps, необходима лицензия Office профессиональный плюс 2013, Office стандартный 2013 или Office для Mac 2011, предусмотренная соглашением о корпоративном лицензировании. Загружаемые файлы находятся в разделах на портале VLSC, посвященных продуктам Office.

2.  Выполните одно из указанных ниже действий.
    
      - Для Windows Server 2012 или Windows Server 2012 R2 напрямую откройте IMG-файл и запустите программу **Setup.exe**.
    
      - Для Windows Server 2008 R2 с пакетом обновления 1 (SP1) используйте программу, которая может подключить или извлечь IMG-файлы. Затем запустите программу **Setup.exe**.

3.  На странице **Условия лицензионного соглашения на использование программного обеспечения корпорации Майкрософт** установите флажок **Я принимаю условия этого соглашения** и нажмите кнопку **Продолжить**.

4.  На странице **Выбор расположения файла** выберите папку, в которой следует установить файлы Сервер Office Web Apps (например, C:\\Program Files\\Microsoft Office Web Apps), затем выберите пункт **Установить**. Если указанная папка не существует, программа установки создаст ее самостоятельно.
    
    Мы рекомендуем устанавливать Сервер Office Web Apps на системном диске.

5.  Когда установка сервера Сервер Office Web Apps завершится, нажмите кнопку **Закрыть**

6.  Скачайте и установите [сервер Office Web Apps с пакетом обновления 1 (SP1)](https://go.microsoft.com/fwlink/p/?linkid=510097). (Рекомендовано для Windows Server 2012 и Windows Server 2008 R2 с пакетом обновления 1 (SP1). Обязательно для Windows Server 2012 R2.)
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Применяя сервер Office Web Apps с пакетом обновления 1 (SP1), следуйте указаниям в разделе <a href="apply-software-updates-to-office-web-apps-server.md">Применение обновлений программного обеспечения к серверу Office Web Apps</a>.</td>
    </tr>
    </tbody>
    </table>


7.  Проверьте наличие обновлений Сервер Office Web Apps, просмотрев список в [Центре обновлений TechNet для Office, серверов Office и связанных продуктов](https://go.microsoft.com/fwlink/p/?linkid=280271).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если вы не установили сервер Office Web Apps с пакетом обновления 1 (SP1), примените обновление <a href="https://go.microsoft.com/fwlink/p/?linkid=296579">KB2810007</a>.</td>
    </tr>
    </tbody>
    </table>


## Шаг 3. Установка языковых пакетов для сервера Office Web Apps

Языковые пакеты Сервер Office Web Apps 2013 позволяют пользователям просматривать многоязычные Интернет-файлы Office, открытые из библиотек документов SharePoint 2013, Outlook Web Access (в виде предварительного просмотра вложений) и Lync 2013 (в виде широковещательных презентаций PowerPoint). Подробнее о работе языковых пакетов см. в статье [Планирование языковых пакетов для сервера Office Web Apps](plan-office-web-apps-server.md).

Для установки языковых пакетов выполните следующие действия.


1.  Скачайте языковые пакеты Сервер Office Web Apps из [Центра загрузки Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=263945).

2.  Запустите программу **WebAppsServerLP\_en-us\_x64.exe**.

3.  На странице **Условия лицензионного соглашения на использование программного обеспечения корпорации Майкрософт** мастера языковых пакетов Сервер Office Web Apps 2013 установите флажок **Я принимаю условия этого соглашения** и нажмите кнопку **Продолжить**.

4.  Когда установка сервера Сервер Office Web Apps завершится, нажмите кнопку **Закрыть**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Чтобы установить языковые пакеты после создания фермы серверов Сервер Office Web Apps, необходимо удалить сервер из фермы, установить на него языковой пакет, а затем вернуть этот сервер обратно в ферму.</p></li>
<li><p>Чтобы языковой пакет работал правильно, его необходимо установить на все серверы в ферме.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Развертывание фермы сервера Office Web Apps Server

Выполните процедуры в одном из следующих разделов в зависимости от создаваемой фермы Сервер Office Web Apps.


> [!TIP]
> Если Windows PowerShell не распознает командлет <STRONG>New-OfficeWebAppsFarm</STRONG> при его выполнении, возможно, вам потребуется импортировать модуль <STRONG>OfficeWebApps</STRONG>. Используйте команду:<BR><CODE>Import-Module -Name OfficeWebApps</CODE>



## Развертывание фермы сервера Office Web Apps, состоящей из отдельного сервера и поддерживающей HTTPS

Если вы развертываете Сервер Office Web Apps только для тестирования или внутреннего использования и вам не нужно предоставить функции Сервер Office Web AppsLync Server 2013, эта процедура для вас. Она позволит установить ферму Сервер Office Web Apps из одного сервера, которая использует HTTP. Вам не понадобится сертификат или подсистема балансировки нагрузки, но потребуется выделенный физический сервер или экземпляр виртуальной машины, на котором не запущены другие серверные приложения.

Вы можете использовать эту ферму Сервер Office Web Apps в качестве сервера Office Web Apps для SharePoint 2013.

**Рисунок. Шаги для развертывания сервера Office Web Apps**

![Три основных шага для развертывания фермы сервера Office Web Apps, состоящей из одного сервера.](images/JJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif "Три основных шага для развертывания фермы сервера Office Web Apps, состоящей из одного сервера.")

## Шаг 1. Создание фермы серверов Office Web Apps

Выполните команду **New-OfficeWebAppsFarm**, чтобы создать новую ферму Сервер Office Web Apps, состоящую из одного сервера, как показано в следующем примере.

    New-OfficeWebAppsFarm -InternalURL "http://servername" -AllowHttp -EditingEnabled

**Параметры**

  - **–InternalURL** — это имя сервера, на котором работает Сервер Office Web Apps, например **http://имя\_сервера**.

  - Параметр **–AllowHttp** настраивает ферму на использование протокола HTTP.

  - **–EditingEnabled** включает редактирование в Office Web Apps при использовании вместе с SharePoint 2013. Этот параметр не используется Lync Server 2013, так как этот узел не поддерживает редактирование.

Дополнительные параметры, настраивающие службы транзакций, прокси-серверы, поддержку клипов и средства просмотра Online Viewer, описываются в статье [New-OfficeWebAppsFarm](new-officewebappsfarm.md).

Сообщения об ошибке "500 Исключения веб-службы" и "500.21 — внутренняя ошибка сервера"

## Шаг 2. Проверка успешного создания фермы серверов Office Web Apps

После создания фермы в командной строке Windows PowerShell отображаются сведения о ней. Чтобы проверить правильность установки и настройки Сервер Office Web Apps, откройте URL-адрес обнаружения Сервер Office Web Apps с помощью браузера, как показано в следующем примере. Этот URL-адрес — это параметр *InternalUrl*, заданный при настройке фермы Сервер Office Web Apps, с добавлением **/hosting/discovery**. Например:

    http://servername/hosting/discovery

Если Сервер Office Web Apps работает без ошибок, в веб-браузере должен открыться XML-файл обнаружения для интерфейса открытой платформы веб-приложений (WOPI). Первые строки этого файла должны содержать примерно следующий текст:

    <?xml version="1.0" encoding="utf-8" ?> 
    - <wopi-discovery>
    - <net-zone name="internal-http">
    - <app name="Excel" favIconUrl="http://servername/x/_layouts/images/FavIcon_Excel.ico" checkLicense="true">
    <action name="view" ext="ods" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xls" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xlsb" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xlsm" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 

## Шаг 3. Настройка узла

Теперь ферму можно использовать в качестве сервера Office Web Apps для узлов по HTTP. Дополнительные сведения о настройке узлов см. в статье [Настройка Office Web Apps для SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md).

## Развертывание фермы сервера Office Web Apps, состоящей из отдельного сервера и поддерживающей HTTPS

Для большинства рабочих сред мы настоятельно рекомендуем использовать протокол HTTPS из-за его функций защиты. Кроме того, HTTPS необходим, если вы хотите предоставлять функции Сервер Office Web AppsLync Server 2013, чтобы пользователи могли просматривать широковещательные показы презентаций PowerPoint в браузере. Вот как установить ферму Сервер Office Web Apps с одним сервером, которая использует HTTPS. Вам потребуется установить сертификат на сервер, как описано в статье [Обеспечение безопасности связи Office Web Apps Server с помощью HTTPS](plan-office-web-apps-server.md).

Эта ферма Сервер Office Web Apps будет использоваться в качестве сервера Office Web Apps для SharePoint 2013 и Lync Server 2013.

**Рисунок. Шаги для развертывания сервера Office Web Apps**

![Три основных шага для развертывания фермы сервера Office Web Apps, состоящей из одного сервера.](images/JJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif "Три основных шага для развертывания фермы сервера Office Web Apps, состоящей из одного сервера.")

## Шаг 1. Создание фермы серверов Office Web Apps

Выполните команду **New-OfficeWebAppsFarm**, чтобы создать новую ферму Сервер Office Web Apps, состоящую из одного сервера, как показано в следующем примере.

    New-OfficeWebAppsFarm -InternalUrl "https://server.contoso.com" -ExternalUrl "https://wacweb01.contoso.com" -CertificateName "OfficeWebApps Certificate" -EditingEnabled

**Параметры**

  - **–InternalURL** — это полное доменное имя сервера, на котором работает Сервер Office Web Apps, например **http://имя\_сервера.contoso.com**.

  - **–ExternalURL** — это полное доменное имя, которое будет доступно из Интернета.

  - **–CertificateName** — это понятное имя сертификата.

  - **–EditingEnabled** — это необязательный параметр, который включает редактирование в Office Web Apps при использовании вместе с SharePoint 2013. Этот параметр не используется Lync Server 2013, так как этот узел не поддерживает редактирование.

Дополнительные параметры, настраивающие службы транзакций, прокси-серверы, поддержку клипов и средства просмотра Online Viewer, описываются в статье [New-OfficeWebAppsFarm](new-officewebappsfarm.md).

Сообщения об ошибке "500 Исключения веб-службы" и "500.21 — внутренняя ошибка сервера"

## Шаг 2. Проверка успешного создания фермы серверов Office Web Apps

После создания фермы в командной строке Windows PowerShell отображаются сведения о ней. Чтобы проверить правильность установки и настройки Сервер Office Web Apps, откройте URL-адрес обнаружения Сервер Office Web Apps с помощью браузера, как показано в следующем примере. Этот URL-адрес — это параметр *InternalUrl*, заданный при настройке фермы Сервер Office Web Apps, с добавлением **/hosting/discovery**. Например:

    https://server.contoso.com/hosting/discovery

Если Сервер Office Web Apps работает без ошибок, в веб-браузере должен открыться XML-файл обнаружения для интерфейса открытой платформы веб-приложений (WOPI). Первые строки этого файла должны содержать примерно следующий текст:

``` 
<?xml version="1.0" encoding="UTF-8"?>
<wopi-discovery><net-zone 
name="internal-https"><app name="Excel" checkLicense="true" 
favIconUrl="https://wac.contoso.com/x/_layouts/images/FavIcon_Excel.ico"><action 
name="view" 
urlsrc="https://wac.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" 
default="true" ext="ods"/><action name="view" 
urlsrc="https://wac.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" 
default="true" ext="xls"/><action name="view"
 
```

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В зависимости от параметров безопасности в используемом браузере может появиться запрос на включение параметра <strong>Показать все содержимое</strong>, прежде чем будет отображено содержимое XML-файла обнаружения.</td>
</tr>
</tbody>
</table>


## Шаг 3. Настройка узла

Теперь ферма готова и может предоставлять узлам функции Office Web Apps по протоколу HTTPS. Подробнее о настройке узлов см. в следующих статьях.

  - [Настройка Office Web Apps для SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)

  - [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

## Развертывание многосерверной фермы сервера Office Web Apps, поддерживающей балансировку сетевой нагрузки и протокол HTTPS

Если вы ожидаете, что в ферму Сервер Office Web Apps будет поступать большой объем трафика, и хотите, чтобы она была доступна из Интернета и внутренней сети, этот тип топологии — то, что вам нужно. В этом разделе описывается, как установить многосерверную ферму Сервер Office Web Apps, которая использует подсистему балансировки нагрузки и HTTPS. Если вы заинтересованы, [узнайте больше об этой топологии](plan-office-web-apps-server.md).

Прежде чем начать, убедитесь, что балансировщик нагрузки настроен, как описано в разделе [Требования сервера Office Web Apps к подсистеме балансировки нагрузки](plan-office-web-apps-server.md). Кроме того, на балансировщике нагрузки необходимо установить сертификат, как описано в разделе [Защита данных, передаваемых сервером Office Web Apps, с помощью протокола HTTPS](plan-office-web-apps-server.md). Эта ферма Сервер Office Web Apps будет использоваться в качестве сервера Office Web Apps для SharePoint 2013 и Lync Server 2013.

**Рисунок. Шаги для развертывания сервера Office Web Apps**

![Четыре основных шага для развертывания фермы сервера Office Web Apps, состоящей из нескольких серверов.](images/JJ219455.4c4b31cb-961b-4efd-b755-a18bdcb5c191(Office.15).gif "Четыре основных шага для развертывания фермы сервера Office Web Apps, состоящей из нескольких серверов.")

## Шаг 1. Создание фермы сервера Office Web Apps на первом сервере

Выполните команду **New-OfficeWebAppsFarm**, чтобы создать новую ферму Сервер Office Web Apps на первом сервере, как показано в следующем примере.

    New-OfficeWebAppsFarm -InternalUrl "https://server.contoso.com" -ExternalUrl "https://wacweb01.contoso.com" -SSLOffloaded -EditingEnabled

**Параметры**

  - **–InternalURL** — это полное доменное имя сервера, на котором работает Сервер Office Web Apps, например **http://имя\_сервера.contoso.com**.

  - **–ExternalURL** — это полное доменное имя, которое будет доступно из Интернета.

  - **–SSLOffloaded** позволяет перенести нагрузку терминирования SSL на подсистему балансировки нагрузки.

  - **–EditingEnabled** — это необязательный параметр, который включает редактирование в Office Web Apps при использовании вместе с SharePoint 2013. Этот параметр не используется Lync Server 2013, так как этот узел не поддерживает редактирование.

Дополнительные параметры, настраивающие службы транзакций, прокси-серверы, поддержку клипов и средства просмотра Online Viewer, описываются в статье [New-OfficeWebAppsFarm](new-officewebappsfarm.md).

Сообщения об ошибке "500 Исключения веб-службы" и "500.21 — внутренняя ошибка сервера"

## Шаг 2. Добавьте дополнительные серверы в ферму

После запуска Сервер Office Web Apps на первом сервере выполните команду **New-OfficeWebAppsMachine** на каждом сервере, который нужно добавить в ферму Сервер Office Web Apps. В параметре **–MachineToJoin** укажите имя компьютера одного из серверов, уже входящих в ферму Сервер Office Web Apps. Например, если server1.contoso.com уже добавлен в ферму, используйте следующую команду:

    New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"

Хотите узнать больше этих параметрах? Их можно найти в разделе [New-OfficeWebAppsMachine](new-officewebappsmachine.md).

## Шаг 3. Проверьте, успешно ли создана ферма серверов Office Web Apps

После создания фермы в командной строке Windows PowerShell отображаются сведения о ней. Чтобы проверить правильность установки и настройки Сервер Office Web Apps, откройте URL-адрес обнаружения Сервер Office Web Apps с помощью браузера, как показано в следующем примере. Этот URL-адрес — это параметр *InternalUrl*, заданный при настройке фермы Сервер Office Web Apps, с добавлением **/hosting/discovery**. Например:

    https://server.contoso.com/hosting/discovery

Если Сервер Office Web Apps работает без ошибок, в веб-браузере должен открыться XML-файл обнаружения для интерфейса открытой платформы веб-приложений (WOPI). Первые строки этого файла должны содержать примерно следующий текст:

    <?xml version="1.0" encoding="UTF-8"?>
    <wopi-discovery><net-zone name="internal-https"><app name="Excel" checkLicense="true" favIconUrl="https://officewebapps.contoso.com/x/_layouts/images/FavIcon_Excel.ico"><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="ods"/><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="xls"/><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="xlsb"/> 

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В зависимости от параметров безопасности в используемом браузере может появиться запрос на включение параметра <strong>Показать все содержимое</strong>, прежде чем будет отображено содержимое XML-файла обнаружения.</td>
</tr>
</tbody>
</table>


## Шаг 4. Настройте узел

Теперь ферма готова и может предоставлять узлам функции Office Web Apps по протоколу HTTPS. Подробнее о настройке узлов см. в следующих статьях.

  - [Настройка Office Web Apps для SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)

  - [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

## Сообщения об ошибке "500 Исключения веб-службы" и "500.21 — внутренняя ошибка сервера"

Если установленные компоненты .NET Framework 3.5 были удалены, при попытке выполнить командлеты OfficeWebApps могут отображаться сообщения "500 Исключения веб-службы" или "500.21 — внутренняя ошибка сервера". Чтобы устранить эти ошибки, выполните следующие команды из командной строки с повышенными привилегиями для очистки параметров, мешающих правильной работе сервера Сервер Office Web Apps:

**Для Windows Server 2008 R2**

```
    %systemroot%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -iru
```
```
    iisreset /restart /noforce
```

**Для Windows Server 2012 или Windows Server 2012 R2**

    dism /online /enable-feature /featurename:IIS-ASPNET45

## См. также


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Планирование сервера Office Web Apps](plan-office-web-apps-server.md)  
[Настройка Office Web Apps для SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)  


[Развертывание Office Web Apps Server и Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)  
  

[](configure-office-web-apps-for-sharepoint-2013.md)

