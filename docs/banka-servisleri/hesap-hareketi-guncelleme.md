---
description: >-
  Erp tarafına aktarılan hareketlerin güncelleme işlemi için kullanılan endpoint
  ve http metod bilgisi aşağıda verilmiştir.
---

# Hesap Hareketi Güncelleme

###

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="177.3097476496784">HTTP Metod</th><th width="569.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/bank_account_data/bank_account_data_update</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Hesap hareketi güncelleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
"column":{ 
            "id": "1",
            "space3": "Error"
         }
}
```

<table><thead><tr><th width="241">Tag</th><th width="334">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td><pre><code>id
</code></pre></td><td>Güncellenecek Tablo Pk İd</td><td><strong>Numerik(int)</strong></td></tr><tr><td><pre><code>space3
</code></pre></td><td>Hesap hareketi aktarım bilgisi</td><td><strong>String</strong></td></tr></tbody></table>

## Hesap Hareketi Güncelleme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/bank_account_data/bank_account_data_update`

Ödüyo içerisine gönderilen hesap hareketi bilgilerini günceller.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                 | Type         | Description                    |
| ------------------------------------ | ------------ | ------------------------------ |
| space3                               | string       | Hesap hareketi aktarım bilgisi |
| id<mark style="color:red;">\*</mark> | numeric(int) | Güncellenecek Tablo Pk İd      |

=== "200 Başarılı"
	```javascript
	{
    "status": true,
    "data": "<1> successfully updated."
	}
	```

===	"400: Bad Request Hatalı"
	```
	{
	{
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.
