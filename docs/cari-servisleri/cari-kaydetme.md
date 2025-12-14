---
description: >-
  Cari kaydetme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir
---

# Cari Kaydetme

###

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="177.3097476496784">HTTP Metod</th><th width="569.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/customer/customer_create</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Cari  kaydetme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
"column":{ 
            "name": "Test Carisi",
            "current_card_code": "0002",
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

<table><thead><tr><th width="241">Tag</th><th width="322">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td><pre><code>name
</code></pre></td><td>Cari Adı</td><td><strong>String</strong></td></tr><tr><td><pre><code>current_card_code
</code></pre></td><td>Cari Kart Kodu</td><td><strong>String</strong></td></tr><tr><td><pre><code>customer_type_1
</code></pre></td><td>Cari Türü</td><td><strong>String("1"="şahıs",               "2"="kuruluş",)</strong></td></tr><tr><td><pre><code>customer_type_2
</code></pre></td><td>Cari Türü</td><td><strong>String('Alıcı'=>'1',    'Satıcı'=>'2',              'Alıcı + Satıcı'=>'3')</strong></td></tr><tr><td><pre><code>status
</code></pre></td><td>Cari Aktiflik Durumu</td><td><strong>String('Aktif'=>'1',    'Pasif'=>'2', )</strong></td></tr><tr><td><pre><code>tax_department
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
</code></pre></td><td>İlçe</td><td><strong>String</strong></td></tr><tr><td><pre><code><strong>balance*
</strong></code></pre></td><td>Cari Bakiye</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td><pre><code>balance_current*
</code></pre></td><td>Vadesi Gelen Bakiye</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td><pre><code>balance_paid*
</code></pre></td><td>Toplam Ödenen Bakiye</td><td><strong>Numerik(decimal)</strong></td></tr></tbody></table>

## Cari Kaydetme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/customer/customer_create`

Ödüyo içerisine gönderilen cari bilgilerini kaydeder.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                               | Type    | Description          |
| -------------------------------------------------- | ------- | -------------------- |
| current\_card\_code                                | numeric | Cari Kart Kodu       |
| customer\_type\_1                                  | numeric | Cari Türü            |
| name                                               |         | Cari Adı             |
| customer\_type\_2                                  | numeric | Cari Türü            |
| status                                             | numeric | Cari Aktiflik Durumu |
| tax\_department                                    | String  | Vergi Dairesi        |
| tax\_number                                        | String  | Vergi Numarası       |
| tc\_number                                         | String  | T.C Numarası         |
| group\_code                                        | String  | ERP Grup Kodu        |
| branch\_key                                        | String  | ERP Şube Kodu        |
| branch\_name                                       | String  | Şube Adı             |
| telephone                                          | String  | Telefon Numarası     |
| email                                              | String  | E-Posta Adresi       |
| country                                            | String  | Ülke                 |
| province                                           | String  | İl                   |
| district                                           | String  | İlçe                 |
| risk                                               | String  |                      |
| balance<mark style="color:red;">\*</mark>          | numeric | Cari Bakiye          |
| balance\_current<mark style="color:red;">\*</mark> | numeric | Vadesi Gelen Bakiye  |
| balance\_paid<mark style="color:red;">\*</mark>    | numeric | Toplam Ödenen Bakiye |

=== "200 Başarılı"
	```javascript
	{
    "status": true,
    "data": "Customer successfully added id <4>"
	}
	```

=== "401 Hatalı"
	```
	{
	}
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.
