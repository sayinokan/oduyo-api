---
description: >-
  Fatura güncelleme işlemi için kullanılan endpoint ve http metod bilgisi
  aşağıda verilmiştir.
---

# Fatura Güncelleme

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="523.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="https://www.siteadi.com/api/v1/payment/payment_update"><mark style="color:red;"><code>https://www.siteadi.com/api/v1/</code></mark></a><mark style="color:red;"><code>invoice/invoice_update</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Fatura güncelleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
      "id":"5",
            "customer_id": "1", 
            "status": "1", 
            "title": "Ödüyo Test Carisi",
            "sku": "120.001.001", 
            "tax_office": 
            "tax_number": "10000000146", 
            "identity_number": "10000000146", 
            "document_no": "1999", 
            "invoice_no": "A001", 
            "erp_ref_id": "5", 
            "invoice_type": "Verilen Hizmet", 
            "payment_type": "Nakit", 
            "invoice_currency_type": "TL",
            "average_expiry_date": "2023-10-06", 
            "total": "1.00", 
            "branch_id": "1",
            "branch_name": "Merkez",
            "storage_id": "1",
            "storage_name": "Ana Depo",
            "currency_type": "TL",
            "currency_value": "1.00",
            "parent_process": "0", 
            "parent_process_txt": "", 
            "note": "Açıklama", 
            "invoice_address": "İstanbul merkez", 
            "invoce_created_in": "2023-10-01 19:30:00",
            "invoce_updated_in": "2023-10-01 19:30:00", 
            "invoice_date": "2023-10-06",
            "invoice_time": "19:00:00"
}
```

## Fatura Güncelleme&#x20;

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/invoice/invoice_update`

Ödüyo içerisine gönderilen fatura işlemlerini günceller.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                               | Type             | Description               |
| -------------------------------------------------- | ---------------- | ------------------------- |
| sku<mark style="color:red;">\*</mark>              | string           | Cari hesap kodu           |
| tax\_office<mark style="color:red;">\*</mark>      | string           | Cari vergi dairesi        |
| tax\_number<mark style="color:red;">\*</mark>      | string           | Cari vegi no              |
| identity\_number<mark style="color:red;">\*</mark> | string           | Tc-vkn kimlik numarası    |
| document\_no                                       | String           | Belge no                  |
| invoice\_no                                        | String           | Fatura no                 |
| title<mark style="color:red;">\*</mark>            | string           | Cari unvan                |
| status<mark style="color:red;">\*</mark>           | numeric(int)     | Fatura durumu(0-1)        |
| customer\_id                                       | numeric(int)     | Ödüyo cari id             |
| erp\_ref\_id                                       | numeric(int)     | Erp id                    |
| invoice\_type                                      | String           | Fatura tipi               |
| payment\_type                                      |                  | Ödeme türü                |
| invoice\_currency\_type                            |                  | Fatura para birimi        |
| average\_expiry\_date                              | date             | Ortalama vade tarihi      |
| total                                              | numeric(decimal) | Fatura tutarı             |
| branch\_id                                         | numeric(int)     | Erp şube id               |
| branch\_name                                       | numeric(decimal) | Erp şube                  |
| storage\_id                                        | string           | Erp malzeme id            |
| storage\_name                                      | string           | Erp malzeme adı           |
| currency\_type                                     | string           | Para birimi               |
| currency\_value                                    | Numerik(decimal) | İşlem sonucu              |
| parent\_process                                    | string           | Üst işlem id              |
| parent\_process\_txt                               | string           | Üst işlem detayı          |
| note                                               | text             | Açıklama                  |
| invoice\_address                                   | text             | Adres                     |
| invoice\_created\_in                               | datetime         | Fatura oluşturulma tarihi |
| invoice\_updated\_in                               | datetime         | Fatura güncellenme tarihi |
| invoice\_date                                      | datetime         | Fatura tarihi             |
| invoice\_time                                      | datetime         | Fatura saati              |
| id<mark style="color:red;">\*</mark>               | numeric(int)     | Güncellenecek satır id    |

=== "200 Başarılı"

	```javascript
	{
    "status": true,
    "data": "<id> Successfully updated"
	}
	```

=== "400: Bad Request Hatalı"
	
	```
	{
	}
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.					