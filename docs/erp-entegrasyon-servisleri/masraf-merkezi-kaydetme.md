---
description: >-
  ERP sisteminde kayıtlı olan masraf merkezi kartlarının, Ödüyo sistemine
  kaydedilmesi için kullanılan endpoint ve HTTP metod bilgisi aşağıda
  verilmiştir.
---

# Masraf Merkezi Kaydetme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_masraf/create</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

```
{
"column":{ 
            "id": "3",
            "integration_id": "2", 
            "status": "1", 
            "key1": "21",
            "key2": "1", 
            "budget": "--",
            "calcbudget": "100", 
            "currency_budget": "120", 
            "description": "0",
            "space1":"",
            "space2":"",
            "space3":"",
            "space4":"",
            "space5":"",
            "masraf_created_in":"2025-05-23 00:00:00",
            "masraf_updated_in":"2025-05-23 00:00:00"
          }
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="194.27734375">Name</th><th width="124.64453125">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>n<strong>umerik(int)</strong></td><td>Masraf merkezine ait Ödüyo id</td></tr><tr><td>integration_id</td><td>string</td><td>Kasa kartına ait ERP id</td></tr><tr><td>status</td><td>string</td><td>Kullanım durumu("1" ⇒ aktif, "0" =>Pasif)</td></tr><tr><td>key1</td><td>string</td><td>Masraf  kodu</td></tr><tr><td>key2</td><td>string</td><td>Masraf  kodu</td></tr><tr><td>budget</td><td>decimal</td><td>Masraf merkezi açıklaması</td></tr><tr><td>calcbudget</td><td>string</td><td>Masraf  tutarı</td></tr><tr><td>currency_budget</td><td>string</td><td>Masraf dövizi</td></tr><tr><td>description</td><td>string</td><td>Açıklama</td></tr><tr><td>space1</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space2</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>masraf_created_in</td><td>datetime</td><td>Kaydedilme tarihi</td></tr><tr><td>masraf_updated_in</td><td>datetime</td><td>Güncellenme tarihi</td></tr></tbody></table>

=== "200"
    ```
    {
        "status": true,
        "data": "Erp Masraf successfully added id <1>"
    }
    ```

=== "404"
    ```
    {
        "status": false
    }
    ```
