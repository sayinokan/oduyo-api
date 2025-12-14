---
description: >-
  ERP sisteminde kayıtlı olan ve Ödüyo ile eşleşmiş durumdaki banka hareketleri
  listeleme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir.
---

# Erp Banka Hareketleri Listeleme

URL

<table><thead><tr><th width="149.40234375">HTTP Metod</th><th></th></tr></thead><tbody><tr><td>POST</td><td>https://www.siteadi.com/api/v1/erp/erp_bank_transfer/list</td></tr></tbody></table>

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

**Response**&#x20;

<table><thead><tr><th width="207.2265625">Name</th><th width="155.6015625">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>n<strong>umerik(int)</strong></td><td>Harekete ait Ödüyo id</td></tr><tr><td>customer_id</td><td>string</td><td>Aktarım yapılacak cari  id</td></tr><tr><td>customer_vkn</td><td>string</td><td>Cari vkn</td></tr><tr><td>transaction_id</td><td>string</td><td>Hareket id</td></tr><tr><td>bank_id</td><td>n<strong>umerik(int)</strong></td><td>Hareketin ait olduğu banka id</td></tr><tr><td>transaction_code</td><td>string</td><td>Hareket işlem kodu</td></tr><tr><td>category</td><td>string</td><td>Fiş türü</td></tr><tr><td>transfer_account</td><td>string</td><td>Hesap bilgisi</td></tr><tr><td>account_iban</td><td>string</td><td>Aktarım yapılacak hesap iban</td></tr><tr><td>erp_status</td><td>string</td><td>Aktarım durumu("success" ⇒ aktarıldı, "error" =>Aktarılamadı)</td></tr><tr><td>erp_response</td><td>string</td><td>Aktarım sonucu erp response</td></tr><tr><td>erp_transferred_bank</td><td>string</td><td>Aktarım yapılacak Erp banka</td></tr><tr><td>erp_transferred_bank2</td><td>string</td><td>Aktarım yapılacak Erp virman banka</td></tr><tr><td>customer_data1</td><td>string</td><td>Cari detay</td></tr><tr><td>customer_data2</td><td>string</td><td>Cari detay</td></tr><tr><td>transaction_description</td><td>string</td><td>Aktarım Açıklama </td></tr><tr><td>salesman_id</td><td>string</td><td>Satış elemanı kodu</td></tr><tr><td>cost_center_id</td><td>string</td><td>Masraf kodu</td></tr><tr><td>project_code</td><td>string</td><td>Proje kodu</td></tr><tr><td>material_code</td><td>string</td><td>Malzeme bağlantı kodu</td></tr><tr><td>branch_id</td><td>string</td><td>Erp şube id</td></tr><tr><td>account_code</td><td>string</td><td>Muhasebe kodu</td></tr><tr><td>special_code</td><td>string</td><td>Kar merkezi kodu</td></tr><tr><td>currency</td><td>string</td><td>Döviz tipi</td></tr><tr><td>currency_amount</td><td>string</td><td>Döviz tutarı</td></tr><tr><td>space1</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space2</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space3</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space4</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>space5</td><td>string</td><td>Tabloda Yer Alan Ekalan Bilgileri</td></tr><tr><td>created_in</td><td>datetime</td><td>Kaydedilme tarihi</td></tr><tr><td>updated_in</td><td>datetime</td><td>Güncellenme tarihi</td></tr></tbody></table>

=== "200"
    ```
    {
        "status": true,
        "data": [        
        {
                        {
                "id": "8095",
                "customer_id": null,
                "customer_vkn": null,
                "transaction_id": "8095",
                "bank_id": "56",
                "transaction_code": "EFT",
                "category": "debit_havale",
                "transfer_account": "",
                "account_iban": "TR360004600632888000388872",
                "erp_status": "",
                "erp_response": "",
                "erp_transferred_bank": "681",
                "erp_transferred_bank2": null,
                "customer_data1": null,
                "customer_data2": null,
                "transaction_description": "632/OPM-EFT HAVALE ÜCRETİ",
                "space1": null,
                "space3": "",
                "space4": null,
                "space5": null,
                "created_in": "2025-08-01 14:54:35",
                "updated_in": "2025-08-01 14:54:35",
                "salesman": null,
                "cost_code": null,
                "project_code": null,
                "material_code": null,
                "branch_id": null,
                "currency": null,
                "currency_amount": null,
                "account_code": "150902"
            }
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