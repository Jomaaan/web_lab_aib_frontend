### 1. РГУПС

Скрипт: 

`curl rgups.ru -I -v -L -k`


`-I` - Этот ключ отправляет HTTP HEAD-запрос на указанный URL и выводит только заголовки ответа без тела.
Это полезно, если вам нужно получить информацию о ресурсе, не загружая его полностью.

`-v` - Этот ключ включает подробный вывод (verbose).
Он отображает информацию о каждом этапе выполнения запроса, включая отправку и получение данных, а также заголовки запроса и ответа.

`-L` - Этот ключ заставляет curl следовать перенаправлениям (переходам по URL) автоматически.
Если ресурс перенаправляет на другой URL, curl будет следовать за ним до достижения конечной цели.

`-k` - Этот ключ отключает проверку SSL-сертификата.
Он полезен, если вы хотите выполнить запрос на сервер с самоподписанным сертификатом или без него.

Что получил при использовании скрипта:

```shell
> HEAD / HTTP/1.1 - Это начало HTTP-запроса с использованием метода HEAD и версии протокола HTTP/1.1.
> Метод HEAD используется для запроса только заголовков ресурса без его фактического содержимого.
> Host: rgups.ru - Этот заголовок указывает хост (сервер), к которому будет отправлен HTTP-запрос.
> User-Agent: curl/7.79.1 - Этот заголовок представляет информацию о пользовательском агенте (браузере или программе, совершающей запрос).
> Accept: */* - Строка указывающая на тип принимаемого контента 
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK - Это строка состояния ответа HTTP, которая указывает на успешное выполнение запроса.
Код состояния 200 OK означает, что сервер успешно обработал запрос и возвращает запрошенный ресурс.
< Server: nginx/1.19.1 - Строка указывает на серверное ПО и его версию
< Date: Wed, 13 Sep 2023 18:11:51 GMT - Строка содержить дату и время когда был получен ответ от сервера
< Content-Type: text/html; charset=utf-8 - Этот заголовок Content-Type указывает на тип контента, который содержится в ответе сервера.
 В данном случае, тип контента - text/html, что означает, что ответ представляет собой HTML-документ.
 Также указывается кодировка символов charset=utf-8, что говорит о том, что текст внутри HTML-документа кодируется с использованием UTF-8.
< Connection: keep-alive -Этот заголовок указывает на настройку соединения между клиентом (вашим скриптом curl) и сервером.
 Значение keep-alive означает, что соединение должно оставаться открытым после завершения запроса и ответа.
< X-Powered-By: ProcessWire CMS - Этот заголовок обычно указывает на программное обеспечение, которое запускает сервер и обрабатывает запросы.
 В данном случае, сервер использует систему управления контентом (CMS) под названием "ProcessWire CMS" для обработки запросов и создания контента.
< Set-Cookie: wire=86eadf3cc378a58f2dff124ae9cf6aef; path=/; HttpOnly; SameSite=Lax - Строка указывает на установку куки (cookie) на стороне клиента. 
Куки представляют собой данные, которые сервер отправляет браузеру, 
и они могут использоваться для отслеживания состояния сессии или других информационных целей.
< Expires: Thu, 19 Nov 1981 08:52:00 GMT - Строка указывает на дату и время истечения срока действия ответа.
Дата указана в прошлом, так как ответ не должен кэшироваться
< Cache-Control: no-store, no-cache, must-revalidate - Строка определяет инструкции для кэширования ответа.
В нашем случае указано, что ответ не должен сохраняться в кэше и должен быть проверен перед использованием
< Pragma: no-cache - Строка указывает, что ответ не должен кэшироваться и должен быть всегда запрашиваемым с сервера.
```
### 2.GitHub

Скрипт: `curl github.com -I -v -L -k`

Что получил при использовании скрипта:

```shell
> HEAD / HTTP/1.1
> Host: github.com
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Server: GitHub.com
< Date: Wed, 13 Sep 2023 18:15:21 GMT
< Content-Type: text/html; charset=utf-8
< Vary: X-PJAX, X-PJAX-Container, Turbo-Visit, Turbo-Frame, Accept-Language, Accept-Encoding, Accept, X-Requested-With -  Этот заголовок указывает на факторы, 
которые могут влиять на кэширование ответа на стороне клиента или прокси-сервера. 
< content-language: en-US - Этот заголовок указывает на язык контента, который отправляется в ответе.
< ETag: W/"aa79b40beb07f510ff7a2bb5f2081380" - Этот заголовок представляет собой метку, которая идентифицирует уникальную версию ресурса. 
Он используется для управления кэшированием на стороне клиента. 
Если ресурс изменяется, ETag изменяется, и клиент может использовать его для определения, нужно ли ему получить обновленную версию ресурса.
< Cache-Control: max-age=0, private, must-revalidate
< Strict-Transport-Security: max-age=31536000; includeSubdomains; preload -  Этот заголовок относится к безопасности. 
Он указывает, что клиент должен поддерживать строгую защиту транспортного уровня (HTTPS) в течение 31536000 секунд и включать поддомены 
< X-Frame-Options: deny - Это мера безопасности, которая может помочь предотвратить атаки.
< X-Content-Type-Options: nosniff - Этот заголовок предотвращает браузер от интерпретации содержимого как чего-то, отличного от указанного в Content-Type.
< X-XSS-Protection: 0 - Этот заголовок указывает на то, что браузер не должен активировать механизм защиты от межсайтового скриптового выполнения (XSS)
< Referrer-Policy: origin-when-cross-origin, strict-origin-when-cross-origin - Этот заголовок управляет тем, какой информацией о предыдущей странице делится браузер при переходе по ссылке.
< Set-Cookie: logged_in=no; Path=/; Domain=github.com; Expires=Wed, Wed, 13 Sep 2024 18:12:11 GMT; HttpOnly; Secure; SameSite=Lax 
< Accept-Ranges: bytes - Этот заголовок указывает, что сервер поддерживает диапазоны запросов для данного ресурса.
< X-GitHub-Request-Id: 1FF9:0FCE:73B2E39:752A979:6501FEBA - Этот заголовок содержит идентификатор запроса, который может быть полезен для отслеживания запроса на стороне сервера.
```

### 3.РЖД


Скрипт: `curl rzd.ru -I -v -L -k --User-agent "Yandex"`

`--User-agent "Yandex"` - Это строка, которую клиент отправляет на сервер, чтобы указать серверу, какое программное обеспечение или устройство отправляет запрос.

Что получил при использовании скрипта:
```shell
> HEAD / HTTP/1.1
> Host: www.rzd.ru
> User-Agent: Yandex
> Accept: */*
>
< HTTP/1.1 200
< Content-Type: text/html;charset=utf-8
< Content-Length: 210102 -  Этот заголовок указывает на длину (размер) содержимого ответа в байтах (210102 байта).
< Connection: keep-alive
< Date: Wed, 13 Sep 2023 18:17:26 GMT
< Vary: Accept-Encoding
< X-UCM-Pod-Name: inex-ucm-776d97f9d-4mqxf - Этот заголовок связан с идентификацией серверного подключения.
< Strict-Transport-Security: max-age=15724800; includeSubDomains
< Via: nginx3 - Этот заголовок указывает на прокси-сервер, через который прошел запрос.
< X-Frame-Options: sameorigin
< Set-Cookie: session-cookie=178488dc2a7afb8a57059bb218991a2449697cbcda9b4aa8e0035f3247d9181bd936287c32178f4b5c11da4a7af8fee8; Max-Age=86400; Path=/; secure; HttpOnly
< X-XSS-Protection: 1; mode=block - Этот заголовок говорит браузеру о включенной защите от XSS и указывает ему блокировать скрипты, 
которые могут представлять угрозу безопасности.
```
### 4.Yandex

Скрипт: `curl yandex.ru -I -v -L -k`

Что получил при использовании скрипта:
```shell
> HEAD /?yredirect=true HTTP/1.1 - Этот запрос будет направлен на сервер с указанием пути / и параметра запроса yredirect=true, и сервер должен ответить только заголовками ресурса, без передачи фактического содержимого.
> Host: dzen.ru
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 Ok
< Cache-Control: no-cache, no-store, max-age=0, must-revalidate
< Content-Type: text/html; charset=utf-8
< Set-Cookie: _yasc=8/sCs3O4rPc72AJNFSP2hDrYplLqhDCZHNQNWrlFA3mN0G6z5hjpF4Ntd0okqUxo7lhI; domain=.yandex.ru; path=/; expires=Sat, 10 Sep 2033 18:32:59 GMT; secure
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< X-Requestid: 0 -  Этот заголовок содержит идентификатор запроса, который может быть полезен для отслеживания запроса на стороне сервера.
< X-Yandex-Req-Id: 1694629979836893-14605358076662102213-balancer-l7leveler-kubr-yp-sas-57-BAL - Заголовок представляет собой уникальный идентификатор запроса, который полезен для отслеживания запроса на стороне сервера Yandex или системы, которая обрабатывает запросы.
```

### 5.Python

Скрипт: `curl python.org -I -v -L -k`

Что получил при использовании скрипта:
```shell
> HEAD / HTTP/1.1
> Host: www.python.org
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Connection: keep-alive
< Content-Length: 50434
< Server: nginx
< Content-Type: text/html; charset=utf-8
< X-Frame-Options: SAMEORIGIN
< Via: 1.1 vegur, 1.1 varnish, 1.1 varnish
< Accept-Ranges: bytes
< Date: Wed, 13 Sep 2023 18:21:11 GMT
< Age: 2224 - Этот заголовок указывает на время в секундах, прошедшее с момента кэширования ответа на сервере или прокси.
< X-Served-By: cache-iad-kiad7000025-IAD, cache-bma1622-BMA - Этот заголовок указывает на серверы и прокси, которые обслуживали запрос.
< X-Cache: HIT, HIT - Этот заголовок указывает, что ответ был получен из кэша как минимум дважды.
< X-Cache-Hits: 2, 7 - Этот заголовок указывает на количество "попаданий" в кэш для данного запроса
< X-Timer: S1694630185.827884,VS0,VE0 - Этот заголовок содержит информацию о времени, затраченном на обработку запроса на сервере.
< Vary: Cookie
< Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```
### 6.Git

Скрипт: `curl git-scm.com -I -v -L -k`

Что получил при использовании скрипта:
```shell
> HEAD / HTTP/1.1
> Host: git-scm.com
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Date: Wed, 13 Sep 2023 18:22:36 GMT
< Content-Type: text/html; charset=utf-8
< Connection: keep-alive
< X-Frame-Options: SAMEORIGIN
< X-Xss-Protection: 1; mode=block
< X-Content-Type-Options: nosniff
< X-Download-Options: noopen - Этот заголовок указывает, что файлы не должны открываться автоматически после загрузки.
< X-Permitted-Cross-Domain-Policies: none - Этот заголовок указывает, что политики, связанные с кросс-доменными запросами, отсутствуют.
< Referrer-Policy: strict-origin-when-cross-origin
< Cache-Control: public, max-age=14400
< Etag: W/"db69273d9410cbf4536e9d4b3a59685d"
< X-Request-Id:  476d2e08-474c-4f3d-8503-d83ed21ae45f
< X-Runtime: 0.015343 - Этот заголовок указывает на время, затраченное на выполнение запроса на стороне сервера
< Via: 1.1 vegur
< CF-Cache-Status: HIT
< Age: 5300
< Server: cloudflare
< CF-RAY:  806281ce2e407903-DME - Этот заголовок может содержать информацию о запросе и обработке на стороне Cloudflare.
```
### 7.JetBrains

Скрипт: `curl jetbrains.com -I -v -L -k`

Что получил при использовании скрипта:
```shell
> HEAD / HTTP/1.1
> Host: www.jetbrains.com
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Content-Type: text/html; charset=utf-8
< Content-Length: 47113
< Connection: keep-alive
< Date: Wed, 13 Sep 2023 18:40:56 GMT
< Server: nginx
< X-Content-Type-Options: nosniff
< Referrer-Policy: same-origin
< Expires: Wed, 13 Sep 2023 18:40:56 GMT - Этот заголовок указывает на дату и время истечения срока действия ответа в кэше.
< Cache-Control: max-age=0
< Pragma: no-cache
< X-Frame-Options: DENY
< X-Content-Type-Options: nosniff
< X-Xss-Protection: 1; mode=block
< Strict-Transport-Security: max-age=31536000;
< Vary: Accept-Encoding
< Via: 1.1 8f473fbf4c5fc98461ca6905ec13126c.cloudfront.net (CloudFront)
< Age: 94
< Set-Cookie: cf_country-region=RU-MOW; Domain=jetbrains.com; Path=/; Secure
< X-Cache: Hit from cloudfront
< X-Amz-Cf-Pop: HEL50-C1 - Этот заголовок содержит информацию о Point of Presence CloudFront, через который прошел запрос.
< X-Amz-Cf-Id:  yMUP6Cni25SE0oXFN9KHfWCuGcSLCW7w9OxlpYavoxUXc_EAJqMq7g== - Этот заголовок может содержать идентификатор запроса и обработки на стороне CloudFront.
```

### 8. VSC

Скрипт: `curl code.visualstudio.com -I -v -L -k`

Что получил при использовании скрипта:
```shell
> HEAD / HTTP/1.1
> Host: code.visualstudio.com
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Content-Length: 50213
< Content-Type: text/html; charset=utf-8
< Accept-Ranges: bytes
< ETag: W/"c425-XBxswsHoV0dlJCAKuBbwZ9s5rjQ"
< Strict-Transport-Security: max-age=31536000; includeSubDomains
< Content-Security-Policy: frame-ancestors 'self' -  Этот заголовок определяет политику безопасности контента и разрешает встраивание ресурсов только с текущего домена.
< X-Frame-Options: SAMEORIGIN
< X-XSS-Protection: 1; mode=block
< X-Content-Type-Options: nosniff
< X-Powered-By: ASP.NET
< x-azure-ref:  20230913T184516Z-kw4yxb8g813019e8zb33y6tmd800000000hg00000000bs2b
< X-Cache: CONFIG_NOCACHE
< Date:  Wed, 13 Sep 2023 18:45:16 GMT
```
