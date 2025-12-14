---
description: >-
  Ödüyo API sorguları yaparken sistemden Session ID alıp body içerisinde oturum
  bilgilerini göndermeniz gerekmektedir. API servisimiz APIKEY ve Session ID
  doğrulaması yapmaktadır.
---

# Kullanıcı Denetimi

### API Key ile Session ID Alma

İstekler gönderilirken istek başlıklarına mutlaka Apikey ve Session ID doğrulama eklenmelidir. Api anahtarınızı APIKEY sayfasından alabilir, yenisini üretebilirsiniz. Aşağıdaki örneklerle web serviste Session açabilir tüm servisleri bu şekilde kullanabilirsiniz. Alınan Session ID süresi 60 dakikadır. Bu süre dolduktan sonra yeniden Session ID alınmalıdır.

```
Apikey API_ANAHTARINIZ
Authorization SESSION_ID
```

!!! info
    `API_ANAHTARINIZ`, Ödüyo içerisinden kopyaladığınız API anahtarınızdır.  
    Bu değeri tekrar `base64 encode` işlemi yapmanıza gerek yoktur.


!!! info
    `SESSION_ID` almak için servisle sisteme giriş yapmanız gerekmektedir.  
    Giriş (login) işlemi sonucunda sistem size **60 dakika geçerli** bir `SESSION_ID` dönecektir.

CURL Örneği

```
# curl --location --request POST 'https://www.siteadi.com/api/v1/ws/login' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Cookie: ci_session=kktk4vntv5g4dn6bb2cadualadtqmp5v' \
--data-urlencode 'username=test' \
--data-urlencode 'oduyo_api_key=test' \
--data-urlencode 'password=test'
```

Javascript örneği

```javascript
var settings = {
  "url": "https://www.siteadi.com/api/v1/ws/login",
  "method": "POST",
  "timeout": 0,
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
    "Cookie": "ci_session=kktk4vntv5g4dn6bb2cadualadtqmp5v"
  },
  "data": {
    "username": "test",
    "oduyo_api_key": "test",
    "password": "test"
  }
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

C# Örneği

```
var client = new RestClient("https://www.siteadi.com/api/v1/ws/login");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/x-www-form-urlencoded");
request.AddHeader("Cookie", "ci_session=kktk4vntv5g4dn6bb2cadualadtqmp5v");
request.AddParameter("username", "test");
request.AddParameter("oduyo_api_key", "test");
request.AddParameter("password", "test");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

PHP Örneği

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.siteadi.com/api/v1/ws/login',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => 'username=test&oduyo_api_key=test&password=test',
  CURLOPT_HTTPHEADER => array(
    'Content-Type: application/x-www-form-urlencoded',
    'Cookie: ci_session=kktk4vntv5g4dn6bb2cadualadtqmp5v'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```