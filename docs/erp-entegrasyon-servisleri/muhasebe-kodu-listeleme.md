---
description: >-
  ERP sisteminde kayıtlı olan ve Ödüyo ile eşleşmiş durumdaki Muhasebe kodları
  listeleme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir.
---

# Muhasebe Kodu Listeleme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_muhCode/list</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

<pre><code>{
    "filters":"",
    "params" :"",
<strong>    "limit":"1000",
</strong>    "offset" : "0",
    "sorting":[{"field": "id", "sort": "ASC"}]
}
</code></pre>

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="190.34375">Name</th><th width="130.3046875">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>n<strong>umerik(int)</strong></td><td>Muhasebe koduna ait Ödüyo id</td></tr><tr><td>integration_id</td><td>string</td><td>Muhasebe koduna ait ERP id</td></tr><tr><td>code</td><td>string</td><td>Kod</td></tr><tr><td>status</td><td>string</td><td>Kullanım durumu("1" ⇒ aktif, "0" =>Pasif)</td></tr><tr><td>key1</td><td>string</td><td>Muhasebe kodu</td></tr><tr><td>key2</td><td>string</td><td>Muhasebe kodu</td></tr><tr><td>type</td><td>string</td><td>Tür</td></tr><tr><td>description</td><td>string</td><td>Açıklama</td></tr><tr><td>description2</td><td>string</td><td>Açıklama</td></tr><tr><td>space1</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space2</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>muhkod_created_in</td><td>datetime</td><td>Muhasebe kodu kaydedilme tarihi</td></tr><tr><td>muhkod_updated_in</td><td>datetime</td><td>Muhasebe kodu güncellenme tarihi</td></tr><tr><td>created_in</td><td>datetime</td><td>Kaydedilme tarihi</td></tr><tr><td>updated_in</td><td>datetime</td><td>Güncellenme tarihi</td></tr></tbody></table>

=== "200"
    ```
    {
        "status": true,
        "data": [
            {
                "id": "1",
                "integration_id": "34",
                "code": "150902",
                "key1": "12",
                "key2": "15",
                "type": "satış",
                "description": "Muhasebe Kodu",
                "description2": "Muhasebe Kodu",
                "space1": null,
                "space2": null,
                "space3": null,
                "space4": null,
                "space5": null,
                "muhkod_created_in": "2025-08-14 15:55:48",
                "muhkod_updated_in": "2025-08-18 15:55:48",
                "created_in": "2025-08-20 15:55:48",
                "updated_in": "2025-08-22 15:55:48"
            }
        ]
    }
    ```

=== "404"
    ```
    {
        "status": false
    }
    ```