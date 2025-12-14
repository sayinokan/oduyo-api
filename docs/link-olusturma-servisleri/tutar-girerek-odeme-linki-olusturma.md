---
description: >-
  Ödeme link oluşturma işlemi için kullanılan endpoint ve http metod bilgisi
  aşağıda verilmiştir.
---

# Tutar Girerek Ödeme Linki Oluşturma

URL

<table><thead><tr><th width="166.546875">HTTP Metod</th><th>URL</th></tr></thead><tbody><tr><td>POST</td><td><a href="https://www.siteadi.com/api/v1/payment/payment_create">https://www.siteadi.com/api/v1/</a>api/v1/pay/get_link</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

Ödeme linki oluşturmak  için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.



```
{
    "id":"76",
    "integration_id":"", 
    "price":500,
    "email":"pinar.koprulu@oduyo.com.tr",
    "payment_type":"2"
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**


<table><thead><tr><th width="260">Name</th><th width="125">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>numeric(int)</td><td>Cariye ait id bilgisi</td></tr><tr><td>integration_id</td><td>numeric(int)</td><td>Carinin  entegrasyon id bilgisi(id ya da integration_id değerlerinden bir tanesi kullanılır)</td></tr><tr><td>price</td><td>string</td><td>Ödeme tutarı</td></tr><tr><td>email</td><td>string</td><td>Makbuz gönderilecek email bilgisi</td></tr><tr><td>payment_type</td><td>numeric(int)</td><td>Ödeme türü(Tutar girerek ödeme=2)</td></tr><tr><td>installment</td><td>numeric(int)</td><td>Taksit sayısı</td></tr><tr><td>“expire_time”:“2025-07-28"</td><td>date</td><td>Son ödeme tarihi</td></tr></tbody></table>

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