---
title: Применение обновлений программного обеспечения к серверу Office Web Apps
TOCTitle: Применение обновлений программного обеспечения к серверу Office Web Apps
ms:assetid: 5d15dbd9-374e-422a-a870-43270dd0a2db
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ966220(v=office.15)
ms:contentKeyID: 51658503
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Применение обновлений программного обеспечения к серверу Office Web Apps 

_<strong>Применимо к:</strong> Office Web Apps Server_

_<strong>Последнее изменение раздела:</strong> 2016-12-16_

**Сводка**. Сведения о применении обновлений программного обеспечения к ферме серверов Office Web Apps.

**Аудитория:** ИТ-специалисты

После нового выпуска Сервер Office Web Apps компания Microsoft создает серию обновлений программного обеспечения для повышения безопасности, эффективности и надежности сервера. В этой статье описывается процесс применения обновлений программного обеспечения к отдельным серверам фермы Сервер Office Web Apps.

> [!IMPORTANT]
> Эта статья входит в состав набора <a href="content-roadmap-for-office-web-apps-server.md">План содержимого для сервера Office Web Apps</a>. Используйте этот обзор в качестве начального этапа для поиска статей, загружаемых файлов и видеозаписей, помогающих развернуть Сервер Office Web Apps и управлять им.<br />
<strong>Нужна помощь с Office Web Apps на рабочем столе или мобильном устройстве?</strong> Для этого можно выполнить поиск по словам &quot;Office Web Apps&quot; на сайте <a href="http://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</a>.


> [!WARNING]
> Применение обновлений Сервер Office Web Apps с использованием автоматического процесса обновления не поддерживается Сервер Office Web Apps, поскольку обновления к Сервер Office Web Apps должны применяться особым образом, описанным в данной статье. Если применять обновления Сервер Office Web Apps автоматически, пользователи, возможно, не смогут просматривать и редактировать документы в Office Web Apps. В таком случае необходимо выполнить перестройку фермы Сервер Office Web Apps. Для этого нужно удалить Сервер Office Web Apps из фермы с помощью <a href="https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps">Remove-OfficeWebAppsMachine</a>, удалить Сервер Office Web Apps с помощью приложения или программы удаления и переустановить Сервер Office Web Apps, следуя пошаговым инструкциям из статьи <a href="deploy-office-web-apps-server.md">Развертывание сервера Office Web Apps</a>. После переустановки примените обновление согласно инструкциям из данной статьи.<br />
Необходимо также прочитать указания из раздела о <a href="plan-office-web-apps-server.md">планировании обновлений для сервера Office Web Apps</a> и внедрить процесс обновления для фермы Сервер Office Web Apps.

## Перед началом работы

Список самых последних доступных обновлений для Сервер Office Web Apps см. в блоге [Microsoft Office Updates](http://go.microsoft.com/fwlink/p/?linkid=280269) и в [центре обновления TechNet (TechNet Update center for Office, Office servers, and related products)](http://go.microsoft.com/fwlink/p/?linkid=280271).

Обновления, выпущенные для Сервер Office Web Apps, будут обновлять Сервер Office Web Apps и любые установленные языковые пакеты Сервер Office Web Apps. Отдельных обновлений для языковых пакетов Сервер Office Web Apps не существует.

При обновлении вам придется создать ферму Сервер Office Web Apps заново. Чтобы подготовиться повторно создать ферму Сервер Office Web Apps, просмотрите свойства текущей фермы Сервер Office Web Apps с помощью командлета Windows PowerShell**Get-OfficeWebAppFarm**, а также параметры [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps). Параметры, используемые для **New-OfficeWebAppsFarm**, должны совпадать с теми, которые использовались при первой настройке фермы Сервер Office Web Apps.

> [!NOTE]
> Задачи, приведенные в этой статье, можно выполнять мышью, сочетаниями клавиш на клавиатуре или сенсорными жестами. Дополнительные сведения см. в следующих источниках.
> <ul>
> <li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=249150">Сочетания клавиш</a></p></li>
> <li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=249151">Сенсорные жесты</a></p></li>
> </ul>


## Применение обновлений программного обеспечения к ферме Office Web Apps из одного сервера

Чтобы применить обновления программного обеспечения к ферме Сервер Office Web Apps из одного сервера, удалите Сервер Office Web Apps из фермы, примените обновление и заново создайте ферму Сервер Office Web Apps. Если в состав фермы входит только один сервер, Сервер Office Web Apps пользователи не смогут использовать Office Web Apps во время обновления. Поэтому планируйте обновление Сервер Office Web Apps на нерабочее время (или время, когда перерыв в работе не критичен).

**Чтобы применить обновления к ферме из одного сервера**

1.  Если обновление Сервер Office Web Apps еще не загружено, загрузите обновление Сервер Office Web Apps, которое необходимо применить, из [Центра загрузки Майкрософт](http://go.microsoft.com/fwlink/p/?linkid=280274).

2.  На сервере Сервер Office Web Apps, к которому нужно применить обновление программного обеспечения, под учетной записью администратора откройте командную строку Windows PowerShell и запустите следующую команду.
    
    ```PowerShell
        Remove-OfficeWebAppsMachine
    ```

3.  Установите обновление Сервер Office Web Apps на данный сервер. При необходимости выполните перезагрузку.

4.  Под учетной записью администратора откройте командную строку Windows PowerShell и запустите командлет **New-OfficeWebAppsFarm** для создания фермы Сервер Office Web Apps заново. URL-адрес, определяемый для **–InternalURL** — это имя сервера, на котором запущен Сервер Office Web Apps (например, **http://Contoso-WAC**). В таком случае нужно использовать то же имя, которое использовалось для предыдущей фермы Сервер Office Web Apps. Используйте те же дополнительные параметры, которые использовались при первом создании фермы Сервер Office Web Apps. Например, параметр **–AllowHttp** настраивает ферму на использование HTTP, а параметр **–EditingEnabled** включает возможность редактирования в Office Web Apps при использовании последнего с SharePoint 2013. Параметр **–EditingEnabled** не используется Lync Server 2013 и Exchange Server 2013, поскольку эти хосты не поддерживают редактирование.
    
    Код в приведенном ниже примере создает новую ферму серверов Сервер Office Web Apps с именем http://Contoso-WAC.
    
    ```PowerShell
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    ```
    
    Дополнительные параметры, настраивающие службы транзакций, прокси-серверы, поддержку клипов и средства просмотра Online Viewer, описаны в статье [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

## Применение обновлений программного обеспечения к ферме Office Web Apps с несколькими серверами

Чтобы применить обновления программного обеспечения к ферме Сервер Office Web Apps с несколькими серверами, необходимо сначала удалить один из серверов из пула балансировки нагрузки и из фермы, применить обновление и создать новую ферму Сервер Office Web Apps. Затем из фермы Сервер Office Web Apps удаляются оставшиеся серверы, обновляются и добавляются к новой обновленной ферме. Нагрузка для новой фермы сбалансируется, когда новая ферма будет иметь достаточное количество серверов для поддержки текущего трафика. При использовании данного процесса обновления пользователи смогут открывать и редактировать документы в Office Web Apps без перерывов в работе.

**Чтобы применить обновления программного обеспечения к ферме из нескольких серверов**

1.  Загрузите обновление Сервер Office Web Apps, которое необходимо применить, из [Центра загрузки Майкрософт](http://go.microsoft.com/fwlink/p/?linkid=280274) в доступное для фермы Сервер Office Web Apps расположение в сети.

2.  Удалите сервер Сервер Office Web Apps, к которому вы хотите применить обновление программного обеспечения, из пула балансировки нагрузки.

3.  На этом сервере Сервер Office Web Apps откройте командную строку Windows PowerShell под учетной записью администратора и запустите следующую команду.
    
    ```PowerShell
        Remove-OfficeWebAppsMachine
    ```

4.  Установите обновление Сервер Office Web Apps на данный сервер. При необходимости выполните перезагрузку.

5.  Откройте командную строку Windows PowerShell под учетной записью администратора и создайте обновленную ферму Сервер Office Web Apps с помощью командлета **New-OfficeWebAppsFarm**. URL-адрес, определяемый для **–InternalURL** — это имя сервера, на котором запущен Сервер Office Web Apps (например,**http://Contoso-WAC**). В таком случае нужно использовать то же имя, которое использовалось для существующей фермы Сервер Office Web Apps. Используйте те же дополнительные параметры, которые использовались при первом создании фермы Сервер Office Web Apps. Например, параметр **–AllowHttp** настраивает ферму на использование HTTP, а параметр **–EditingEnabled** включает возможность редактирования в Office Web Apps при использовании последнего с SharePoint 2013. Параметр **–EditingEnabled** не используется Lync Server 2013 и Exchange Server 2013, поскольку эти хосты не поддерживают редактирование.
    
    Код в приведенном ниже примере создает новую ферму серверов Сервер Office Web Apps с именем http://Contoso-WAC.
    
    ```PowerShell
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    ```
    
    Дополнительные параметры, настраивающие службы транзакций, прокси-серверы, поддержку клипов и средства просмотра Online Viewer, описываются в статье [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

6.  Балансируйте нагрузку для новой фермы в зависимости от количества серверов в ферме Сервер Office Web Apps. Это действие можно отложить до того момента, когда у вас будет больше обновленных серверов для добавления к ферме.

7.  Выполните следующие действия для всех остальных серверов фермы.
    
    1.  Удалите следующий сервер Сервер Office Web Apps из пула балансировки нагрузки.
    
    2.  Установите на сервер обновление Сервер Office Web Apps. При необходимости выполните перезагрузку.
    
    3.  Откройте командную строку Windows PowerShell под учетной записью администратора и запустите следующую команду. Параметр **–MachineToJoin** добавляет текущий сервер к существующей ферме Сервер Office Web Apps. В этом случае вам необходимо добавить сервер к обновленной ферме Сервер Office Web Apps. Поэтому используйте имя компьютера одного из серверов в обновленной ферме Сервер Office Web Apps.
        
        ```PowerShell
            New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"
        ```

## См. также


[Remove-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)  
[Get-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappsfarm?view=officewebapps-ps)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
  

[](content-roadmap-for-office-web-apps-server.md)

