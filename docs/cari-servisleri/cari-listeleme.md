---
description: >-
  Cari listeleme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir.
---

# Cari Listeleme

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="515.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/customer/customer_list</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Cari listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
    "filters":"",
    "params" :"",
    "limit":"1000",
    "offset" : "0",
    "sorting":[{"field": "id", "sort": "ASC"}]
}
```

!!! info
	Body içerisinde gönderilen alanlarla ilgili detayları görmek için [tıklayınız.](../../../filtreleme-parametreleri)

## Cari Listeleme.

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/customer/customer_list`

Ödüyo içerisindeki carileri listeler.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                     | Type   | Description          |
| ---------------------------------------- | ------ | -------------------- |
| filters                                  | string | Filtreleme alanıdır. |
| params                                   | string | Parametre alanıdır.  |
| limit<mark style="color:red;">\*</mark>  | string | Sorgu limiti.        |
| offset<mark style="color:red;">\*</mark> | string | Sayfalama            |
| sorting                                  | String | Sıralama             |

=== "200 Başarılı"
	```javascript
	{
    "status": true,
    "data": [
        {
            "id": "1",
            "name": "Test Carisi",
            "customer_type_1": "2",
            "customer_type_2": "1",
            "status": "1",
            "tax_department": "",
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
            "balance_paid": "0.0000",
            "created_in": "2021-11-26 12:34:43",
            "updated_in": "2021-11-26 12:34:43"
        },
        {
            "id": "2",
            "name": "Test Carisi 2",
            "customer_type_1": "2",
            "customer_type_2": "1",
            "status": "1",
            "tax_department": "",
            "tc_number": "",
            "group_code": "",
            "branch_key": "0",
            "branch_name": "",
            "telephone": "000000000000000",
            "email": "testiki@oduyo.com.tr",
            "country": "",
            "province": "",
            "district": "",
            "risk": "",
            "balance": "23600.0000",
            "balance_current": "23600.0000",
            "balance_paid": "5900.0000",
            "created_in": "2021-11-26 12:34:43",
            "updated_in": "2021-11-26 12:34:43"
        }
	}
	```
=== "401 Hatalı"
	```
	{
	}
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.

### <mark style="color:blue;">Sonuç Parametreleri</mark>

<table><thead><tr><th width="312">Tag</th><th width="222.38403041825097">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td>id</td><td>Tablo Pk İd</td><td><strong>Numerik(int)</strong></td></tr><tr><td>name</td><td>Cari Adı</td><td><strong>String</strong></td></tr><tr><td>customer_type_1</td><td>Cari Türü</td><td><strong>"1"="şahıs",               "2"="kuruluş",</strong></td></tr><tr><td>customer_type_2</td><td>Cari Türü</td><td><strong>'Alıcı'=>'1',    'Satıcı'=>'2',              'Alıcı + Satıcı'=>'3'</strong></td></tr><tr><td>current_card_code</td><td>Cari Kart Kodu</td><td><strong>String</strong></td></tr><tr><td>status</td><td>Cari Aktiflik Durumu</td><td><strong>'Aktif'=>'1',    'Pasif'=>'2',</strong>    </td></tr><tr><td>tax_department</td><td>Vergi Dairesi</td><td><strong>String</strong></td></tr><tr><td>tax_number</td><td>Vergi Numarası</td><td><strong>String</strong></td></tr><tr><td>tc_number</td><td>T.C Numarası</td><td><strong>String</strong></td></tr><tr><td>group_code</td><td>ERP Grup Kodu</td><td><strong>String</strong></td></tr><tr><td>branch_key</td><td>ERP Şube Kodu</td><td><strong>String</strong></td></tr><tr><td>branch_name</td><td>Şube Adı</td><td><strong>String</strong></td></tr><tr><td>telephone</td><td>Telefon Numarası</td><td><strong>String</strong></td></tr><tr><td>email</td><td>E-Posta Adresi</td><td><strong>String</strong></td></tr><tr><td>country</td><td>Ülke</td><td><strong>String</strong></td></tr><tr><td>province</td><td>İl</td><td><strong>String</strong></td></tr><tr><td>district</td><td>İlçe</td><td><strong>String</strong></td></tr><tr><td>balance</td><td>Cari Bakiye</td><td><strong>Numerik(</strong>decimal<strong>)</strong></td></tr><tr><td>balance_current</td><td>Vadesi Gelen Bakiye</td><td><strong>Numerik(</strong>decimal<strong>)</strong></td></tr><tr><td>balance_paid</td><td>Toplam Ödenen Bakiye</td><td><strong>Numerik(</strong>decimal<strong>)</strong></td></tr><tr><td>created_in</td><td>Cari Kayıt Tarihi</td><td><strong>Date</strong></td></tr><tr><td>updated_in</td><td>Cari Kayıt Güncellenme Tarihi</td><td><strong>Date</strong></td></tr></tbody></table>