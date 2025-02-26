### Задание №1. Исследование заголовков и тела обычных запросов и их ответов.

- Request URL:`https://ya.ru/` - Это URL-адрес, на который был отправлен запрос. В данном случае, запрос направлен на https://ya.ru/.

- Request Method:`GET` - Это HTTP-метод, используемый для запроса. GET - это один из стандартных методов HTTP, используемый для запроса данных от сервера.

- Status Code:`200` - Этот код состояния HTTP указывает на результат выполнения запроса.
Код 200 означает успешное выполнение запроса, что означает, что сервер успешно вернул запрошенные данные.

- Remote Address:`5.255.255.242:443` - Это IP-адрес и порт сервера, с которым установлено соединение.
В данном случае, запрос был отправлен на IP-адрес 5.255.255.242 и порт 443, который обычно используется для защищенных HTTPS-соединений.

- Referrer Policy:`origin` - Это политика отправителя, которая определяет, какую информацию о реферере (странице, с которой был сделан запрос) отправлять на сервер.
Здесь установлена политика origin, что означает, что будет отправлена информация только об источнике запроса.

- Content-type:`text/html; charset=UTF-8` - Этот заголовок указывает на тип контента, который был возвращен сервером.
В данном случае, тип контента - text/html, что означает, что сервер вернул HTML-документ.
Кроме того, указана кодировка символов UTF-8, которая используется для текстового содержимого.

- Cache-control:`no-cache,no-store,max-age=0,must-revalidate` -  Этот заголовок определяет настройки кеширования для браузера.
Значение no-cache,no-store,max-age=0,must-revalidate говорит о том, что данные не должны кешироваться и должны быть перепроверены на сервере при каждом запросе.

- Cookie:`is_gdpr=0; is_gdpr_b=CLaqFBDWzwEoAg==; yandex_csyr=1695296578;...` - Этот заголовок содержит информацию о куки (cookie), которые отправляются серверу.
Куки - это маленькие фрагменты данных, которые сервер может хранить на компьютере клиента и использовать для отслеживания состояния сеанса и других данных.
В данном случае, перечислены различные куки и их значения.

- User-agent:`Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/117.0.0.0 Safari/537.36` - Этот заголовок содержит информацию о пользовательском агенте (браузере или программе), которая отправляет запрос.
В данном случае, пользовательский агент указывает, что это запрос был отправлен из браузера Chrome версии 117.0.0.0 на операционной системе Windows 10.

- Referer:`https://ya.ru/`Этот заголовок указывает на источник (ссылку или URL) с которого был сделан запрос.
В данном случае, запрос отправлен с реферера https://ya.ru/, что означает, что пользователь перешел на текущую страницу с этой ссылки.

### Задание №2. Исследование указывающих ответов сервера.
При переходе по адресу **http://rgups.ru/** и его изменении на **https://rgups.ru/** происходит автоматическое перенаправление с HTTP на HTTPS. Это сделано для обеспечения безопасности и конфиденциальности данных.

HTTP (HyperText Transfer Protocol) – это основной протокол передачи данных во Всемирной паутине. Однако HTTP не шифрует данные, которые передаются между вашим браузером и веб-сервером, что делает их уязвимыми для перехвата и изменения злоумышленниками.

В связи с этим был создан HTTPS (HyperText Transfer Protocol Secure), который является более безопасным вариантом HTTP. Он использует защищенное соединение, обеспечиваемое SSL/TLS (Secure Sockets Layer/Transport Layer Security), чтобы шифровать данные, передаваемые между браузером и веб-сервером.

Многие веб-сайты, включая rgups.ru, настроены таким образом, чтобы автоматически перенаправлять пользователей на защищенную HTTPS-версию сайта. Это может быть осуществлено с использованием различных методов, таких как 301-е перенаправление (постоянное) или правила HSTS (HTTP Strict Transport Security) в настройках веб-сервера.
Это делается для обеспечения безопасности пользователей и их данных при взаимодействии с сайтом.

### Задание №3. Исследование получения и передачи cookie.

1. Name: Это имя, которое выдается файлу cookie и используется для его идентификации на стороне сервера.

2. Value: Значение, связанное с именем cookie. Это информация, которая сохраняется на клиентской стороне и может быть доступна на сервере при каждом запросе с этой страницы.

3. Domain: Домен, к которому привязан файл cookie. Это определяет, на какие поддомены данного домена распространяется файл cookie.

4. Path: Указывает путь в URL-адресе, для которого применяется файл cookie. Это позволяет ограничить область действия cookie только для определенной части сайта.

5. Expires: Дата и время, когда файл cookie должен истечь и быть удаленным. После этой даты файл cookie перестает быть действительным.

6. Size: Размер файла cookie в байтах. Это поле указывает, сколько данных может храниться в данном файле cookie.

7. HttpOnly: Если установлено значение "true", то файл cookie недоступен для JavaScript на клиентской стороне. Это повышает безопасность, так как предотвращает доступ к файлам cookie через потенциально уязвимые скрипты.

8. Secure: Если установлено значение "true", то файл cookie будет отправляться только по защищенному HTTPS-соединению. Это обеспечивает шифрование передачи данных и повышает безопасность.

9. SameSite: Определяет, в каких случаях файл cookie будет отправляться вместе с запросами к серверу. Опции включают "Strict", "Lax", и "None". Настройка SameSite помогает предотвратить некоторые виды атак, связанных с файлами cookie, такие как CSRF.

10. Partition: Это заголовок, связанный с новой концепцией изоляции файлов cookie, позволяющей разделять файлы cookie между разными контекстами и сайтами, чтобы улучшить безопасность и конфиденциальность.

11. Priority: Позволяет устанавливать приоритет файлу cookie. Это может влиять на то, как браузер обрабатывает и отправляет файлы cookie, особенно в условиях ограниченных ресурсов, таких как более эффективная загрузка страниц.

Для просмотра cookie, связаных с текущим сайтом:

- Откройте веб-сайт, с которым связаны cookie.
- Нажмите правой кнопкой мыши на странице и выберите "Исследовать элемент" (Inspect Element).
- Перейдите на вкладку "Storage" в инструментах разработчика.
- В левой панели выберите "Cookies". Здесь отобразятся все cookie для текущего сайта.
  
Cookie (куки) - это небольшие текстовые файлы, которые веб-сайты отправляют и хранят на компьютере пользователя через веб-браузер.

### Задание №4. Исследование построения документов и сопутствующих запросов.

1. DOM, или Document Object Model (Модель объектов документа), представляет собой структуру программного интерфейса для представления и взаимодействия с документами HTML, XML и XHTML в веб-разработке.
DOM представляет документ в виде иерархии объектов, которая может быть легко изменена с помощью JavaScript или других скриптовых языков.

2. Итоговый документ может отличаться от тела ответа, полученного от сервера по нескольким причинам:
- Обработка на клиенте: Современные веб-приложения часто выполняют обработку данных на стороне клиента с использованием JavaScript. Это может включать в себя добавление, удаление или изменение содержимого на основе пользовательских действий или других условий.
- Серверные шаблоны: Некоторые серверы используют системы шаблонов для генерации содержимого на основе данных из базы данных или других источников. Это может привести к тому, что реальное содержимое, отображаемое в браузере, отличается от первоначального ответа сервера.
- Прокси-серверы и CDN: Промежуточные серверы, такие как прокси-серверы или сети доставки контента (CDN), могут изменять содержимое, прежде чем оно достигает конечного пользователя. Это может быть связано с оптимизацией, сжатием или другими преобразованиями.
- Браузерные расширения: Расширения, установленные в браузере пользователя, могут вносить изменения в содержимое страницы.
- Кеширование: Иногда старая версия страницы может кешироваться на уровне браузера или на уровне прокси-сервера, что может привести к тому, что пользователь видит устаревшую версию страницы.
- Серверная логика: В зависимости от условий (например, тип устройства, агент пользователя, геолокация и т. д.), сервер может предоставлять различные версии содержимого.

3. Большое количество запросов и ответов в списке, то это может быть связано с тем, что современные веб-страницы часто содержат множество ресурсов, таких как изображения, стили, скрипты, шрифты и другие элементы.
Каждый из этих ресурсов запрашивается и загружается отдельно.

### Задание №5. Определение параметров запроса.

1. Необходимо выполнить запрос к **shedule.php**
2. В ответе мы получаем часть HTML-кода, тип которого указан во вкладке Header Content-Type: text/html; charset=UTF-8
3. Выполнил POST-запрос
4.  Данные, которые использовал для получения
    - action: timetable
    - fac-id: 1
    - course-id: 3
    - group-id: 26463
    - edu-type: internal
