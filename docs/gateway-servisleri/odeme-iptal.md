---
description: >-
  Ödeme İptal. Bu işlemde tutar belirtilmez, başanlı ödeme işleminin iptali
  sağlanır.
---

# Ödeme İptal

### <mark style="color:blue;">URL</mark>

Ödeme iptal işlemi için kullanılan endpoint ve http metod bilgisi aşağıda yer aldığı gibidir.



<table><thead><tr><th width="175.3097476496784">HTTP Metod</th><th width="614.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="https://www.siteadi.com/api/v1/payment/payment_create"><mark style="color:red;"><code>https://www.siteadi.com/api/v1/</code></mark></a><mark style="color:red;"><code>gateway/cancel</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İstek Parametreleri</mark> <a href="#url" id="url"></a>

<table><thead><tr><th width="178">Parametre Adı</th><th width="92">Tipi</th><th width="84">Zorunlu</th><th>Açıklama</th></tr></thead><tbody><tr><td>payment_id</td><td>integer</td><td>Evet</td><td>İptal etmek istediğiniz ödemeye ait benzersiz id</td></tr></tbody></table>

### <mark style="color:blue;">Dönüş Parametreleri</mark> <a href="#url" id="url"></a>

İptal işlemine ait bilgiler data parametresi altında dizi olarak dönülmektedir.

<table><thead><tr><th width="164">Parametre Adı</th><th width="114">Tipi</th><th>Açıklama</th></tr></thead><tbody><tr><td>result</td><td>boolean</td><td>İşlem durumunu gösterir true/false.</td></tr><tr><td>payment id</td><td>integer</td><td>İptal isteği gönderilen ödeme işleminin benzersiz id'si </td></tr><tr><td>message</td><td>string</td><td>İptal işlemi sonuç açıklaması.</td></tr><tr><td>order_id</td><td>string</td><td>İptal isteği gönderilen ödeme işleminin sipariş numarası</td></tr><tr><td>ref_no</td><td>string</td><td>İptal işleminin banka tarafındaki referans numarası</td></tr></tbody></table>