---
description: >-
  İptal ve iade edilen çekim işlemlerinin listeleme işlemi için kullanılan
  endpoint ve http metod bilgisi aşağıda verilmiştir.
---

# İptal-İade İşlemleri Listeleme

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="426.4285714285714">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/payment_return/payment_return_select</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İstek Parametreleri</mark>

İptal ve iade edilen çekim işlemlerinin listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

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

## İptal-İade İşlemleri Listeleme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/payment_return/payment_return_select`

Ödüyo içerisindeki çekim işlemlerini listeler.

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
|                                          | String |                      |
|                                          | String |                      |

=== "200 Başarılı"

    ```json
    {
      "status": true,
      "data": [
        {
          "id": "1",
          "paymentsend_id": "FHoQQzMCxcz8Y4W20230224220554",
          "collection_email": "1",
          "collection_sms": "0",
          "period_order": "0",
          "email": "test@oduyo.com.tr",
          "card_type1": "maximum",
          "card_type2": "visa",
          "card_name_surname": "test test",
          "comment": "",
          "NULL": "",
          "customer_id": "371",
          "orderid": "44451c5a76",
          "installment_number": "",
          "plus_installment": "",
          "status": "3D-SUCCESS",
          "masked_card": "",
          "total_with_commison": "100.0000",
          "total_without_commison": "100.0000",
          "currency_type": null,
          "transaction_data": "İade talebiniz Sipay 'e iletilmiştir.\nİade Edilen Tutar:100,00 TL\nSipariş No:44451c5a76\nOrder No:167727279259684\nReferans No:305500060928\nİşlem Tarihi:2023-02-24 23:15:35",
          "transaction_bank": "Sipay",
          "transaction_type": "2",
          "partial": "",
          "name_surname": "bla bla",
          "phone_number": "",
          "post_code": "",
          "city": "-",
          "district": "-",
          "country": "-",
          "payment_type": "cancel",
          "member_code": "",
          "payment_note": "",
          "payment_address": "",
          "erp_order_ids": "",
          "erp_status": "success",
          "erp_status_msg": "{\"Code\":200,\"Data\":2078,\"Result\":true,\"msg\":null,\"fisno\":\"44451c5a76\"}",
          "id_number": "",
          "tax_number": "",
          "payment_ip": "127.0.0.1",
          "space1": "12/2026",
          "space2": "3a136752d4",
          "space3": "",
          "space4": "{\"status_code\":100,\"status_description\":\"Refund completed successfully\",\"order_no\":\"167727279259684\",\"invoice_id\":\"44451c5a76\",\"ref_no\":\"305500060928\",\"ref_number\":\"305500060928\"}",
          "space5": "",
          "space6": "",
          "pos_id": "16",
          "created_in": "2023-02-24 23:15:35",
          "updated_in": "2023-02-24 23:15:35"
        }
      ]
    }
    ```

=== "401 Hatalı"

    ```json
    {
      "status": false,
      "message": "Yetkisiz erişim"
    }
    ```

!!! info
    **Önemli:** Header içerisinde mutlaka `Apikey` ve `Session ID` bilgisi gönderilmelidir.


### <mark style="color:blue;">Sonuç Parametreleri</mark>

Çekim işlemleri listeleme işlemi  için yapılan istek sonucunda alınması beklenen parametreler aşağıdaki tablo ve alt başlıklar altında listelenmiştir.

<table><thead><tr><th width="192.39507525927533">Tag</th><th width="264.07985888816484">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td>id</td><td>Tablo Pk İd</td><td><strong>Numerik(int)</strong></td></tr><tr><td>paymentsend_id</td><td>Ödeme Gönderim Numarası</td><td><strong>String</strong></td></tr><tr><td>collection_email</td><td>Tahsilat Makbuzu E-mail Gönderimi</td><td><p><strong>int("1"=gönderildi,</strong></p><p><strong>"2"=gönderilmedi)</strong></p></td></tr><tr><td>collection_sms</td><td>Tahsilat Makbuzu Sms Gönderimi</td><td><p><strong>int("1"=gönderildi,</strong></p><p><strong>"2"=gönderilmedi)</strong></p></td></tr><tr><td>period_order</td><td>Periyot </td><td><strong>Numerik(int)</strong></td></tr><tr><td>email</td><td>Müşteri  E-posta Adresi</td><td><strong>String</strong></td></tr><tr><td>card_type1</td><td>Kart Türü</td><td><strong>"bonus",        "maksimum",</strong></td></tr><tr><td>card_type2</td><td>Kart Tipi</td><td><strong>"mastercard",                             "visa"</strong></td></tr><tr><td>name_surname</td><td>Kart Üzerindeki İsim</td><td><strong>String</strong></td></tr><tr><td>comment</td><td>Açıklama</td><td><strong>String</strong></td></tr><tr><td>customer_id</td><td>Ödeme Yapan Müşteri İçin Tutulan Pk İd</td><td><strong>String</strong></td></tr><tr><td>orderid</td><td>Sipariş Numarası</td><td><strong>String</strong></td></tr><tr><td>installment_number</td><td>Taksit Sayısı</td><td><strong>String</strong></td></tr><tr><td>plus_installment</td><td>Artı Taksit Sayısı</td><td><strong>String</strong></td></tr><tr><td>status</td><td>Ödeme Durumu</td><td><strong>"3D-SUCCESS"=Başarılı,                 "3D-ERROR"=Başarısız, "3-D POST"=Hatalı</strong></td></tr><tr><td>masked_card</td><td>Kart Numarası</td><td><strong>String</strong></td></tr><tr><td>total_with_commison</td><td>Komisyonlu Toplam Tutar</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td>total_without_commison</td><td>Komisyonsuz Toplam Tutar</td><td><strong>Numerik(decimal)</strong></td></tr><tr><td>currency_type</td><td>Para Birimi</td><td><strong>String</strong></td></tr><tr><td>transaction_data</td><td>İşlem Sonucu</td><td><strong>String</strong></td></tr><tr><td>transaction_bank</td><td>İşlem yapılan Banka</td><td><strong>String</strong></td></tr><tr><td>transaction_type</td><td>İşlem Tipi</td><td><strong>String</strong></td></tr><tr><td>partial</td><td></td><td><strong>String</strong></td></tr><tr><td>name_surname</td><td>Müşteri Bilgisi</td><td><strong>String</strong></td></tr><tr><td>phone_number</td><td>Müşteri Telefon Numarası</td><td><strong>String</strong></td></tr><tr><td>post_code"</td><td>Müşteri Posta Kodu</td><td><strong>String</strong></td></tr><tr><td>city</td><td>Şehir</td><td><strong>String</strong></td></tr><tr><td>district</td><td>Semt</td><td><strong>String</strong></td></tr><tr><td>country</td><td>Ülke</td><td><strong>String</strong></td></tr><tr><td>payment_type</td><td>Ödeme Tipi</td><td><strong>String</strong></td></tr><tr><td>member_code</td><td>Üye Kodu</td><td><strong>String</strong></td></tr><tr><td>payment_note</td><td>Ödeme Notu</td><td><strong>String</strong></td></tr><tr><td>payment_address</td><td>Ödeme Adresi</td><td><strong>String</strong></td></tr><tr><td>erp_order_ids</td><td>Erp Sipariş Numarası</td><td><strong>String</strong></td></tr><tr><td>erp_status</td><td>Erp Aktarılma Durumu</td><td><strong>"success"=aktarıldı, "error"=aktarılmadı,</strong> </td></tr><tr><td>erp_status_msg</td><td>Erp Aktarım Mesajı</td><td><strong>String</strong></td></tr><tr><td>id_number</td><td>T.C Numarası</td><td><strong>String</strong></td></tr><tr><td>tax_number</td><td>Vergi Numarası</td><td><strong>String</strong></td></tr><tr><td>payment_ip</td><td>Ödeme Yapılan İp Adresi</td><td><strong>String</strong></td></tr><tr><td>space1</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space2</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space3</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space4</td><td>Bankadan Gelen Sonuç Logu</td><td><strong>String</strong></td></tr><tr><td>space5</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space6</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>space7</td><td>Tabloda Yer Alan Ekalan Bilgileri</td><td><strong>String</strong></td></tr><tr><td>pos_id</td><td>Çekimin Yapıldığı Sanal Pos İçin Tutulan Pk İd</td><td><strong>String</strong></td></tr><tr><td>created_in</td><td>Tablo Ekleme Tarihi</td><td><strong>Date</strong></td></tr><tr><td>updated_in</td><td>Tablodaki Verinin Güncellendiği Tarih</td><td><strong>Date</strong></td></tr></tbody></table>
