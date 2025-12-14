---
description: >-
  Cari hareket silme işlemi için kullanılan endpoint ve http metod bilgisi
  aşağıda verilmiştir
---

# Cari Hareket Silme

###

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="177.3097476496784">HTTP Metod</th><th width="569.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/customer_transaction/customer_transaction_delete</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Cari hareket silme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
"column":{ 
            "id": "1"
         }
}
```

<table><thead><tr><th width="215">Tag</th><th>Açıklama</th><th>Format</th></tr></thead><tbody><tr><td><code>id*</code></td><td>Silinecek Tablo Pk İd</td><td><strong>Numerik(int)</strong></td></tr></tbody></table>

## Cari Hareket Silme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/customer_transaction/customer_transaction_delete`

Ödüyo içerisine gönderilen cari hareket kaydını siler.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                 | Type         | Description           |
| ------------------------------------ | ------------ | --------------------- |
| id<mark style="color:red;">\*</mark> | numeric(int) | Silinecek Tablo Pk İd |

=== "200 Başarılı"
	```javascript
	{
    "status": true,
    "data": "1 is successfully deleted"
	}
	```

=== "400: Bad Request Hatalı"
	```
	{
	}
	```
	
!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.
