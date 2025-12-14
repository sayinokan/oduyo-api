---
description: >-
  Sipariş listeleme işlemi için kullanılan endpoint ve http metod bilgisi
  aşağıda verilmiştir.
---

# Sipariş Listeleme

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="426.4285714285714">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="#url"><mark style="color:red;"><code>https://www.siteadi.com/api/v1</code></mark></a><mark style="color:red;"><code>/order/order_list</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İstek Parametreleri</mark>

Sipariş listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

```
{
    "filters":"",
    "params" :"",
    "limit":"1000",
    "offset" : "0",
    "sorting":[{"field": "id", "sort": "ASC"}]
}
```

!!! info
	Body içerisinde gönderilen alanlarla ilgili detayları görmek için [tıklayınız.](../../../filtreleme-parametreleri)

## Sipariş Listeleme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/invoice/invoice_list`

Ödüyo içerisindeki sipariş işlemlerini listeler.

#### Headers

| Name                                            | Type   | Description                                                                           |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| Apikey<mark style="color:red;">\*</mark>        | String | Ödüyo paneli içerinde APIKEY bölümünden alınmalıdır.                                  |
| Authorization<mark style="color:red;">\*</mark> | String | Kullanıcı denetimi bölümünde anlatılan Login servisi ile üretilmelidir. (SESSION\_ID) |

#### Request Body

| Name                                     | Type   | Description          |
| ---------------------------------------- | ------ | -------------------- |
| filters                                  | string | Filtreleme alanıdır. |
| params                                   | string | Parametre alanıdır.  |
| limit<mark style="color:red;">\*</mark>  | string | Sorgu limiti.        |
| offset<mark style="color:red;">\*</mark> | string | Sayfalama            |
| sorting                                  | String | Sıralama             |

===	"200 Başarılı"
	```javascript
	{
    "status": true,
    "data": [
        {
            "customer_id": "1", //ödüyo cari id
            "status": "1", //fatura durumu 0-1
            "title": "Ödüyo Deneme Carisi", // cari ünvan
            "sku": "120.001.001", // cari hesap kodu
            "tax_office": "Kartal V.D.", //cari vergi dairesi
            "tax_number": "10000000146", //cari vergi numarası
            "identity_number": "10000000146", // tc-vkn kimlik numarası
            "document_no": "1999", //belge numarası
            "invoice_no": "A001", //fatura numarası
            "erp_ref_id": "5", //fatura erp tarafında mevcutsa erp id si
            "invoice_type": "Verilen Hizmet", // fatura tipi
            "payment_type": "Nakit", //ödeme türü 
            "invoice_currency": "TL", //fatura para birimi
            "average_expiry_date": "2023-10-06", // ortalama vade tarihi
            "total": "1.00", //toplam tutar
            "branch_id": "1",
            "branch_name": "Merkez",
            "storage_id": "1",
            "storage_name": "Ana Depo",
            "currency_type": "TL",
            "currency_value": "1.00",
            "parent_process": "0", //üst işlem id
            "parent_process_txt": "", // üst işlem detayı
            "note": "Açıklama", //fatura açıklama
            "invoice_address": "İstanbul merkez", //fatura adresi
            "invoce_created_in": "2023-10-01 19:30:00", //fatura oluşturulma tarihi
            "invoce_updated_in": "2023-10-01 19:30:00", //fatura güncelleme tarihi
            "invoice_date": "2023-10-06",
            "invoice_time": "19:00:00"
            
         }
	}
	```

===	"401 Hatalı"

	```
	{
	}
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir

### <mark style="color:blue;">Sonuç Parametreleri</mark>

Çekim işlemleri listeleme işlemi  için yapılan istek sonucunda alınması beklenen parametreler aşağıdaki tablo ve alt başlıklar altında listelenmiştir.

<table><thead><tr><th width="192.39507525927533">Tag</th><th width="264.07985888816484">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td>customer_id</td><td>Ödüyo cari id</td><td><strong>int</strong></td></tr><tr><td>status</td><td>Fatura durumu</td><td><p><strong>int("1"=Ödendi,</strong></p><p><strong>"0"=Ödenmedi)</strong></p></td></tr><tr><td>title</td><td>Cari ünvan</td><td><strong>String</strong></td></tr><tr><td>sku</td><td>Cari hesap kodu</td><td><strong>String</strong></td></tr><tr><td>order_status</td><td>cari vergi dairesi</td><td><strong>String</strong></td></tr><tr><td>tax_number</td><td>Cari vergi numarası</td><td><strong>String</strong></td></tr><tr><td>identity_number</td><td>Tc-vkn kimlik numarası</td><td><strong>String</strong></td></tr><tr><td>erp_red_id</td><td>Erp id</td><td><strong>İnt</strong></td></tr><tr><td>invoice_type</td><td>Fatura tipi</td><td><strong>String</strong></td></tr><tr><td>invoice_currency</td><td>Fatura para birimİ</td><td><strong>String</strong></td></tr><tr><td>average_expiry_date</td><td>Ortalama vade tarihi</td><td><strong>Date</strong></td></tr><tr><td>total</td><td>Fatura Tutar</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td>branch_id</td><td>Erp şube id</td><td><strong>İnt</strong></td></tr><tr><td>branch_name</td><td>Erp şube</td><td><strong>String</strong></td></tr><tr><td>storage_id</td><td>Erp malzeme id</td><td><strong>String</strong></td></tr><tr><td>storage_name</td><td>Erp malzeme adı</td><td><strong>String</strong></td></tr><tr><td>currency_type</td><td>Para birimi</td><td><strong>String</strong></td></tr><tr><td>currency_value</td><td>İşlem sonucu</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td>parent_process</td><td>Üst işlem id</td><td><strong>String</strong></td></tr><tr><td>parent_process_txt</td><td>Üst işlem detayı</td><td><strong>String</strong></td></tr><tr><td>invoice_address</td><td>Adres</td><td><strong>Text</strong></td></tr><tr><td>invoice_created_in</td><td>Fatura oluşturulma tarihi</td><td><strong>Datetime</strong></td></tr><tr><td>invoice_updated_in</td><td>Fatura güncellenme tarihi</td><td><strong>Datetime</strong></td></tr><tr><td>invoice_date</td><td>Fatura tarihi</td><td><strong>Datetime</strong></td></tr><tr><td>invoice_time</td><td>Fatura saati</td><td><strong>Datetime</strong></td></tr></tbody></table>


