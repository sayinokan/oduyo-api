---
description: >-
  3D Secure ile yapılan ödemelerin tamamlanabilmesi için 2 endpoint'e istek
  atılması gerekmektedir.
---

# 3D Secure ile Ödeme Onaylama

• 3d Secure Ödeme Başlatma

• 3d Secure Ödeme Onaylama

Bu iki adımda gönderilen isteklerden herhangi birinde sorun olması durumunda ödeme tamamlanmayacaktır.&#x20;

\
\*3d Secure Ödeme Başlatma\* adımda ödeme işlemi başlatılarak çekim işlemi hazır duruma getirilir.

\*3d Secure Ödeme Onaylama\* adımında ise ilk adımda başlatılan işlem onaylanarak ücretin tahsil edilmesi sağlanır.

### <mark style="color:blue;">URL</mark>

3d Secure Ödeme Onaylama için kullanılan endpoint ve http metod bilgisi aşağıda yer aldığı gibidir.

<table><thead><tr><th width="150">HTTP Metod</th><th width="426.4285714285714">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="#url"><mark style="color:red;"><code>https://www.siteadi.com/api/v1/gateway/payment_3d_complete</code></mark></a></td></tr></tbody></table>

### <mark style="color:blue;">İstek Parametreleri</mark>

İptal ve iade edilen çekim işlemlerinin listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

<table><thead><tr><th width="170">Parametre Adı</th><th width="104">Tipi</th><th width="86">Zorunlu</th><th>Açıklama</th></tr></thead><tbody><tr><td>payment_id</td><td>integer</td><td>Evet</td><td>Daha önce başlatılan ödemeden elde edilen payment_id bilgisidir.</td></tr></tbody></table>

### <mark style="color:blue;">Sonuç Parametreleri</mark>

Ödeme Onaylama işlemine ait detaylar data parametresi altında dizi olarak dönülmektedir.



<table><thead><tr><th width="207">Parametre Adı</th><th width="117">Tipi</th><th>Açıklama</th></tr></thead><tbody><tr><td>result</td><td>boolean</td><td><p></p><p>İşlem durumu<br></p></td></tr><tr><td>payment_id</td><td>integer</td><td>Ödeme işleminin benzersiz id'si.</td></tr><tr><td>message</td><td>string</td><td>İşlem durumu açıklaması.</td></tr><tr><td>installment_count</td><td>integer</td><td>Taksit Sayısı</td></tr><tr><td>order_id</td><td>string</td><td>Ödeme işlemi sipariş numarası</td></tr><tr><td>auth_code</td><td>string</td><td>Banka işlem numarası</td></tr></tbody></table>