---
description: >-
  Fatura kaydetme işlemi için kullanılan endpoint ve http metod bilgisi aşağıda
  verilmiştir
---

# Fatura Kaydetme&#x20;

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="175.3097476496784">HTTP Metod</th><th width="614.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="https://www.siteadi.com/api/v1/payment/payment_create"><mark style="color:red;">https://www.siteadi.com/api/v1/</mark></a><mark style="color:red;">invoice/invoice_create</mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Fatura kaydetme  işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

<pre><code>{
<strong>            "customer_id": "1", 
</strong>            "status": "1", 
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
            "invoice_created_in": "2023-10-01 19:30:00",
            "invoice_updated_in": "2023-10-01 19:30:00", 
            "invoice_date": "2023-10-06",
            "invoice_time": "19:00:00"
}
</code></pre>

## Fatura Kaydetme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/invoice/invoice_create`

Ödüyo içerisine gönderilen fatura işlemlerini kaydeder.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                           | Type             | Description               |
| ---------------------------------------------- | ---------------- | ------------------------- |
| sku<mark style="color:red;">\*</mark>          | string           | cari hesap kodu           |
| tax\_office<mark style="color:red;">\*</mark>  | string           | Cari vergi dairesi        |
| tax\_number<mark style="color:red;">\*</mark>  | string           | Cari vegi no              |
| document\_no<mark style="color:red;">\*</mark> | string           | Belge no                  |
| invoice\_no                                    | string           | Fatura no                 |
| erp\_ref\_id                                   | numeric(int)     | Erp id                    |
| title<mark style="color:red;">\*</mark>        | string           | Cari unvan                |
| status<mark style="color:red;">\*</mark>       | numeric(int)     | Fatura durumu(0-1)        |
| customer\_id                                   | numeric(int)     | Ödüyo cari id             |
| invoice\_type                                  | string           | Fatura tipi               |
| payment\_type                                  | string           | Ödeme türü                |
| invoice\_currency                              | string           | Fatura para birimi        |
| total                                          | numerik(decimal) | Fatura tutarı             |
| branch\_id                                     | numeric(int)     | Erp şube id               |
| branch\_name                                   | string           | Erp şube                  |
| storage\_id                                    | string           | Erp malzeme id            |
| storage\_name                                  | string           | Erp malzeme adı           |
| currency\_type                                 | string           | Para birimi               |
| currency\_value                                | numerik(decimal) | İşlem sonucu              |
| parent\_process                                | string           | Üst işlem id              |
| parent\_process\_txt                           | string           | Üst işlem detayı          |
| note                                           | text             | Açıklama                  |
| invoice\_address                               | text             | Adres                     |
| invoce\_created\_in                            | datetime         | Fatura oluşturulma tarihi |
| invoce\_updated\_in                            | datetime         | Fatura güncellenme tarihi |
| invoice\_date                                  | datetime         | Fatura tarihi             |
| invoice\_time                                  | datetime         | Fatura saati              |

=== "200 Başarılı"
	```javascript
	{
    "status": true,
    "data": "Payment successfully added id <id>"
	}
	```

=== "400: Bad Request Hatalı"
	```
	{
	}
	```
!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.