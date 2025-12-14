---
description: >-
  ERP sisteminde kayıtlı olan ve Ödüyo ile eşleşmiş durumdaki banka hareketleri
  güncelleme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir.
---

# Erp Banka Hareketleri Güncelleme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_bank_transfer/update</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

```postman_json
{
    "column": {
        "id": 8096,
        "erp_status": "success"
    }
}
```

#### &#x20;<a href="#url-1" id="url-1"></a>

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="174.26953125">Name</th><th width="155.6015625">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>n<strong>umerik(int)</strong></td><td>Proje koduna ait Ödüyo id</td></tr><tr><td>erp_status</td><td>string</td><td>Aktarım durumu("success" ⇒ aktarıldı, "error" =>Aktarılamadı)</td></tr></tbody></table>

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
