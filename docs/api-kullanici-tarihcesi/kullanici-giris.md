---
description: >-
  Kullanıcı giriş tarihçesi listeleme işlemi için kullanılan endpoint ve http
  metod bilgisi aşağıda verilmiştir.
---

# Kullanıcı Giriş

### <mark style="color:blue;">URL</mark>

<table><thead><tr><th width="150">HTTP Metod</th><th width="579.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/user_login_history/user_login_history_list</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İşlem Parametreleri</mark>

Kullanıcı giriş tarihçesi listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

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

## Kullanıcı Giriş Tarihçesi Listeleme

<mark style="color:green;">`POST`</mark> `https://www.siteadi.com/api/v1/user_login_history/user_login_history_list`

Ödüyo içerisindeki kullanıcıların giriş tarihçesini listeler.

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
            "customer_id": "4",
            "ip_address": "127.0.0.1",
            "user_agent": "Chrome 127.0.1.107 - Linux",
            "username": "test",
            "status": "0",
            "space1": "",
            "space2": "",
            "space3": "",
            "space4": "",
            "space5": "",
            "created_in": "2021-09-07 23:18:48",
            "updated_in": "2021-09-07 23:19:05"
        }
	}       
	```

===	"400: Bad Request Hatalı"
	```
	{
	}
	```
	
!!! info
	**Önemli:** Header içerisinde mutlaka Apikey ve Session ID bilgisi gönderilmelidir.

### <mark style="color:blue;">Sonuç Parametreleri</mark>

| Tag          | Açıklama                         | Format                                   |
| ------------ | -------------------------------- | ---------------------------------------- |
| id           | İşlem Numarası                   | <p><strong>Numerik(int)</strong><br></p> |
| customer\_id | Kullanıcı İd                     | <p><strong>Numerik(int)</strong><br></p> |
| ip\_address  | İp Adresi                        | String                                   |
| user\_agent  | Kullanıcının Giriş Yaptığı Cihaz | String                                   |
| username     | Kullanıcı Adı                    | **String**                               |
| status       | Aktiflik Durumu                  | **String**                               |
| space1       | Ekalan                           | **String**                               |
| space2       | Ekalan                           | **String**                               |
| space3       | Ekalan                           | **String**                               |
| space4       | Ekalan                           | **String**                               |
| space5       | Ekalan                           | **String**                               |
| created\_in  | Veri Kayıt Tarihi                | **Date**                                 |
| updated\_in  | Veri Güncellenme Tarihi          | **Date**                                 |
