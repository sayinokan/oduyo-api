---
description: >-
  ERP sisteminde kayıtlı olan proje kodlarının, Ödüyo sisteminde güncellenmesi
  için kullanılan endpoint ve HTTP metod bilgisi aşağıda verilmiştir.
---

# Proje Kodları Güncelleme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_project_code/update</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

```
{
"column":{ 
            "id": "2", 
            "integration_id": "22", 
            "status": "1", 
            "key1": "21",
            "key2": "1", 
            "description": "-- asdfsd fasdfasdfasdf",
            "space1":"",
            "space2":"",
            "space3":"",
            "space4":"",
            "space5":"",
            "project_created_in":"2025-05-23 00:00:00",
            "project_updated_in":"2025-05-23 00:00:00"
         }
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="174.26953125">Name</th><th width="155.6015625">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>n<strong>umerik(int)</strong></td><td>Proje koduna ait Ödüyo id</td></tr><tr><td>integration_id</td><td>string</td><td>Proje koduna ait ERP id</td></tr><tr><td>status</td><td>string</td><td>Kullanım durumu("1" ⇒ aktif, "0" =>Pasif)</td></tr><tr><td>key1</td><td>string</td><td>Proje  kodu</td></tr><tr><td>key2</td><td>string</td><td>Proje  kodu</td></tr><tr><td>description</td><td>string</td><td>Açıklama</td></tr><tr><td>space1</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space2</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>project_created_in</td><td>datetime</td><td>Kaydedilme tarihi</td></tr><tr><td>project_updated_in</td><td>datetime</td><td>Güncellenme tarihi</td></tr></tbody></table>

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
