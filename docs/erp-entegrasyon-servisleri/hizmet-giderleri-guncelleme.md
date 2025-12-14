---
description: >-
  ERP sisteminde kayıtlı olan ve Ödüyo ile eşleşmiş durumdaki Hizmet Gideri
  güncelleme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir.
---

# Hizmet Giderleri Güncelleme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_services/update</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

```
{
"column":{
            "id": "1",
            "integration_id": "164380",
            "status": "P",
            "key1": "2",
            "key2": "1",
            "description": "HARİTACILIK HİZMETİ",
            "muh_description": "",
            "space1": "Alınan",
            "space2": "AX001",
            "space3": "",
            "space4": "",
            "space5": "",
            "services_created_in": "0000-00-00 00:00:00",
            "services_updated_in": "2022-02-18 16:46:26",
            "created_in": "2025-03-06 12:44:54",
            "updated_in": "2025-03-06 12:44:54"
        }
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="181.203125">Name</th><th width="133.09765625">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>numeric(int)</td><td>Hizmet giderine ait Ödüyo id</td></tr><tr><td>integration_id</td><td>string</td><td>Hizmet giderine ait ERP id</td></tr><tr><td>status</td><td>string</td><td>Hizmet kullanım durumu("A" ⇒ aktif, "P" =>Pasif)</td></tr><tr><td>key1</td><td>string</td><td>Hizmet Key</td></tr><tr><td>key2</td><td>string</td><td>Hizmet Key</td></tr><tr><td>description</td><td>string</td><td>Açıklama</td></tr><tr><td>muh_description</td><td>string</td><td>Açıklama</td></tr><tr><td>space1</td><td>string</td><td>Hizmet türü</td></tr><tr><td>space2</td><td>string</td><td>Hizmet kodu</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>services_created_in</td><td>datetime</td><td>Hizmet kayıt tarihi</td></tr><tr><td>services_updated_in</td><td>datetime</td><td>Hizmet güncelleme tarihi</td></tr><tr><td>created_in</td><td>datetime</td><td>Kayıt tarihi</td></tr><tr><td>updated_in</td><td>datetime</td><td>Güncelleme tarihi</td></tr></tbody></table>

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