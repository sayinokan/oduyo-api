---
description: >-
  Hesap bilgileri listeleme işlemi için kullanılan endpoint ve http metod
  bilgisi aşağıda verilmiştir.
---

# Hesap Bilgileri

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="592.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/bank_account_configuration/bank_account_configuration_list</code></mark></td></tr></tbody></table>

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.

### <mark style="color:blue;">İşlem</mark> <mark style="color:blue;">Parametreleri</mark>

Hesap bilgileri listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

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

## Hesap Bilgileri Listeleme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/bank_account_configuration/bank_account_configuration_list`&#x20;

Ödüyo içerisindeki eklenmiş hesapların bilgilerini listeler.

#### Headers

| Name                                       | Type   | Description                                                                           |
| ------------------------------------------ | ------ | ------------------------------------------------------------------------------------- |
| Apikey\*<mark style="color:red;">\*</mark> | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization                              | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name    | Type   | Description          |
| ------- | ------ | -------------------- |
| filters | string | Filtreleme alanıdır. |
| params  | string | Parametre alanıdır.  |
| limit   | string | Sorgu limiti.        |
| offset  | string | Sayfalama            |
| sorting | string | Sıralama             |

===	"200: OK Başarılı"
    ```javascript
    {
        "status": true,
        "data": [
            {
                "id": "6",
                "bank": "garanti",
                "bankname": "Garanti Bankası",
                "account_name": "Garanti Bankası",
                "status": "1",
                "balance": "35788.0000",
                "bankusername": "",
                "bankusernameid": "",
                "bankpass": "",
                "bankiddbx": "55",
                "bankcurrency": "TRY",
                "bankcode": "10123",
                "bankfirmname": "Ödüyo Finansal A.Ş",
                "bankfirmcode": "",
                "bankaccountnum": "153215313",
                "bankserviceaddress": "",
                "bankiban": "TR220006200148000006689192",
                "bank_customer_no": "",
                "bankserviceid": "",
                "enviroment": "",
                "bankfirmkey": "",
                "bankcenternum": "",
                "bs_error": "",
                "space1": "",
                "space2": "",
                "space3": "",
                "space4": "",
                "space5": "",
                "space6": "",
                "space7": "4",
                "created_in": "2021-02-21 23:42:22",
                "updated_in": "2021-02-21 23:42:22",
                "bs_last_work": "2019-12-27 15:15:04",
                "bs_last_update": "2019-12-27 15:15:04"
            }
        ]
    }
    ```

=== "400: Bad Request Hatalı"

	```javascript
	{
    // Response
	}
	```

### <mark style="color:blue;">Sonuç</mark> <mark style="color:blue;">Parametreleri</mark>

<table><thead><tr><th width="224.43902439024393">Tag</th><th width="322.8006372325899">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td>id</td><td>Tablo Pk İd</td><td><strong>Numerik(int)</strong></td></tr><tr><td>bank</td><td>Banka Adı</td><td><strong>String</strong></td></tr><tr><td>bankname</td><td>Banka Adı</td><td><strong>String</strong></td></tr><tr><td>account_name</td><td>Hesap Adı</td><td><strong>String</strong></td></tr><tr><td>status</td><td>Aktif Olma Durumu</td><td><strong>String</strong></td></tr><tr><td>balance</td><td>Toplam Bakiye</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td>bankusername</td><td>Banka Kullanıcı Adı</td><td><strong>String</strong></td></tr><tr><td>bankusernameid</td><td>Banka Kullanıcı İd</td><td><strong>String</strong></td></tr><tr><td>bankpass</td><td>Banka Şifre Bilgisi</td><td><strong>String</strong></td></tr><tr><td>bankiddbx</td><td>Banka Hareket Unique ID</td><td><strong>String</strong></td></tr><tr><td>bankcurrency</td><td>Hesap Kur Birimi</td><td><strong>String</strong></td></tr><tr><td>bankcode</td><td>Banka Kodu</td><td><strong>String</strong></td></tr><tr><td>bankfirmname</td><td>Banka Firma Adı </td><td><strong>String</strong></td></tr><tr><td>bankfirmcode</td><td>Banka Firma Kodu</td><td><strong>String</strong></td></tr><tr><td>bankaccountnum</td><td>Banka Hesap Numarası</td><td><strong>String</strong></td></tr><tr><td>bankserviceaddress</td><td>Banka Servis Adresi</td><td><strong>String</strong></td></tr><tr><td>bankiban</td><td>Banka İban Numarası</td><td><strong>String</strong></td></tr><tr><td>bank_customer_no</td><td>Banka Müşteri Numarası</td><td><strong>String</strong></td></tr><tr><td>bankserviceid</td><td>Banka Servis İd</td><td><strong>String</strong></td></tr><tr><td>enviroment</td><td></td><td><strong>String</strong></td></tr><tr><td>bankfirmkey</td><td>Banka Firma Kodu</td><td><strong>String</strong></td></tr><tr><td>bankcenternum</td><td>Banka Merkez Numarası</td><td><strong>String</strong></td></tr><tr><td>bs_error</td><td>Hata Mesajı</td><td><strong>String</strong></td></tr><tr><td>space1</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space2</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space3</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space4</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space5</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space6</td><td>Banka Hesabına Ait Erp İd Bilgisi</td><td><strong>String</strong></td></tr><tr><td>space7</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>created_in</td><td>Veri Kayıt Tarihi</td><td><strong>Date</strong></td></tr><tr><td>updated_in</td><td>Veri Güncelleme Tarihi</td><td><strong>Date</strong></td></tr><tr><td>bs_last_work</td><td></td><td><strong>Date</strong></td></tr><tr><td>bs_last_update</td><td></td><td><strong>Date</strong></td></tr></tbody></table>