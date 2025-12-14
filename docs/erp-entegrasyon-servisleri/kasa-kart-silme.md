---
description: >-
  ERP sisteminde kayıtlı olan kasa kartlarının, Ödüyo sistemden silinmesi için
  kullanılan endpoint ve HTTP metod bilgisi aşağıda verilmiştir.
---

# Kasa Kart Silme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_kasa_fisi/delete</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

```
{
 "column":
     { 
      "id": "12"
     }
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="134.78515625">Name</th><th width="124.64453125">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>numeric(int)</td><td>Kasa kartına ait id bilgisi</td></tr></tbody></table>

=== "200"
    ```
    {
        "status": true,
        "data": "Kasa Kartı Silme Islemi Basarili"
    }
    ```
=== "404"
    ```
    {
        "status": false
    }
    ```