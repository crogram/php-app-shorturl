# php-app-shorturl

## ð PHP è½»éçº§ç­é¾æ¥ç³»ç»

æ¬ç¨åºæ¯ä¸æ¬¾ç®åçç­é¾æ¥çæç³»ç»ï¼æå¶æ¹ä¾¿é¨ç½²ã

#### ä½éªé¢è§

[url.uiisc.ml](http://url.uiisc.ml)

![preview](WX20221126-114544.jpg)

### æ¯æåè½

- ðµAPIå¿«éçæç­é¾æ¥
- ð±å¨çº¿ç½é¡µçæç­é¾æ¥
- ðæ¯æRedisãFileç¼å­æ§å¶ï¼å¼åä¸­ï¼
- ðð¼ââï¸ åå§: ç´æ¥è·³è½¬å°ç®æ ç½ç«
- ð¸æ Referer: æ  Referer åæ°ï¼ç®æ ç½ç«æ æ³è·åæ¥æºç«å°å
- ð· å å¯è·³è½¬ : å å¯è·³è½¬åæ°ä¿¡æ¯ï¼åå¤§é¨åç¬è«æåæ¢æµ
- ðº ä¼ªè£é¡µé¢ : ä½¿ç¨éæºä¿¡æ¯ãè®ºåãååæ¥éªè¿æºå¨äººç¬è«
- ð¥ éåå³ç: ä¸æ¬¡æ§è·³è½¬(éåå³ç)
- ð å¯ç è®¿é®: å°ä¸ºä½ çæå¯ç ï¼è®¿é®æ¶éè¦å¯ç éªè¯
- ð éå å¾æ: éå å¯ææ¬ä¿¡æ¯ï¼æ¨å¯ä»¥å¨æ­¤çè¨å¹¶åäº«ç»æ¨çå¶ä»ç¤¾äº¤åªä½ç¨æ·
- ð» ä»éPCè®¿é®
- ð± ä»éææºè®¿é®
- ð¨ð³ ä»éä¸­å½å¤§éç¨æ·è®¿é®
- ðºï¸ ä»ééä¸­å½å¤§éç¨æ·è®¿é®


#### å®è£

##### ä¸è½½æ¬ç¨åºå°ç½ç«æ ¹ç®å½

```bash
php -S 127.0.0.1:12138
```

##### è®¿é®æµè§

http://127.0.0.1:12138

##### Nginx éç½®

```nginx
location / {
    try_files $uri $uri/ /index.php?$query_string;
}
```

##### Apache éç½®

```apl
RewriteEngine on
RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ /index.php/?$1 [L]
```


##### äºçº§ç®å½éç½®

æ¯å¦ï¼`/shorturl/`ä»¥ `/` ç»å°¾ï¼å®éè®¿é® `http://ip/shorturl/`

```php
define('SUB_PATH', '/shorturl/');
```

åæ ·ï¼è¿é Nginx è¦åéç½®

```nginx
 location /shorturl {
    try_files $uri $uri/ /shorturl/index.php?$query_string;
 }
```

è¿é Apache è¦åéç½®

```apl
RewriteRule ^(.*)$ /shorturl/index.php/?$1 [L]
```

#### API

##### çæç­é¾æ¥

```bash
curl -s http://127.0.0.1:12138/api/link?url=https://uinote.com/article-430.html
```

Response

```json
{"msg":"ok","code":200,"data":"http://127.0.0.1:12138/s/aFdlm"}
```

this project's initial version is forked from https://github.com/ellermister/shorturl, thanks to [ellermister](https://github.com/ellermister) !


