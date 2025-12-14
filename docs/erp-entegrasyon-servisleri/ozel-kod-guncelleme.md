---
description: >-
  ERP sisteminde kayıtlı olan özel kodlarının, Ödüyo sisteminde güncellenmesi
  için kullanılan endpoint ve HTTP metod bilgisi aşağıda verilmiştir.
---

# Özel Kod Güncelleme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_special_code/update</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

<pre><code><strong>{
</strong>"column":{ 
            "id": "1",
            "integration_id": "1111111",
            "code": "TESTCODE",
            "status": "1",
            "key1": "21",
            "key2": "1",
            "note": null,
            "typecode": "26",
            "description": "-- asdfsd fasdfasdfasdf",
            "space1": "",
            "space2": "",
            "space3": "",
            "space4": "",
            "space5": "",
            "special_created_in": "2025-05-23 00:00:00",
            "special_updated_in": "2025-05-23 00:00:00"
        }
}
</code></pre>

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="172.36328125">Name</th><th width="130.3046875">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>n<strong>umerik(int)</strong></td><td>Özel koduna ait Ödüyo id</td></tr><tr><td>integration_id</td><td>string</td><td>Özel koduna ait ERP id(Erp eşleşmesi için gereklidir.)</td></tr><tr><td>code</td><td>string</td><td>Kod</td></tr><tr><td>status</td><td>string</td><td>Kullanım durumu("1" ⇒ aktif, "0" =>Pasif)</td></tr><tr><td>key1</td><td>string</td><td>Özel  kod</td></tr><tr><td>key2</td><td>string</td><td>Özel  kod</td></tr><tr><td>typecode</td><td>string</td><td>Özel kod türü</td></tr><tr><td>description</td><td>string</td><td>Açıklama</td></tr><tr><td>space1</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space2</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>special_created_in</td><td>datetime</td><td>Özel kod kaydedilme tarihi</td></tr><tr><td>special_updated_in</td><td>datetime</td><td>Özel kod güncellenme tarihi</td></tr></tbody></table>

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
