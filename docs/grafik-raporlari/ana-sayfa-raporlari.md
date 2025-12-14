---
description: >-
  Ana Sayfa Raporları Listeleme işlemi için kullanılan endpoint ve http metod
  bilgisi aşağıda verilmiştir
---

# Ana Sayfa Raporları

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="565.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/dashboard_list_data/dashboard_list</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İstek</mark> <mark style="color:blue;">Parametreleri</mark>

Ana sayfa raporları listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

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

## Ana Sayfa Raporları Listeleme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/dashboard_list_data/dashboard_list`

Ödüyo içerisindeki anasayfa grafiklerindeki içerikleri listeler.

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

=== "200 Başarılı"
	```javascript
	{
    "status": true,
    "data": [
        {
            "id": "1",
            "bankTypePaymentData": "{\"TL\":\"[{\\\"islem_banka\\\":\\\"garanti\\\",\\\"islem_sayisi\\\":\\\"9\\\",\\\"toplam_odeme\\\":\\\"107265.0000\\\"},{\\\"islem_banka\\\":\\\"vakifkatilim\\\",\\\"islem_sayisi\\\":\\\"1\\\",\\\"toplam_odeme\\\":\\\"239889.0000\\\"}]\",\"USD\":null,\"EUR\":null,\"GBP\":null,\"RUB\":null,\"JPY\":null,\"ALL\":\"[{\\\"islem_banka\\\":\\\"garanti\\\",\\\"islem_sayisi\\\":\\\"9\\\",\\\"toplam_odeme\\\":\\\"107265\\\"},{\\\"islem_banka\\\":\\\"vakifkatilim\\\",\\\"islem_sayisi\\\":\\\"1\\\",\\\"toplam_odeme\\\":\\\"239889\\\"}]\"}",
            "cardTypePaymentData": "{\"TL\":\"[{\\\"card_turu\\\":\\\"bonus\\\",\\\"islem_sayisi\\\":\\\"10\\\",\\\"toplam_odeme\\\":\\\"347154.0000\\\"}]\",\"USD\":null,\"EUR\":null,\"GBP\":null,\"RUB\":null,\"JPY\":null,\"ALL\":\"[{\\\"card_turu\\\":\\\"bonus\\\",\\\"islem_sayisi\\\":\\\"10\\\",\\\"toplam_odeme\\\":\\\"347154\\\"}]\"}",
            "topTen":"[{\"adsoyadm\":\"h\üseyin kele\ş kele\ş\",\"islem_sayisi\":\"1\",\"toplam\":\"239889\"},{\"adsoyadm\":\"ALTENA LAST\İK SAN.VE T\İC.LTD.\ŞT\İ.\",\"islem_sayisi\":\"6\",\"toplam\":\"107262\"},{\"adsoyadm\":\"xcxcvxcvxc\",\"islem_sayisi\":\"1\",\"toplam\":\"1\"},{\"adsoyadm\":\"fdss\",\"islem_sayisi\":\"1\",\"toplam\":\"1\"},{\"adsoyadm\":\"sddsfds\",\"islem_sayisi\":\"1\",\"toplam\":\"1\"}]",
            "installmentFee": "[{\"islem_banka\":\"garanti\",\"komisyon\":\"0\"},{\"islem_banka\":\"vakifkatilim\",\"komisyon\":\"0\"}]",
            "mail_sms_other_payment": "{\"mail_payment\":\"[{\\\"islem_sayisi\\\":\\\"1\\\",\\\"mail_odemeleri\\\":\\\"239889\\\",\\\"MONTH\\\":\\\"2021-08\\\"},{\\\"islem_sayisi\\\":\\\"1\\\",\\\"mail_odemeleri\\\":\\\"17877\\\",\\\"MONTH\\\":\\\"2021-09\\\"}]\",\"sms_payment\":null,\"all_payment\":\"[{\\\"islem_sayisi\\\":\\\"1\\\",\\\"tum_odemeler\\\":\\\"239889\\\",\\\"MONTH\\\":\\\"2021-08\\\"},{\\\"islem_sayisi\\\":\\\"6\\\",\\\"tum_odemeler\\\":\\\"107262\\\",\\\"MONTH\\\":\\\"2021-09\\\"},{\\\"islem_sayisi\\\":\\\"3\\\",\\\"tum_odemeler\\\":\\\"3\\\",\\\"MONTH\\\":\\\"2021-11\\\"}]\"}",
            "today_payment_success": "{\"TL\":{\"today_total_payment_success\":null,\"basari_sayisi\":\"0\"},\"USD\":{\"today_total_payment_success\":null,\"basari_sayisi\":\"0\"},\"EUR\":{\"today_total_payment_success\":null,\"basari_sayisi\":\"0\"},\"GBP\":{\"today_total_payment_success\":null,\"basari_sayisi\":\"0\"},\"RUB\":{\"today_total_payment_success\":null,\"basari_sayisi\":\"0\"},\"JPY\":{\"today_total_payment_success\":null,\"basari_sayisi\":\"0\"},\"total\":{\"today_total_payment_success\":null,\"basari_sayisi\":\"0\"}}",
            "today_payment_error": "{\"TL\":{\"today_total_payment_error\":null,\"hata_sayisi\":\"0\"},\"USD\":{\"today_total_payment_error\":null,\"hata_sayisi\":\"0\"},\"EUR\":{\"today_total_payment_error\":null,\"hata_sayisi\":\"0\"},\"GBP\":{\"today_total_payment_error\":null,\"hata_sayisi\":\"0\"},\"RUB\":{\"today_total_payment_error\":null,\"hata_sayisi\":\"0\"},\"JPY\":{\"today_total_payment_error\":null,\"hata_sayisi\":\"0\"},\"total\":{\"today_total_payment_error\":null,\"hata_sayisi\":\"0\"}}",
            "today_payment_success_chart": "[]",
            "today_serbest_payment": null,
            "today_mail_payment": null,
            "payment_success_chart": "[{\"date\":\"2021-08-27\",\"total\":\"239889.00\"},{\"date\":\"2021-09-03\",\"total\":\"107262.00\"},{\"date\":\"2021-11-21\",\"total\":\"3.00\"}]",
            "week_success_payment": "{\"week_success_payment\":null,\"basari_sayisi\":\"0\"}",
            "week_error_payment": "{\"week_error_payment\":null,\"hata_sayisi\":\"0\"}",
            "week_serbest_payment": null,
            "week_mail_payment": null,
            "month_payment_success": "{\"month_payment_success\":null,\"basari_sayisi\":\"0\"}",
            "month_payment_error": "{\"month_payment_error\":null,\"hata_sayisi\":\"0\"}",
            "month_serbest_payment": "{\"month_payment_success\":null,\"basari_sayisi\":\"0\"}",
            "month_mail_payment": "{\"month_payment_success\":null,\"basari_sayisi\":\"0\"}",
            "year_payment_success": "{\"year_payment_success\":null,\"basari_sayisi\":\"0\"}",
            "year_serbest_payment": "{\"year_payment_success\":null,\"basari_sayisi\":\"0\"}",
            "year_mail_payment": "{\"year_payment_success\":null,\"basari_sayisi\":\"0\"}",
            "year_payment_error": "{\"year_payment_error\":null,\"hata_sayisi\":\"0\"}",
            "total_payment": "347154",
            "total_payment_error_succes": "{\"total_payment_success\":\"347154\",\"basari_sayisi\":\"61\",\"total_payment_error\":\"0.000\",\"hata_sayisi\":\"0\"}",
            "general_detail_in_page": "[]",
            "general_detail_in_page_formonth": "[]",
            "general_detail_in_page_forday": "[{\"doviz_tur\":\"TL\"}]",
            "table_update_userlog": null,
            "created_in": "2022-04-25 12:15:44",
            "updated_in": "2022-04-25 12:15:44"
        }
    ]
	}
	```

=== "400: Bad Request Hatalı"
	```
	{
	}
	```

!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.

### <mark style="color:blue;">Sonuç Parametreleri</mark>

<table><thead><tr><th width="313.4477619113817">Tag</th><th width="220.9803073261785">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td><code>İd</code></td><td>İşlem numarası</td><td><strong>Numerik(int)</strong></td></tr><tr><td>bankTypePaymentData</td><td>Banka Türü Ödeme Verileri</td><td><strong>String</strong></td></tr><tr><td>cardTypePaymentData</td><td>Kart Türü Ödeme Verileri</td><td><strong>String</strong></td></tr><tr><td>topTen</td><td>En Fazla Ödeme Yapan Cari Verileri</td><td><strong>String</strong></td></tr><tr><td>installmentFee</td><td>Pos Bazında Ödemeler</td><td><strong>String</strong></td></tr><tr><td>mail_sms_other_payment</td><td>Aylık Toplam Ödeme Tutarları</td><td><strong>String</strong></td></tr><tr><td>today_payment_success</td><td>Bugün Yapılan Başarılı Çekimler</td><td><strong>String</strong></td></tr><tr><td>today_payment_error</td><td>Bugün Yapılan Hatalı Çekimler</td><td><strong>String</strong></td></tr><tr><td>today_payment_success_chart</td><td>Bugün Yapılan Başarılı Çekimler Grafiği</td><td><strong>String</strong></td></tr><tr><td>today_serbest_payment</td><td>Bugün Yapılan Serbest Çekimler</td><td><strong>String</strong></td></tr><tr><td>today_mail_payment</td><td></td><td><strong>String</strong></td></tr><tr><td>payment_success_chart</td><td>Başarılı Çekim Grafiği</td><td><strong>String</strong></td></tr><tr><td>week_success_payment</td><td>Haftalık Başarılı Çekimler</td><td><strong>String</strong></td></tr><tr><td>week_error_payment</td><td>Haftalık Hatalı Çekimler</td><td><strong>String</strong></td></tr><tr><td>week_serbest_payment</td><td>Haftalık Yapılan Serbest Çekimler</td><td><strong>String</strong></td></tr><tr><td>week_mail_payment</td><td></td><td><strong>String</strong></td></tr><tr><td>month_payment_success</td><td>Aylık Başarılı Çekimler</td><td><strong>String</strong></td></tr><tr><td>month_payment_error</td><td>Aylık Hatalı Çekimler</td><td><strong>String</strong></td></tr><tr><td>month_serbest_payment</td><td>Aylık Yapılan Serbest Çekimler</td><td><strong>String</strong></td></tr><tr><td>month_mail_payment</td><td></td><td><strong>String</strong></td></tr><tr><td>year_payment_success</td><td>Yıllık Yapılan Başarılı Çekimler</td><td><strong>String</strong></td></tr><tr><td>year_serbest_payment</td><td>Yıllık Yapılan Serbest Çekimler</td><td><strong>String</strong></td></tr><tr><td>year_mail_payment</td><td></td><td><strong>String</strong></td></tr><tr><td>year_payment_error</td><td>Yıllık Hatalı Çekimler</td><td><strong>String</strong></td></tr><tr><td>total_payment</td><td>Toplam Çekim</td><td><strong>String</strong></td></tr><tr><td>total_payment_error_succes</td><td>Toplam </td><td><strong>String</strong></td></tr><tr><td>general_detail_in_page</td><td></td><td><strong>String</strong></td></tr><tr><td>general_detail_in_page_formonth</td><td></td><td><strong>String</strong></td></tr><tr><td>general_detail_in_page_forday</td><td></td><td><strong>String</strong></td></tr><tr><td>oduyo_firma_id</td><td>Firma işlem numarası</td><td><strong>String</strong></td></tr><tr><td>table_update_userlog</td><td>Tabloyu Güncelleyen Kullanıcı Log Bilgisi</td><td><strong>String</strong></td></tr><tr><td>created_in</td><td>Veri Kayıt Tarihi</td><td><strong>Date</strong></td></tr><tr><td>updated_in</td><td>Veri Güncellenme Tarihi</td><td><strong>Date</strong></td></tr></tbody></table>