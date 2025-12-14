---
description: >-
  ERP sisteminde kayıtlı olan ve Ödüyo ile eşleşmiş durumdaki banka hesapları
  güncelleme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir.
---

# Banka Hesap Güncelleme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_bank_account/update</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

```
{
"column":{ 
            "id" :121,
            "integration_id": "2", 
            "status": "1", 
            "currency": "TL",
            "account_no": "0960900010100046", 
            "iban": "TR660006701000000093520111",
            "account_name": "Akbank T.A.Ş.", 
            "account_code": "1000104", 
            "account_branch": "0609",
            "banka_key": "770-80-011",
            "space1":"",
            "space2":"",
            "space3":"",
            "space4":"",
            "space5":"",
            "note":"",
            "hhs_code":"",
            "hhs_code_desc":"",
            "tckn_area":"",
            "name":"",
            "phone_area":"",
            "email_area":""
          }
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="157.77734375">Name</th><th width="134.66796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>n<strong>umerik(int)</strong></td><td>Hesaba ait Ödüyo id</td></tr><tr><td>integration_id</td><td>string</td><td>Hesaba ait ERP id</td></tr><tr><td>status</td><td>string</td><td>Hesap kullanım durumu("1" ⇒ aktif, "0" =>Pasif)</td></tr><tr><td>currency</td><td>string</td><td>Hesabın döviz bilgisi</td></tr><tr><td>account_no</td><td>string</td><td>Hesap numarası</td></tr><tr><td>iban</td><td>string</td><td>Hesap iban numarası</td></tr><tr><td>account_name</td><td>string</td><td>Hesap adı</td></tr><tr><td>account_code</td><td>string</td><td>Hesap kodu</td></tr><tr><td>account_branch</td><td>string</td><td>Hesap şube numarası</td></tr><tr><td>banka_key</td><td>string</td><td>Hesap Erp kodu</td></tr><tr><td>space1</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space2</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>note</td><td>string</td><td>Hesap açıklama</td></tr><tr><td>hhs_code</td><td>string</td><td>Banka  kodu</td></tr><tr><td>hhs_code_desc</td><td>string</td><td>Banka  key</td></tr><tr><td>tckn_area</td><td>string</td><td>Hesabın tanımlı olduğu tckn</td></tr><tr><td>name</td><td>string</td><td>Hesaba ait ad soyad</td></tr><tr><td>phone_area</td><td>string</td><td>Bildirim tel no</td></tr><tr><td>email_area</td><td>string</td><td>Bildirim mail adresi</td></tr></tbody></table>

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