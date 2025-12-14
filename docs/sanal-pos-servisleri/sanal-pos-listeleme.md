---
description: >-
  Sanal Pos listeleme işlemi için kullanılan endpoint ve http metod bilgisi
  aşağıda verilmiştir.
---

# Sanal Pos Listeleme

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="515.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;">https://www.siteadi.com/api/v1/bank_list/bank_list_select</mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark> <a href="#url" id="url"></a>

Kayıtlı Sanal Pos listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

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

## Sanal Pos Listeleme.

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/bank_list/bank_list_select`

Ödüyo içerisindeki carileri listeler.

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
            "bank_id": "1",
            "name": "Garanti",
            "image": "",
            "method": "gvp",
            "model": "3d_pay",
            "info": "{\"bank_id\":\"1\",\"card_type\":[],\"gvp_terminal_id\":\"30691297\",\"gvp_merchant_id\":\"7000679\",\"gvp_user_name\":\"PROVAUT\",\"gvp_provaut_password\":\"123qweASD\\/\",\"gvp_3D_storekey\":\"12345678\",\"gvp_classic_url\":\"https:\\/\\/sanalposprovtest.garanti.com.tr\\/VPServlet\",\"gvp_3D_url\":\"https:\\/\\/sanalposprovtest.garanti.com.tr\\/servlet\\/gt3dengine\",\"gvp_bayi_sanalpos_id\":\"\",\"gvp_single_installment\":0,\"gvp_doviz_active\":0,\"gvp_campaignchooselink\":0,\"instalment_1\":\"0\",\"instalment_2\":\"0\",\"instalment_3\":\"2.3\",\"instalment_4\":\"3.4\",\"instalment_5\":\"5.6\",\"instalment_6\":\"6\",\"instalment_7\":\"7\",\"instalment_8\":\"8\",\"instalmentamount_1\":\"0\",\"instalmentamount_2\":\"0\",\"instalmentamount_3\":\"0\",\"instalmentamount_4\":\"0\",\"instalmentamount_5\":\"0\",\"instalmentamount_6\":\"0\",\"instalmentamount_7\":\"0\",\"instalmentamount_8\":\"0\",\"instalment\":\"1=0;2=0;3=2.3;4=3.4;5=5.6;6=6;7=7;8=8;\",\"instalment_araci\":\"\",\"instalmentamount_araci\":\"\",\"instalmentplus\":\"\",\"plus_inst_price\":0,\"installmentsamount\":\"1=0;2=0;3=0;4=0;5=0;6=0;7=0;8=0;\",\"customer_group\":[]}",
            "status": "1",
            "bank_code": "garanti",
            "default_bank": "1",
            "table_update_userlog": null,
            "oduyo_firma_id": null
        },      
	]
	}
	```
	
===	"401 Hatalı"
	```
	{
	}
	```
	
!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.

### <mark style="color:blue;">Sonuç Parametreleri</mark>

<table><thead><tr><th width="211.78468802907685">Tag</th><th width="170.38403041825097">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td>bank_id</td><td>Tablo Pk İd</td><td><strong>Numerik(int)</strong></td></tr><tr><td>name</td><td>Banka Adı</td><td><strong>String</strong></td></tr><tr><td>image</td><td>Banka Logosu</td><td><strong>String</strong></td></tr><tr><td>method</td><td>Pos Türü</td><td><strong>String</strong></td></tr><tr><td>model</td><td>Pos Modeli</td><td><strong>String</strong></td></tr><tr><td>info</td><td>Pos Bilgileri</td><td><p><strong>'bank_block_day_1'=>'Bloke gün sayısı',</strong></p><p><strong>'bank_expiry_day_1'=>'Diğer kartlar için bloke gün sayısı'</strong></p></td></tr><tr><td>status</td><td>Pos Durumu</td><td><strong>'Aktif'=>'1',    'Pasif'=>'2',</strong>    </td></tr><tr><td>bank_code</td><td>Banka Kodu</td><td><strong>String</strong></td></tr><tr><td>default_bank</td><td>Varsayılan Pos</td><td><strong>Numerik(int)</strong></td></tr><tr><td>table_update_userlog</td><td></td><td><strong>Text</strong></td></tr><tr><td>oduyo_firma_id</td><td>Tanımlı Sunucu İd</td><td><strong>String</strong></td></tr></tbody></table>
