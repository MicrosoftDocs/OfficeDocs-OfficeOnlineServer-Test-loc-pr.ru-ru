---
title: Использование Windows PowerShell для администрирования SharePoint 2013
TOCTitle: Использование Windows PowerShell для администрирования SharePoint 2013
ms:assetid: ae4901b4-505a-42a9-b8d4-fca778abc12e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Ee806878(v=office.15)
ms:contentKeyID: 49624501
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Использование Windows PowerShell для администрирования SharePoint 2013

 

_**Применимо к:**SharePoint Foundation 2013, SharePoint Server 2013 Enterprise, SharePoint Server 2013 Standard_

_**Последнее изменение раздела:**2016-12-16_

**Сводка**. В этой статье приводятся сведения об основных командлетах Windows PowerShell и использовании Windows PowerShell в SharePoint 2013.

В этой статье

  - Общие сведения

  - Доступ к Windows PowerShell для продуктов SharePoint 2013

  - Разрешения

  - Скрипты и политики выполнения

  - Изучение Windows PowerShell

## Общие сведения

Оболочка командной строки Windows PowerShell предоставляет язык скриптов, обеспечивающий администратору полный доступ к API-интерфейсам. С ее помощью администраторы могут работать напрямую с SharePoint 2013, управляя веб-приложениями, семействами сайтов, сайтами, списками и многими другими элементами. Кроме того, администраторы могут создавать скрипты с использованием командлетов.

Windows PowerShell 3.0 является необходимым компонентом для установки SharePoint 2013. Эта оболочка устанавливается с помощью средства Средство подготовки продуктов Microsoft SharePoint. По умолчанию Windows PowerShell располагается по пути \<%SystemRoot%\>\\System32\\WindowsPowerShell\\v1.0\\PowerShell.exe.

Список новых возможностей Windows PowerShell 3.0 приводится в статье, посвященной платформе [Windows Management Framework 3.0](http://go.microsoft.com/fwlink/p/?linkid=272782)

Интерактивное средство и рекомендации по изучению синтаксиса Windows PowerShell см. в статье, посвященной [средству построения команд Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=229854), а также в [руководстве по началу работы](http://www.microsoft.com/en-us/download/details.aspx?id=27588).

Рекомендуем использовать Windows PowerShell при выполнении задач администрирования в командной строке. Командная строка Stsadm устарела, но включена для обеспечения совместимости с предыдущими версиями продукта.

## Доступ к Windows PowerShell для SharePoint 2013

После установки SharePoint 2013 существующие командлеты Windows PowerShell будут доступны в командной консоли Командная консоль SharePoint 2013. Для управления большинством элементов SharePoint 2013 используется командная консоль Командная консоль SharePoint. С ее помощью можно создавать новые семейства веб-сайтов, веб-приложения, учетные записи пользователей, приложения-службы, прокси и многое другое. Вводимые в командную консоль Командная консоль SharePoint команды возвращают объекты SharePoint на основе платформы Microsoft .NET Framework. Эти объекты можно использовать в качестве ввода для последующих команд или сохранить их как локальные переменные для последующего использования.

При использовании командной консоли Командная консоль SharePoint не требуется регистрировать оснастку, содержащую командлеты. Регистрация модуля Microsoft.SharePoint.PowerShell.dll для SharePoint 2013 осуществляется автоматически в результате выполнения строки `Add-PSSnapin Microsoft.SharePoint.PowerShell` в файле SharePoint.ps1, который расположен в папке *%CommonProgramFiles%*\\Microsoft Shared\\Web Server Extensions\\15\\Config\\PowerShell\\Registration. Если вы предпочитаете использовать консоль Windows PowerShell, эту оснастку необходимо зарегистрировать вручную.

При использовании командной консоли Командная консоль SharePoint и консоли Windows PowerShell вы имеете возможность загружать дополнительные оснастки. Дополнительные сведения см. в статье, посвященной [настройке профилей](http://go.microsoft.com/fwlink/p/?linkid=183166).

**Доступ к командной консоли Командная консоль SharePoint**

1.  Запустите Командная консоль SharePoint.
    
      - Для Windows Server 2008 R2:
        
          - Нажмите кнопку **Пуск** и последовательно выберите пункты **Продукты Продукты Microsoft SharePoint 2013** и **Командная консоль SharePoint**.
    
      - Для Windows Server 2012:
        
          - На **начальном** экране щелкните **Командная консоль SharePoint**.
            
            Если **Командная консоль SharePoint** отсутствует на **начальном** экране:
        
        <!-- end list -->
        
          - Щелкните правой кнопкой мыши **Компьютер**, выберите **Все приложения** и щелкните **Командная консоль SharePoint**.
    
    Дополнительные сведения о взаимодействии с Windows Server 2012 см. в статье [Общие задачи управления и навигации в Windows Server 2012](http://technet.microsoft.com/ru-ru/library/hh831491.aspx).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Командная консоль Командная консоль SharePoint 2013 и консоль Windows PowerShell разным способом используют параметр <code>ReuseThread</code>, который определяет порядок использования потоковой модели. Командная консоль Командная консоль SharePoint 2013 использует потоковую модель в соответствии с определением в строке <code>{Host.Runspace.ThreadOptions = &quot;ReuseThread&quot;}</code> файла SharePoint.ps1. Дополнительные сведения см. в статье, посвященной <a href="http://go.microsoft.com/fwlink/p/?linkid=183145">параметрам потоковой модели PS</a>.</td>
</tr>
</tbody>
</table>


## Разрешения

## Локальные

Прежде чем использовать командлет **Add-SPShellAdmin**, чтобы предоставить пользователям разрешения на выполнение командлетов SharePoint 2013, убедитесь в том, что соблюдены следующие минимальные требования:

  - Вы должны являться участником предопределенной роли сервера **securityadmin** для экземпляра SQL Server.

  - Вы должны являться участником предопределенной базы данных **db\_owner** на всех базах данных, которые вы планируете обновить.

  - Вы должны входить в группу "Администраторы" сервера, на котором выполняется командлет Windows PowerShell.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если этих разрешений недостаточно, обратитесь к администратору установки или администратору SQL Server за дополнительными разрешениями.</td>
</tr>
</tbody>
</table>


Дополнительные сведения о разрешениях Windows PowerShell см. в разделах Разрешения и [Add-SPShellAdmin](https://technet.microsoft.com/ru-ru/library/ff607596\(v=office.15\))

Если вы не являетесь участником роли **SharePoint\_Shell\_Access** или локальной группы **WSS\_Admin\_WPG**, используйте командлет **Add-SPShellAdmin** для добавления группы **WSS\_Admin\_WPG** на все интерфейсные веб-серверы в ферме SharePoint и в роль **SharePoint\_Shell\_Access**. Если в базе данных SQL Server отсутствует роль **SharePoint\_Shell\_Access**, она автоматически создается при выполнении командлета **Add-SPShellAdmin**. После выполнения командлета **Add-SPShellAdmin** пользователи могут выполнять командлеты SharePoint Windows PowerShell в среде фермы с несколькими серверами.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219451.note(Office.15).gif" title="Примечание" alt="Примечание" /><strong>Примечание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Учетной записи пользователя, под которой выполнялась установка SharePoint 2013, предоставляются соответствующие разрешения на выполнение командлетов Windows PowerShell. Если вам требуется предоставить разрешения на выполнение командлетов Windows PowerShell другим пользователям, используйте для этого командлет <strong>Add-SPShellAdmin</strong>.</td>
</tr>
</tbody>
</table>


Для этого запустите командлет **Add-SPShellAdmin** для всех баз данных, к которым необходимо предоставить доступ. Если база данных не указана, по умолчанию используется база данных конфигурации фермы. Если база данных указана, база данных конфигурации фермы будет включена в дополнение к указанной базе данных.

Чтобы просмотреть список всех командлетов **SPShellAdmin**, введите в командной строке Windows PowerShell команду `Get-Command -Noun SPShellAdmin`.

## SharePoint Online

Убедитесь, что у вас есть следующие административные разрешения.

  - Вам должна быть назначена роль глобального администратора сайта SharePoint Online, на котором выполняется командлет Windows PowerShell. Дополнительные сведения см. в статье, посвященной [группам пользователей и административным ролям по умолчанию](http://go.microsoft.com/fwlink/p/?linkid=242451).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ219455.important(Office.15).gif" title="Важно" alt="Важно" /><strong>Важно!</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Вы можете использовать конкретную группу Windows PowerShell с SharePoint Online. Дополнительные сведения см. в разделе <a href="https://technet.microsoft.com/ru-ru/library/fp161362(v=office.15)">PowerShell Office 365 для SharePoint Online</a>.</td>
    </tr>
    </tbody>
    </table>


## Скрипты и политики выполнения

С помощью Windows PowerShell вы можете выполнять как отдельные задачи по администрированию, так и последовательности задач, которые автоматизируются с помощью скриптов. Скрипт представляет собой текстовый файл с одной или несколькими командами Windows PowerShell. Файлы скриптов Windows PowerShell имеют расширение ps1.

Для выполнения скриптов требуется минимальный уровень политики выполнения SharePoint 2013 RemoteSigned (по умолчанию установлен уровень Windows PowerShell Restricted). Если вы оставите уровень политики Restricted, командная консоль Командная консоль SharePoint 2013 автоматически изменит уровень политики для Windows PowerShell на RemoteSigned. Это означает, что вам необходимо использовать команду **Запуск от имени администратора** для запуска командной консоли Командная консоль SharePoint 2013 с повышенными разрешениями администратора. Это изменение будет применяться ко всем сеансам Windows PowerShell. Дополнительные сведения см. в статье, посвященной [перечислению ExecutionPolicy](http://go.microsoft.com/fwlink/p/?linkid=242452).

Дополнительные сведения о скриптах и политиках выполнения см. в статьях [о\_скриптах](http://go.microsoft.com/fwlink/p/?linkid=144310) и [о\_политиках\_выполнения](http://go.microsoft.com/fwlink/p/?linkid=193050) соответственно.

## Изучение Windows PowerShell

Мы предлагаем несколько обучающих ресурсов по Windows PowerShell для ИТ-специалистов SharePoint.

**Центр скриптов TechNet**

В центре скриптов TechNet представлен обширный выбор материалов по изучению основ работы с Windows PowerShell. Здесь также имеется репозиторий с образцами скриптов, часто используемых в различных продуктах Майкрософт. В следующей таблице перечислены основные обучающие ресурсы.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Страница</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187813">Документация по Windows PowerShell на сайте TechNet</a></p></td>
<td><p>В этом разделе библиотеки TechNet представлены веб-копии основных тем справки по командлету Windows PowerShell Get-Help. Здесь также можно найти веб-копии документа &quot;Приступая к работе с Windows PowerShell&quot;, справку по программе PowerShell.exe и краткое руководство по Windows PowerShell.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187815">Создание скриптов Windows PowerShell</a></p></td>
<td><p>Домашняя страница обучающего ресурса по созданию скриптов Windows PowerShell.</p></td>
</tr>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187817">Руководство владельца Windows PowerShell</a></p></td>
<td><p>Интерактивное руководство по основным операциям Windows PowerShell.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187819">Краткий справочник по Windows PowerShell</a></p></td>
<td><p>Загружаемая копия краткого справочника, который устанавливается вместе с Windows PowerShell.</p></td>
</tr>
</tbody>
</table>


Перед изучением этих ресурсов и использованием Windows PowerShell для продуктов SharePoint 2013 рекомендуется ознакомиться со следующими командлетами:

  - [Get-Command](http://go.microsoft.com/fwlink/p/?linkid=171069)

  - [Get-Member](http://go.microsoft.com/fwlink/p/?linkid=171070)

  - [Get-Help](http://go.microsoft.com/fwlink/p/?linkid=171068)

  - [Создание псевдонимов](http://go.microsoft.com/fwlink/p/?linkid=113207)

  - [Каналы и конвейер Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=187808)

  - [Наборы параметров командлетов](http://go.microsoft.com/fwlink/p/?linkid=187810)

  - [Foreach-Object](http://go.microsoft.com/fwlink/p/?linkid=187812)

  - [Where-Object](http://go.microsoft.com/fwlink/p/?linkid=187811)

