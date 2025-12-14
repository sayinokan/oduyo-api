---
description: >-
  Cari güncelleme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir
---

# Cari Güncelleme

###

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="177.3097476496784">HTTP Metod</th><th width="569.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/customer/customer_update</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Cari güncelleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
"column":{ 
            "id": "1",
            "name": "Test Carisi",
            "customer_type_1": "2",
            "customer_type_2": "1",
            "status": "1", 
            "tax_department": "",
            "tax_number": "",
            "tc_number": "",
            "group_code": "",
            "branch_key": "0",
            "branch_name": "",
            "telephone": "000000000000000",
            "email": "test@oduyo.com.tr",
            "country": "",
            "province": "",
            "district": "",
            "risk": "",
            "balance": "-9440.0000",
            "balance_current": "0.0000",
            "balance_paid": "0.0000"
         }
}
```

<table><thead><tr><th width="241">Tag</th><th width="334">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td><pre><code>id
</code></pre></td><td>Güncellenecek Tablo Pk İd</td><td><strong>Numerik(int)</strong></td></tr><tr><td><pre><code>name
</code></pre></td><td>Cari Adı</td><td><strong>String</strong></td></tr><tr><td><pre><code>customer_type_1
</code></pre></td><td>Cari Türü</td><td><strong>"1"="şahıs",               "2"="kuruluş",</strong></td></tr><tr><td><pre><code>customer_type_2
</code></pre></td><td>Cari Türü</td><td><strong>'Alıcı'=>'1',    'Satıcı'=>'2',              'Alıcı + Satıcı'=>'3'</strong></td></tr><tr><td><pre><code>status
</code></pre></td><td>Cari Aktiflik Durumu</td><td><strong>Numerik</strong></td></tr><tr><td><pre><code>tax_department
</code></pre></td><td>Vergi Dairesi</td><td><strong>String</strong></td></tr><tr><td><pre><code><strong>tax_number
</strong></code></pre></td><td>Vergi Numarası</td><td><strong>String</strong></td></tr><tr><td><pre><code><strong>tc_number
</strong></code></pre></td><td>T.C Numarası</td><td><strong>String</strong></td></tr><tr><td><pre><code>group_code
</code></pre></td><td>ERP Grup Kodu</td><td><strong>String</strong></td></tr><tr><td><pre><code><strong>branch_key
</strong></code></pre></td><td>ERP Şube Kodu</td><td><strong>String</strong></td></tr><tr><td><pre><code>branch_name
</code></pre></td><td>Şube Adı</td><td><strong>String</strong></td></tr><tr><td><pre><code><strong>telephone
</strong></code></pre></td><td>Telefon Numarası</td><td><strong>String</strong></td></tr><tr><td><pre><code>email
</code></pre></td><td>E-Posta Adresi</td><td><strong>String</strong></td></tr><tr><td><pre><code><strong>country
</strong></code></pre></td><td>Ülke</td><td><strong>String</strong></td></tr><tr><td><pre><code>province
</code></pre></td><td>İl</td><td><strong>String</strong></td></tr><tr><td><pre><code>district
</code></pre></td><td>İlçe</td><td><strong>String</strong></td></tr><tr><td><pre><code><strong>risk
</strong></code></pre></td><td></td><td><strong>String</strong></td></tr><tr><td><pre><code><strong>balance*
</strong></code></pre></td><td>Cari Bakiye</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td><pre><code>balance_current*
</code></pre></td><td>Vadesi Gelen Bakiye</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td><pre><code>balance_paid*
</code></pre></td><td>Toplam Ödenen Bakiye</td><td><strong>Numerik(decimal)</strong></td></tr></tbody></table>

## Cari Güncelleme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/customer/customer_update`

Ödüyo içerisine gönderilen cari bilgilerini günceller.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                               | Type             | Description               |
| -------------------------------------------------- | ---------------- | ------------------------- |
| name                                               | string           | Cari Adı                  |
| customer\_type\_1                                  | string           | Cari Türü                 |
| id<mark style="color:red;">\*</mark>               | numeric(int)     | Güncellenecek Tablo Pk İd |
| customer\_type\_2                                  | string           | Cari Türü                 |
| status                                             | string           | Cari Aktiflik Durumu      |
| tax\_department                                    | string           | Vergi Dairesi             |
| tax\_number                                        | string           | Vergi Numarası            |
| tc\_number                                         | string           | T.C Numarası              |
| group\_code                                        | string           | ERP Grup Kodu             |
| branch\_key                                        | string           | ERP Şube Kodu             |
| branch\_name                                       | string           | Şube Adı                  |
| telephone                                          | string           | Telefon Numarası          |
| email                                              | string           | E-Posta Adresi            |
| country                                            | string           | Ülke                      |
| province                                           | string           | İl                        |
| district                                           | string           | İlçe                      |
| balance<mark style="color:red;">\*</mark>          | numeric(decimal) | Cari Bakiye               |
| balance\_current<mark style="color:red;">\*</mark> | numeric(decimal) | Vadesi Gelen Bakiye       |
| balance\_paid<mark style="color:red;">\*</mark>    | numeric(decimal) | Toplam Ödenen Bakiye      |

=== "200 Başarılı"
	```javascript
	{
    "status": true,
    "data": "<1> successfully updated."
	}
	```
=== "400: Bad Request Hatalı"
	```
	{
	}
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.
