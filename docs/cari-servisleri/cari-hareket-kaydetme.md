---
description: >-
  Cari hareket kaydetme işlemi için kullanılan endpoint ve http metod bilgisi
  aşağıda verilmiştir
---

# Cari Hareket Kaydetme

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="177.3097476496784">HTTP Metod</th><th width="527.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="#url"><mark style="color:red;"><code>https://www.siteadi.com/api/v1/customer_transaction/customer_transaction_create</code></mark></a></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Cari hareket kaydetme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
"column":{ 
            "customer_id": "1",           
            "amount": "50",
            "sign": "2",
            "date": "2022.05.08",
            "hour": "16:00",            
            "comment": "pınartest",
            "currency": "TL"
            }
}
```

<table><thead><tr><th width="199">Tag</th><th width="334">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td><pre><code>customer_id*
</code></pre></td><td>Hareketin kaydedileceği cari pk id</td><td><strong>numerik(int)</strong></td></tr><tr><td><pre><code>amount*
</code></pre></td><td>Hareket tutarı(hareket tutarı borç ya da alacak belirtmeksizin sadece tutar olarak gönderilmelidir)</td><td><strong>numerik(</strong>decimal<strong>)</strong></td></tr><tr><td><pre><code>sign*
</code></pre></td><td>Hareket tutarının borç ya da alacak durumu</td><td><strong>"1"=alacak,              "-1"=borç,</strong></td></tr><tr><td><pre><code>date*
</code></pre></td><td>Hareket tarihi</td><td><strong>YYYY/AA/GG</strong></td></tr><tr><td><pre><code>hour*
</code></pre></td><td>Hareket saati</td><td><strong>Y-m-d H:i:s</strong></td></tr><tr><td><pre><code>comment*
</code></pre></td><td>Açıklama</td><td><strong>String</strong></td></tr><tr><td><pre><code>currency*
</code></pre></td><td>Hareket para birimi</td><td><strong>String</strong></td></tr></tbody></table>

## Cari Hareket Kaydetme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/customer_transaction/customer_transaction_create`

Ödüyo içerisine gönderilen cari hareket işlemlerini kaydeder.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                           | Type    | Description                        |
| ---------------------------------------------- | ------- | ---------------------------------- |
| amount<mark style="color:red;">\*</mark>       | numeric | Hareket tutarı                     |
| sign<mark style="color:red;">\*</mark>         | numeric | Borç ya da alacak durumu           |
| customer\_id<mark style="color:red;">\*</mark> | numeric | Hareketin kaydedileceği cari pk id |
| date<mark style="color:red;">\*</mark>         | date    | Hareket tarihi                     |
| hour<mark style="color:red;">\*</mark>         | time    | Hareket saati                      |
| comment<mark style="color:red;">\*</mark>      | String  | Açıklama                           |
| currency<mark style="color:red;">\*</mark>     | String  | Hareket para birimi                |

=== "200 Başarılı"
	```javascript
	{
    "status": true,
    "data": {
        "customer_id": "1",
        "amount": "50",
        "date": "2022.05.08",
        "hour": "16:00",
        "comment": "test",
        "currency": "TL",
        "debt": "0",
        "credit": "50",
        "transaction_number": "000000023",
        "document_no": "000000023",
        "transaction_type": "alacak"
		}
	}
	```

=== "400: Bad Request Hatalı"
	```
	{
	}
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.

### <mark style="color:blue;">Sonuç Parametreleri</mark> <a href="#url" id="url"></a>

Cari hareket kaydetme işlemi  için yapılan istek sonucunda alınması beklenen parametreler aşağıdaki tablo ve alt başlıklar altında listelenmiştir.

| Tag                 | Açıklama                          |
|---------------------|----------------------------------|
| `customer_id`       | Hareketin kaydedileceği cari pk id |
| `amount`            | Hareket tutarı                   |
| `date`              | Hareket tarihi                   |
| `hour`              | Hareket saati                   |
| `comment`           | Açıklama                        |
| `currency`          | Hareket para birimi             |
| `debt`              | Alacak tutarı                   |
| `credit`            | Borç tutarı                    |
| `transaction_number`| İşlem numarası                  |
| `document_no`       | Belge numarası                  |
| `transaction_type`  | Hareketin Alacak ya da Borç durumu |

