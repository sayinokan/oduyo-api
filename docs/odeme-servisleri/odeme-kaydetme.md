---
description: >-
  Çekim işlemleri kaydetme işlemi için kullanılan endpoint ve http metod bilgisi
  aşağıda verilmiştir
---

# Ödeme Kaydetme&#x20;

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="175.3097476496784">HTTP Metod</th><th width="614.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="https://www.siteadi.com/api/v1/payment/payment_create"><mark style="color:red;"><code>https://www.siteadi.com/api/v1/payment/payment_create</code></mark></a></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Çekim işlemleri listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
"column":{ 
"paymentsend_id":"1",
"collection_email":"1", 
"collection_sms":"1", 
"period_order":"1", 
"email":test@oduyo.com.tr", 
"card_type1":"bonus", 
"card_type2":"mastercard", 
"name_surname":"test", 
"comment":"test", 
"firm_id":"1", 
"customer_id":"1", 
"orderid":"1", 
"installment_number":"1", 
"plus_installment":"1",
"status":"3D-POST", 
"masked_card":"5529******819", 
"total_with_commison":"1.000", 
"total_without_commison":"1.000", 
"currency_type":"tl", 
"transaction_data":"test", 
"transaction_bank":"garanti", 
"transaction_type":"2", 
"partial":"", 
"card_name_surname":"test", 
"phone_number":"5454445544", 
"post_code":"34000", 
"city":"İstanbul", 
"district":"Kadıköy", 
"country":"Türkiye", 
"payment_type":"3d", 
"member_code":"", 
"payment_note":"test", 
"payment_address":"test", 
"erp_order_ids":"", 
"erp_status":"success", 
"erp_status_msg":"", 
"id_number":"", 
"tax_number":"", 
"payment_ip":"127.0.0.1", 
"space1":"", 
"space2":"", 
"space3":"", 
"space4":"", 
"space5":"", 
"space6":"", 
"space7":"", 
"pos_id":"" 
}
}
```

## Ödeme Kaydetme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/payment/payment_create`

Ödüyo içerisine gönderilen çekim işlemlerini kaydeder.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                                | Type             | Description                                |
| --------------------------------------------------- | ---------------- | ------------------------------------------ |
| period\_order<mark style="color:red;">\*</mark>     | numeric(int)     | Periyodik ödeme                            |
| email<mark style="color:red;">\*</mark>             | string           | Müşteri  e-posta adresi                    |
| card\_type1<mark style="color:red;">\*</mark>       | string           | Kredi kart türü (Bonus)                    |
| card\_type2<mark style="color:red;">\*</mark>       | string           | Kredi kart türü (Master)                   |
| card\_name\_surname                                 | string           | Kart Üzerindeki İsim                       |
| comment                                             | string           | Açıklama                                   |
| collection\_sms<mark style="color:red;">\*</mark>   | numeric(int)     | Tahsilat makbuzu sms gönderimi             |
| collection\_email<mark style="color:red;">\*</mark> | numeric(int)     | Tahsilat makbuzu e-mail gönderimi          |
| paymentsend\_id                                     | numeric(int)     | Ödeme gönderim numarası                    |
| customer\_id                                        | numeric(int)     | Ödeme yapan müşteri için tutulan pk id     |
| orderid                                             | string           | Sipariş numarası                           |
| installment\_number                                 | string           | Taksit sayısı                              |
| plus\_installment                                   | string           | Artı taksit sayısı                         |
| status                                              | string           | Ödeme durumu                               |
| masked\_card                                        | string           | Kart numarası                              |
| total\_with\_commison                               | numeric(decimal) | Komisyonlu toplam tutar                    |
| total\_without\_commison                            | numericdecimal)  | Komisyonsuz toplam tutar                   |
| currency\_type                                      | string           | Para birimi                                |
| transaction\_data                                   | string           | İşlem sonucu                               |
| transaction\_bank                                   | string           | İşlem yapılan banka                        |
| transaction\_type                                   | string           | İşlem tipi                                 |
| name\_surname                                       | string           | Ödeme yapan müşteri bilgisi                |
| phone\_number                                       | string           | Müşteri Telefon no                         |
| post\_code                                          | string           | Posta kodu                                 |
| city                                                | string           | Şehir                                      |
| district                                            | string           | İlçe                                       |
| country                                             | string           | Ülke                                       |
| payment\_type                                       | string           | Ödeme tipi                                 |
| member\_code                                        | string           | Üye kodu                                   |
| payment\_note                                       | string           | Ödeme notu                                 |
| payment\_address                                    | string           | Ödeme adresi                               |
| erp\_order\_ids                                     | string           | Erp sipariş numarası                       |
| erp\_status                                         | string           | Erp aktarılma durumu                       |
| erp\_status\_msg                                    | string           | Erp aktarım mesajı                         |
| id\_number                                          | string           | Tc no                                      |
| tax\_number                                         | string           | Vergi no                                   |
| payment\_ip                                         | string           | Ödeme yapılan İp adresi                    |
| space1                                              | string           | Tabloda yer alan ekalan bilgileri          |
| space2                                              | string           | Tabloda yer alan ekalan bilgileri          |
| space6                                              | string           | Tabloda yer alan ekalan bilgileri          |
| space3                                              | string           | Tabloda yer alan ekalan bilgileri          |
| space5                                              | string           | Tabloda yer alan ekalan bilgileri          |
| space4<mark style="color:red;">\*</mark>            | string           | Bankadan gelen sonuç logu                  |
| space7                                              | string           | Tabloda yer alan ekalan bilgileri          |
| pos\_id<mark style="color:red;">\*</mark>           | string           | Çekim yapılan sanal pos için tutulan pk id |

=== "200 Başarılı"

	```json
	{
    "status": true,
    "data": "Payment successfully added id <id>"
	}
	```

=== "400: Bad Request Hatalı"

	```json
	{
	"status": false,
	"error": "Bad Request"
	}
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.