# TotalCMS demo Stored XSS

## Author: (Sergio)

**Description:** Cross Site Scripting vulnerability in TotalCMS demo allows a local attacker to execute arbitrary code via a crafted script to the admin Post settings.

**Attack Vectors:** Scripting A vulnerability in the sanitization of the entry in the admin Post settings. allows injecting JavaScript code that will be executed when the user accesses the web page.

---

### POC:


When logging into the panel, we will go to the "/admin/post- Settings" section off General Menu.

![image](https://github.com/sromanhu/TotalCMS-Stored-XSS---Post/assets/87250597/729e7e4a-1ebe-4174-9719-e5615f028c55)




We edit that Post Settings and see that we can inject arbitrary Javascript code in the permalink menu.


### XSS Payload:

```js
<img src=1 onerror=alert("XSS_TotalCMS")
```



We check the link to the blog post:
![image](https://github.com/sromanhu/TotalCMS-Stored-XSS---Post/assets/87250597/dec3a06c-9cc0-4426-8947-a01be863ecdd)



We copy the Post Link and access the URL:
![image](https://github.com/sromanhu/TotalCMS-Stored-XSS---Post/assets/87250597/72dd8586-3292-46f9-8854-510b70f48c8d)




In the following image you can see the embedded code that executes the payload in the main web.
![image](https://github.com/sromanhu/TotalCMS-Stored-XSS---Post/assets/87250597/6adc8581-ffc2-4c0d-a4ea-450d1d278547)





</br>

### Additional Information:
[http://www.cmsmadesimple.org/](https://www.totalcms.co/)

https://owasp.org/Top10/es/A03_2021-Injection/
