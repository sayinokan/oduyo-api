---
description: >-
  ERP sisteminde kayıtlı olan Çek ve Senetlerin, Ödüyo sistemine kaydedilmesi
  için kullanılan endpoint ve HTTP metod bilgisi aşağıda verilmiştir.
---

# Çek & Senet Kaydetme

öURL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_cek_senet/create</td></tr></tbody></table>

#### İşlem Parametreleri <a href="#url-1" id="url-1"></a>

```
{
"column":{
            "id": "1",
            "integration_id": "1",
            "currency": "TL",
            "currency_key": "2147483647",
            "bordro_key": "1398",
            "customer_code": "120.01.05.006",
            "portfoy_no": "P009298",
            "status": "PRTF",
            "type": "SNT_MST",
            "amount": "140000.0000",
            "bank_key": "O",
            "account_no": "10111111",
            "account_name": "Vadesiz Tl",
            "iban": "TR380001200134600010111111",
            "account_code": "1245696",
            "account_branch": "Karataş Şube",
            "customer_key": "1234556",
            "firmname": "Ödüyo Finansal Teknoloji A.Ş.",
            "space1": "",
            "space2": "",
            "space3": "",
            "space4": "",
            "space5": "",
            "created_in": "2025-08-11 16:07:52",
            "updated_in": "2025-08-11 16:07:52",
            "bordro_info": "",
            "note": "",
            "vade": "2025-08-11 16:07:52"
        }
}
```

Headers

<table><thead><tr><th width="156.984375">Name</th><th width="125.91796875">Type</th><th>Description</th></tr></thead><tbody><tr><td>Apikey*</td><td>String</td><td>Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.</td></tr><tr><td>Authorization*</td><td>String</td><td>Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION_ID)</td></tr></tbody></table>

**Request Body**

<table><thead><tr><th width="157.77734375">Name</th><th width="133.09765625">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>numeric(int)</td><td>Çek ve Senete ait Ödüyo id</td></tr><tr><td>integration_id</td><td>string</td><td>Çek ve Senete ait ERP id</td></tr><tr><td>currency</td><td>string</td><td>Döviz bilgisi</td></tr><tr><td>currency_key</td><td>string</td><td>Döviz kodu</td></tr><tr><td>bordro_key</td><td>string</td><td>Bordro kodu</td></tr><tr><td>customer_code</td><td>string</td><td>Cari kodu</td></tr><tr><td>portfoy_no</td><td>string</td><td>Portföy kodu</td></tr><tr><td>status</td><td>string</td><td>Hesap kullanım durumu("1" ⇒ aktif, "0" =>Pasif)</td></tr><tr><td>type</td><td>string</td><td>Çek - Senet türü</td></tr><tr><td>amount</td><td>decimal</td><td>Tutar</td></tr><tr><td>banka_key</td><td>string</td><td>Hesap Erp kodu</td></tr><tr><td>account_no</td><td>string</td><td>Hesap numarası</td></tr><tr><td>account_name</td><td>string</td><td>Hesap adı</td></tr><tr><td>iban</td><td>string</td><td>Hesap iban numarası</td></tr><tr><td>account_branch</td><td>string</td><td>Hesap şube numarası</td></tr><tr><td>customer_key</td><td>string</td><td>Cari kodu</td></tr><tr><td>firmname</td><td>string</td><td>Firma adı</td></tr><tr><td>space1</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space2</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>created_in</td><td>datetime</td><td>Kayıt tarihi</td></tr><tr><td>updated_in</td><td>datetime</td><td>Güncelleme tarihi</td></tr><tr><td>bordro_info</td><td>string</td><td>Bordro açıklama</td></tr><tr><td>note</td><td>string</td><td>Açıklama</td></tr><tr><td>vade</td><td>datetime</td><td>Vade tarihi</td></tr></tbody></table>

=== "200"
    ```
    {
        "status": true,
        "data": "Çek & Senet successfully added id <1>"
    }
    ```

=== "404"
    ```
    {
        "status": false
    }
    ```