---
title: Настройка Office Web Apps для SharePoint 2013
TOCTitle: Настройка Office Web Apps для SharePoint 2013
ms:assetid: a5276781-133b-413c-beca-b851e17c2081
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Ff431687(v=office.15)
ms:contentKeyID: 49624496
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Настройка Office Web Apps для SharePoint 2013

_<strong>Применимо к:</strong> Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_<strong>Последнее изменение раздела:</strong> 2016-12-16_

**Сводка.** Руководство по настройке SharePoint 2013 для использования Office Web Apps.

**Аудитория:** ИТ-специалисты

Эта статья — продолжение статьи [Развертывание сервера Office Web Apps](deploy-office-web-apps-server.md), где описывалась настройка сервера, на котором работает Сервер Office Web Apps. В этой статье описано, как настроить SharePoint 2013 для использования Сервер Office Web Apps. Сначала вам потребуется выполнить несколько командлетов Windows PowerShell в SharePoint 2013. После этого пользователи смогут открывать файлы Office из библиотек документов SharePoint 2013 в браузере.

Если вы не знакомы с возможностями Сервер Office Web Apps, [прочитайте их обзор](office-web-apps-server-overview.md).

Содержание:

  - Подготовка к настройке SharePoint 2013 для использования сервера Office Web Apps

  - Настройка SharePoint 2013 для использования сервера Office Web Apps

  - Устранение неполадок в Office Web Apps при использовании с SharePoint 2013

  - Отключение SharePoint 2013 от сервера Office Web Apps

## Подготовка к настройке SharePoint 2013 для использования сервера Office Web Apps

Перед началом работы нужно кое-что проверить.

  - Установите SharePoint 2013. Инструкции см. в статье [Установка SharePoint 2013](https://technet.microsoft.com/ru-ru/library/cc303424\(v=office.15\)).

  - Убедитесь, что все веб-приложения SharePoint 2013 используют проверку подлинности на основе утверждений. Визуализация и редактирование Office Web Apps не будут работать для веб-приложений SharePoint 2013, использующих классический режим проверки подлинности. Подробнее см. в статье [Требования к проверке подлинности SharePoint для Office Web Apps](plan-office-web-apps-used-with-sharepoint-2013.md).

  - Чтобы пользователи могли редактировать (а не только читать) документы Office в браузере, вам потребуется лицензия на редактирование. Кроме того, необходимо разрешить редактирование в ферме серверов Сервер Office Web Apps. Подробнее о требованиях лицензирования см. в статье [Лицензирование Office Web Apps для редактирования файлов Office](plan-office-web-apps-used-with-sharepoint-2013.md).

  - При входе в SharePoint 2013 с использованием системной учетной записи вы не сможете тестировать подключение между SharePoint 2013 и сервером Сервер Office Web Apps. Войдите с другой учетной записью, чтобы проверить подключение.

  - В условиях недостатка памяти могут происходить сбои при просмотре документов Office в Office Web Apps. Изучите [требования к оборудованию — веб-серверы, серверы приложений и конфигурации с одним сервером](https://technet.microsoft.com/ru-ru/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver) для SharePoint 2013. Они совпадают с требованиями для сервера Сервер Office Web Apps.

## Настройка SharePoint 2013 для использования сервера Office Web Apps

Выберите один из следующих разделов в зависимости от того, будете ли вы использовать протокол HTTP или HTTPS. HTTP рекомендуется, в основном, для тестовых сред. В рабочих средах лучше выбрать более безопасный протокол HTTPS.

## Тестовая среда с использованием HTTP

В этой конфигурации установите сервер Сервер Office Web Apps, выполнив действия, описанные в статье [Развертывание фермы серверов Office Web Apps, состоящей из отдельного сервера, в тестовой среде](deploy-office-web-apps-server.md). Настройте ферму Сервер Office Web Apps для использования внутреннего URL-адреса и HTTP. В [Видео. Настройка Office Web Apps для SharePoint 2013](video-configure-office-web-apps-for-sharepoint-2013.md) показано, как установить Сервер Office Web Apps и настроить SharePoint 2013 для использования Сервер Office Web Apps в тестовой среде.

## Шаг 1. Открытие командной консоли SharePoint 2013 с повышенными привилегиями

Выберите процедуру, соответствующую операционной системе вашего сервера.

**В Windows Server 2008 R2**

1.  Нажмите кнопку **Пуск** и последовательно выберите **Все программы**, **Продукты Microsoft SharePoint 2013**.

2.  Щелкните правой кнопкой мыши пункт **Командная консоль SharePoint 2013** и выберите пункт **Запуск от имени администратора**.

**В Windows Server 2012**

1.  Нажмите клавиши WINDOWS+Q или проведите пальцем в центр от края экрана, чтобы отобразить экспресс-кнопки, и щелкните **Поиск**, чтобы просмотреть все установленные на компьютере приложения.

2.  Щелкните правой кнопкой мыши пункт **Командная консоль SharePoint 2013**, чтобы открыть панель приложения.

3.  В панели приложения выберите **Запуск от имени администратора**.

## Шаг 2. Создание привязки между SharePoint 2013 и Office Web Apps Server

Выполните следующую команду, в которой \<WacServerName\> представляет полное доменное имя URL-адреса, установленного для внутренних URL-адресов. Это точка входа для трафика сервера Сервер Office Web Apps. Для данной тестовой среды необходимо указать параметр –AllowHTTP, чтобы разрешить SharePoint 2013 получать сведения обнаружения из фермы серверов Сервер Office Web Apps посредством протокола HTTP. Если вы не укажете –AllowHTTP, то SharePoint 2013 будет пытаться использовать для взаимодействия с фермой серверов Сервер Office Web Apps протокол HTTPS, и эта команда завершится неудачно.

```PowerShell
    New-SPWOPIBinding -ServerName <WacServerName> -AllowHTTP
```

После выполнения этой команды вы должны увидеть список привязок, отображенный в командной строке Windows PowerShell.

Требуется помощь? См. описание командлета [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps).

## Шаг 3. Просмотр зон WOPI для привязок SharePoint

Сервер Сервер Office Web Apps использует зоны для определения, какой URL-адрес (внутренний или внешний) и какой протокол (HTTP или HTTPS) использовать при взаимодействии с узлом, в данном случае с SharePoint 2013. По умолчанию SharePoint Server 2013 использует зону **internal-https**. Выполните следующую команду, чтобы узнать текущую зону.

```PowerShell
    Get-SPWOPIZone
```

Эта команда должна показать зону WOPI **internal-http**. Если она отображается правильно, перейдите к шагу 5. В противном случае перейдите к следующему шагу.

Требуется помощь? См. описание командлета [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Шаг 4. Изменение зоны WOPI на зону "internal-http"

Если в результате шага 3 была получена зона **internal-https**, выполните следующую команду, чтобы изменить ее на **internal-http**. Это изменение необходимо потому, что зона SharePoint 2013 должна соответствовать зоне фермы серверов Сервер Office Web Apps.

```PowerShell
    Set-SPWOPIZone -zone "internal-http"
```

Убедитесь, что новая зона является зоной **internal-http**, выполнив **Get-SPWOPIZone** еще раз.

Требуется помощь? См. описание командлетов [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps) и [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Шаг 5. Изменение значения параметра AllowOAuthOverHttp в SharePoint 2013 на True

Чтобы использовать Office Web Apps в SharePoint 2013 посредством протокола HTTP в тестовой среде, необходимо установить для параметра AllowOAuthOverHttp значение **True**. В противном случае Office Web Apps не будет работать. Текущее состояние можно проверить, выполнив следующую команду:

```PowerShell
    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp
```

Если эта команда возвращает значение **False**, установите значение **True**, выполнив следующую команду.

```PowerShell
    $config = (Get-SPSecurityTokenServiceConfig)

    $config.AllowOAuthOverHttp = $true

    $config.Update()
```

Снова выполните следующую команду, чтобы убедиться, что параметр AllowOAuthOverHttp теперь имеет значение **True**.

```PowerShell
    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp
```

Требуется помощь? См. описание командлета [Get-SPSecurityTokenServiceConfig](https://technet.microsoft.com/ru-ru/library/ff607642\(v=office.15\)).

## Шаг 6. Проверка работы Office Web Apps

В SharePoint 2013 убедитесь, что вы не вошли с использованием системной учетной записи, так как вы не сможете редактировать или просматривать документы в Office Web Apps. Перейдите в библиотеку документов SharePoint 2013, содержащую документы Office, и откройте файл Word, PowerPoint, Excel или OneNote. Документ должен открыться в браузере, где этот файл должен отображаться с помощью Office Web Apps.

Если этот шаг выполнить не удается, см. раздел Диагностика и устранение ошибок в Office Web Apps.

## Рабочая среда, которая использует протокол HTTPS

Прежде чем приступить к следующим процедурам, убедитесь, что сервер Сервер Office Web Apps установлен, выполнив действия из статьи [Развертывание фермы серверов Office Web Apps, состоящей из отдельного сервера и поддерживающей HTTPS](deploy-office-web-apps-server.md#singlehttps) или [Развертывание многосерверной фермы серверов Office Web Apps с балансировкой нагрузки, поддерживающей протокол HTTP](deploy-office-web-apps-server.md#multihttps)

## Шаг 1. Открытие командной консоли SharePoint 2013

Выберите процедуру, соответствующую операционной системе вашего сервера.

**В Windows Server 2008 R2**

1.  Нажмите кнопку **Пуск** и последовательно выберите **Все программы**, **Продукты Microsoft SharePoint 2013**.

2.  Щелкните правой кнопкой мыши **Командная консоль SharePoint 2013**, чтобы открыть контекстное меню, и выберите пункт **Запуск от имени администратора**.

**В Windows Server 2012**

1.  Нажмите клавишу Windows+Q или проведите пальцем в центр от края экрана, чтобы отобразить экспресс-кнопки, и щелкните **Поиск**, чтобы просмотреть все установленные на компьютере приложения.

2.  Щелкните правой кнопкой мыши **командную консоль SharePoint 2013**, чтобы открыть панель приложения.

3.  В панели приложения выберите **Запуск от имени администратора**.

## Шаг 2. Создание привязки между SharePoint 2013 и Office Web Apps Server

Выполните следующую команду, в которой \<WacServerName\> представляет полное доменное имя URL-адреса, установленного для внутренних URL-адресов. Это точка входа для трафика сервера Сервер Office Web Apps.

```PowerShell
    New-SPWOPIBinding -ServerName <WacServerName> 
```

Требуется помощь? См. описание командлета [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps).

## Шаг 3. Просмотр зоны WOPI SharePoint 2013

Сервер Сервер Office Web Apps использует зоны для определения, какой URL-адрес (внутренний или внешний) и какой протокол (HTTP или HTTPS) использовать при взаимодействии с узлом, в данном случае с SharePoint 2013. По умолчанию SharePoint Server 2013 использует зону **internal-https**. Убедитесь, что это текущая зона, выполнив следующую команду:

```PowerShell
    Get-SPWOPIZone
```

Отметьте, какая зона WOPI отображается.

Требуется помощь? См. описание командлета [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Шаг 4. Изменение зоны WOPI при необходимости

В зависимости от вашей среды может потребоваться изменить зону WOPI. При использовании фермы SharePoint, которая одновременно является внешней и внутренней, укажите внешнюю ферму. Если используемая ферма SharePoint является только внутренней, укажите внутреннюю зону.

Если в результате шага 3 отображается зона **internal-https**, а ферма SharePoint только внутренняя, можно пропустить этот шаг. Если ферма SharePoint одновременно является внутренней и внешней, необходимо выполнить следующую команду, чтобы изменить зону на **external-https**.

```PowerShell
    Set-SPWOPIZone -zone "external-https"
```

Требуется помощь? См. описание командлета [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps).

## Шаг 5. Проверка работы Office Web Apps

В SharePoint 2013 убедитесь, что вы не вошли с использованием системной учетной записи, так как вы не сможете редактировать или просматривать документы в Office Web Apps. Перейдите в библиотеку документов SharePoint 2013, содержащую документы Office, и откройте файл Word, PowerPoint, Excel или OneNote. Документ должен открыться в браузере, где этот файл должен отображаться с помощью Office Web Apps.

Если этот шаг выполнить не удается, см. раздел Диагностика и устранение ошибок в Office Web Apps.

## Устранение неполадок в Office Web Apps при использовании с SharePoint 2013

Если Office Web Apps не работает правильно при использовании вместе с SharePoint 2013, найдите симптом ниже и развернуть заголовок, чтобы открыть действия по устранению неполадок.

## Проблема: при нажатии ссылки "создать документ" в библиотеке SharePoint предлагается возможность отправки документа вместо возможности создания нового документа Office. При выборе (однократном щелчке) документа Office файл открывается в клиентском приложении. Предварительные просмотры документов Office не отображаются.

Далее приводятся некоторые варианты устранения ошибки.

**Определите, применяется ли проверка подлинности на основе утверждений в веб-приложении SharePoint, которое используется для создания нового документа.**

Открывать файлы в Office Web Apps могут только веб-приложения, применяющие проверку подлинности на основе утверждений. Чтобы определить поставщика проверки подлинности для веб-приложения, выполните следующие действия.

1.  В Центр администрирования SharePoint 2013 щелкните **Управление веб-приложениями**.

2.  Выберите веб-приложение, которое нужно проверить, а затем нажмите на ленте кнопку **Поставщики проверки подлинности**.

Для правильной работы Office Web Apps с веб-приложением поставщик проверки подлинности должен отображаться как **Проверка подлинности на основе утверждений**. Чтобы разрешить эту проблему, можно либо удалить веб-приложение и создать его с использованием проверки подлинности на основе утверждений, либо изменить способ проверки подлинности для этого приложения. Подробнее см. в статье [Требования к проверке подлинности SharePoint для Office Web Apps](plan-office-web-apps-used-with-sharepoint-2013.md).

**Проверьте соответствие зон WOPI в SharePoint 2013 и фермы серверов Office Web Apps.**

Для этого выполните в SharePoint Server следующую команду:

```PowerShell
    Get-SPWopiZone 
```

Вы получите одно из следующих значений:

  - internal-https

  - internal-http

  - external-https

  - external-http

Теперь выполните в SharePoint Server следующую команду:

```PowerShell
    Get-SPWOPIBinding
```

В полученном результате найдите строку **WopiZone: зона**. Если результат, полученный из командлета Get-SPWopiZone, не соответствует зоне, которую возвратил командлет Get-SPWOPIBinding, выполните в SharePoint Server командлет **Set-SPWOPIZone -Zone**, чтобы изменить зону WOPI для соответствия результату, полученному из командлета Get-SPWOPIBinding. Справку по использованию этих командлетов см. в описаниях [Get-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIBinding?view=sharepoint-ps), [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps) и [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Проблема: при попытке редактирования документа Office в Office Web Apps появляется сообщение об ошибке "Документ не может быть открыт для редактирования".

Иногда пользователи-участники группы безопасности Active Directory не могут редактировать документы в браузере. Для решения этой проблемы нужно правильно настроить приложение службы профилей пользователей и полностью синхронизировать его с членством пользователей и членством в группах. Дополнительные сведения см. в [этой статье базы знаний](https://support.microsoft.com/kb/2908321).

## Проблема: при попытке просмотра документа Office в Office Web Apps появляется сообщение "Произошла ошибка".

Убедитесь, что вы не вошли с использованием системной учетной записи, так как вы не сможете редактировать или просматривать документы. Войдите как другой пользователь и повторите попытку доступа к Office Web Apps.

## Проблема: при попытке просмотра документа Office в Office Web Apps появляется сообщение "Произошла ошибка. Не удается открыть документ".

Если вы настраиваете Office Web Apps в тестовой среде, использующей протокол HTTP, проверьте, установлен ли параметр AllowOAuthOverHttp в значение **True**, как описывается в разделеШаг 5. Измените значение параметра AllowOAuthOverHttp в SharePoint 2013 на True.

Если вы когда-либо добавляли домены в список разрешений с помощью командлета [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps), убедитесь, что доступ к Office Web Apps осуществляется с несущего домена, который находится в списке разрешений. Чтобы просмотреть несущие домены в списке разрешений, откройте на сервере Сервер Office Web Apps командную строку Windows PowerShell от имени администратора и запустите командлет [Get-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappshost?view=officewebapps-ps). Чтобы добавить домен в список разрешений, используйте командлет [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps).

## Проблема: при попытке просмотреть документ Office в Office Web Apps отображается сообщение об ошибке "Приложению Word Web App не удается открыть этот документ, так как служба занята. Повторите попытку позже".

  - Установлен ли на контроллере домена сервер Сервер Office Web Apps? К сожалению, Сервер Office Web Apps не может быть запущен на контроллере домена. Сервер Office Web Apps должен быть установлен на отдельном сервере, входящем в состав домена. Подробнее см. в статье [Требования к конфигурации, программному и аппаратному обеспечению для сервера Office Web Apps](plan-office-web-apps-server.md).

  - Убедитесь, что на вашем компьютере используется SharePoint 2013 с версией сборки 15.0.4420.1017 (или более поздней). Чтобы проверить номер сборки, выполните на сервере SharePoint 2013 следующее.
    
    1.  В меню **Пуск** последовательно выберите **Все программы**, **Продукты Microsoft SharePoint 2013**, **Центр администрирования SharePoint 2013**.
    
    2.  Выберите элемент **Параметры системы**, а затем — **Управление серверами в этой ферме**.
    
    Проверьте **версию базы данных конфигурации**. Она должна иметь значение **15.0.4420.1017** или выше. Чтобы получить дополнительную информацию, перейдите в [Центр обновлений для Office, серверов Office и связанных продуктов](https://go.microsoft.com/fwlink/p/?linkid=160585).

## Проблема: при попытке просмотреть документ Office в Office Web Apps с помощью созданного пользователем URL-адреса отображается сообщение об ошибке "Файл не найден. URL-адрес исходного файла недействителен или документ не является общедоступным. Проверьте, правильно ли указан URL-адрес, а затем свяжитесь с владельцем документа".

Пытаетесь ли вы открыть с пользовательского URL-адреса документ, размер файла которого превышает 10 МБ? Убедитесь, что размер документа не превышает 10 мегабайт.

## Проблема: предварительный просмотр документов Office не отображается в SharePoint 2013. Вместо него появляется ошибка "Не удается отобразить это содержимое во фрейме".

В условиях недостатка памяти могут возникать проблемы с предварительным просмотром документов Office. Требования к памяти для SharePoint 2013, совпадающие с требованиями, используемыми сервером Сервер Office Web Apps, см. в статье [Требования к оборудованию — веб-серверы, серверы приложений и конфигурации с одним сервером](https://technet.microsoft.com/ru-ru/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver).

## Проблема: отображается сообщение об ошибке "Подключение к данным настроено таким образом, чтобы всегда использовать файл подключения, а {0:ExcelWebApp} не поддерживает файлы внешнего подключения. Не удалось обновить следующие подключения: Подключения к данным".

Причиной является то, что Сервер Office Web Apps не поддерживает файл подключения к данным Office (ODC-файл), в котором хранятся сведения о подключении. Чтобы решить данную проблему, выполните следующие действия.

1.  Откройте книгу в клиентском приложении Excel.

2.  Щелкните **Данные** \> **Подключения**.

3.  Выберите подключения к данным из списка в сообщении, а затем нажмите **Свойства**.

4.  Выберите вкладку **Определение**.

5.  Снимите флажок **Всегда использовать флажок файла подключений для**.

6.  Заново загрузите книгу в библиотеку документов SharePoint.

Чтобы включить возможность взаимодействия пользователей с книгами, содержащими модель данных или представления Power View, в окне обозревателя, настройте службы Excel в SharePoint Server для отображения книг. Для этого администратор SharePoint должен запустить командлет New-SPWOPISupressionSetting на сервере, на котором установлен SharePoint Server. Подробнее см. в статьях [New-SPWOPISuppressionSetting](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPISuppressionSetting?view=sharepoint-ps) и [Администрирование служб Excel в SharePoint Server 2013](https://technet.microsoft.com/ru-ru/library/ee681487\(v=office.15\)).

## Отключение SharePoint 2013 от сервера Office Web Apps

Если по каким-либо причинам требуется отключить SharePoint 2013 от сервера Сервер Office Web Apps, используйте следующую команду.

```PowerShell
    Remove-SPWOPIBinding -All:$true
```

Требуется помощь? См. описание командлета [Remove-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Remove-SPWOPIBinding?view=sharepoint-ps).

## См. также


[New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps)  
[Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps)  


[План содержимого для сервера Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Развертывание сервера Office Web Apps](deploy-office-web-apps-server.md)  
  

[](deploy-office-web-apps-server.md)