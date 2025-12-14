---
description: >-
  Hesap hareketleri listeleme işlemi için kullanılan endpoint ve http metod
  bilgisi aşağıda verilmiştir.
---

# Hesap Hareketleri

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="592.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/bank_account_data/bank_account_data_list</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark>

Hesap hareketleri listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

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

## Hesap Hareketleri Listeleme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/bank_account_data/bank_account_data_list`

Ödüyo içerisindeki hesap hareketlerini  listeler.

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
            "oduyo_bank_id": "5",
            "bank_id": "50",
            "bs_id": "428",
            "balance": "4056.4200",
            "total": "480.0000",
            "bs_name": "-",
            "bs_dc": "Credit",
            "bs_code": "BOE",
            "bs_note": "ÖRNEK BANKA HESAP HAREKETİ AÇIKLAMASI",
            "bankiddbx": "",
            "unique_id": "dd4e0b68677e541cb0b300c2ef877a8e",
            "opponent_name": "-",
            "opponent_iban": "TR560000011100023400916740",
            "space1": "",
            "space2": "",
            "space3": "",
            "space4": "",
            "space5": "",
            "space6": "",
            "space7": "",
            "table_update_userlog": null,
            "created_in": "2021-02-21 23:31:03",
            "updated_in": "2021-02-21 23:31:03",
            "bs_date_issue": "2020-11-27",
            "bs_date_readed": "2021-03-03 23:35:16"
        }
	}        
	```

=== "400: Bad Request Hatalı"
	```
	{
	}
	```

!!!info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.

### Sonuç Parametreleri

<table><thead><tr><th width="229.44946720659954">Tag</th><th width="312.5146551868354">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td>id</td><td>Tablo Pk İd</td><td><strong>Numerik(int)</strong></td></tr><tr><td>oduyo_bank_id</td><td>Banka Hesap Bilgisini Çeken Serviste Yer Pk Bilgisi</td><td><strong>Numerik(int)</strong></td></tr><tr><td>bank_id</td><td>Banka Hareketini Okuyan Sunucunun Banka İçin Tuttuğu Pk Bilgisi</td><td><strong>Numerik(int)</strong></td></tr><tr><td>bs_id</td><td>Banka Hareketini Okuyan Sunucunun Banka Hareketi İçin Tuttuğu Pk Bilgisi</td><td><strong>Numerik(int)</strong></td></tr><tr><td>balance</td><td>Hesapta Yer Alan Total Bakiye</td><td><strong>Numerik(</strong>decimal<strong>)</strong></td></tr><tr><td>total</td><td>İşlem Total Fiyat Bilgisi.</td><td><strong>Numerik(</strong>decimal<strong>)</strong></td></tr><tr><td>bs_name</td><td>Hareketin Aktarılacağı Hesap Adı</td><td><strong>String</strong></td></tr><tr><td>bs_dc</td><td>Kart Tip Kodu</td><td><strong>"Debit"=Para Çıkışı,   "Credit"=Para Girişi</strong></td></tr><tr><td>bs_code</td><td>Banka İşlem Kodu</td><td><strong>String</strong></td></tr><tr><td>bs_note</td><td>Hareket Açıklaması</td><td><strong>String</strong></td></tr><tr><td>bankiddbx</td><td>Banka Hareket Unique ID</td><td><strong>String</strong></td></tr><tr><td>unique_id</td><td>Banka Hareket Unique Code</td><td><strong>String</strong></td></tr><tr><td>opponent_name</td><td>Paranın Gönderildiği Karşı Hesap Adı</td><td><strong>String</strong></td></tr><tr><td>opponent_iban</td><td>Paranın Gönderildiği Karşı İban</td><td><strong>String</strong></td></tr><tr><td>space1</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space2</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space3</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space4</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space5</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space6</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space7</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>table_update_userlog</td><td>Tabloyu Güncelleyen Kullanıcı Log Bilgisi</td><td><strong>String</strong></td></tr><tr><td>created_in</td><td>Tablo ekleme tarihi</td><td><strong>Date</strong></td></tr><tr><td>updated_in</td><td>Tablodaki Verinin Güncellendiği Tarih</td><td><strong>Date</strong></td></tr><tr><td>bs_date_issue</td><td>Banka Hareketinin Okunduğu Tarih</td><td><strong>Date</strong></td></tr><tr><td>bs_date_readed</td><td>Banka Hareketinin Okunduğu Tarih Detay</td><td><strong>Date</strong></td></tr></tbody></table>


