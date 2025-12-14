---
description: >-
  Serbest ödeme link oluşturma işlemi için kullanılan endpoint ve http metod
  bilgisi aşağıda verilmiştir.
---

# Serbest Ödeme Link Oluşturma

URL

<table><thead><tr><th width="166.546875">HTTP Metod</th><th>URL</th></tr></thead><tbody><tr><td>POST</td><td><a href="https://www.siteadi.com/api/v1/payment/payment_create">https://www.siteadi.com/</a>api/v1/payLink/getlink</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

Serbest ödeme linki oluşturmak  için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
    "id":"76"
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**


<table><thead><tr><th width="134.78515625">Name</th><th width="124.64453125">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>numeric(int)</td><td>Cariye ait id bilgisi</td></tr></tbody></table>

=== "200"
	```
	{
    "status": true,
    "data": "{\"url\":\"http:\\/\\/127.0.0.1\\/paymentnew\\/?4ABE7AE7A199CEE87D34CC1360E706=s%3A96%3A%22eJwLLqksLqkMNQwJicwsSnR2yUoMCvWsDEwNNcwrj8j01DbyCfI3McjxzNJOc%2FF28korLXXKSE2OCCtxLQr1ds0tBADYbhYh%22%3B\",\"paymentsendid\":\"wEMi6QXkBCRls5u20250721123434\"}"
	}
	```

=== "404"
	```
	{
    "status": false,
    "message": "No record found for this ID"
	}
	```