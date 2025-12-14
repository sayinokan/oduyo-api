---
description: >-
  ERP sisteminde kayıtlı olan kasa kartlarının, Ödüyo sisteminde güncellenmesi
  için kullanılan endpoint ve HTTP metod bilgisi aşağıda verilmiştir.
---

# Kasa Kart Güncelleme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_kasa_fisi/update</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

```
{
"column":{ 
            "id" :2,
            "integration_id": "2", 
            "status": "1", 
            "key1": "21",
            "key2": "1", 
            "note": "--",
            "price": "100", 
            "price1": "120", 
            "price2": "0",
            "balance": "1260",
            "balance1": "1566",
            "balance2": "",
            "description":"MERKEZ KASA",
            "space2":"",
            "space3":"",
            "space4":"",
            "space5":"",
            "kasafisi_created_in":"2025-05-23 00:00:00",
            "kasafisi_updated_in":"2025-05-23 00:00:00"
          }
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

<table><thead><tr><th width="194.27734375">Name</th><th width="124.64453125">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>numeric(int)</td><td>Kasa kartına ait Ödüyo id</td></tr><tr><td>integration_id</td><td>string</td><td>Kasa kartına ait ERP id</td></tr><tr><td>status</td><td>string</td><td>Hesap kullanım durumu("1" ⇒ aktif, "0" =>Pasif)</td></tr><tr><td>key1</td><td>string</td><td>Kasa kart kodu</td></tr><tr><td>key2</td><td>string</td><td>Kasa kart kodu</td></tr><tr><td>note</td><td>string</td><td>Kasa kart açıklaması</td></tr><tr><td>price</td><td>decimal</td><td>Kasa kart tutarı</td></tr><tr><td>price1</td><td>decimal</td><td>Kasa kart tutarı</td></tr><tr><td>price2</td><td>decimal</td><td>Kasa kart tutarı</td></tr><tr><td>balance</td><td>decimal</td><td>Kasa bakiye</td></tr><tr><td>balance1</td><td>decimal</td><td>Kasa bakiye</td></tr><tr><td>balance2</td><td>decimal</td><td>Kasa bakiye</td></tr><tr><td>description</td><td>string</td><td>Açıklama</td></tr><tr><td>space2</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>kasafisi_created_in</td><td>datetime</td><td>Kaydedilme tarihi</td></tr><tr><td>kasafisi_updated_in</td><td>datetime</td><td>Güncellenme tarihi</td></tr></tbody></table>

**Request Body**

=== "200"
    ```
    {
        "status": true,
        "data": "Guncelleme islemi Basarili"
    }
    ```

=== "404"
    ```
    {
        "status": false
    }
    ```