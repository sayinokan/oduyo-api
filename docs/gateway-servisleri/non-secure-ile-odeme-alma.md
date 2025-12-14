---
description: >-
  Ödeme ile ilgili bilgiler tek sorguda gönderilerek olumlu(ödeme alındı) yada
  olumsuz (ödeme alınamadı) sonuç alınır.
---

# Non-Secure ile Ödeme Alma

### <mark style="color:blue;">URL</mark>

Non-Secure Ödeme Alma için kullanılan endpoint ve http metod bilgisi aşağıda yer aldığı gibidir.

<table><thead><tr><th width="150">HTTP Metod</th><th width="523.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="https://www.siteadi.com/api/v1/payment/payment_update"><mark style="color:red;"><code>https://www.siteadi.com/api/v1/</code></mark></a><mark style="color:red;"><code>gateway/payment</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İstek Parametreleri</mark> <a href="#url" id="url"></a>

Çekim işlemleri güncelleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

<table><thead><tr><th width="163">Parametre Adı</th><th width="95">Tipi</th><th width="79">Zorunlu</th><th>Açıklama</th></tr></thead><tbody><tr><td>pos_alias</td><td>string</td><td>Hayır</td><td>Çekim işleminin yapılacağı pos kimliği. Gönderilmemesi durumunda Yönetim Panelinde yer alan veriler kullanılarak Akıllı Pos Yönlendirme özelliği ile en uygun pos üzerinden çekim işlemi yapılacaktır.</td></tr><tr><td>card_brand</td><td>decimal</td><td>Hayır</td><td>Çekim işleminin yapılacağı pos'un kart ailesi bilgisidir. Bankaya ait bir pos_alias gönderildiğinde bu parametrenin gönderilmesine gerek yoktur. Ödeme kuruluşuna ait pos_alias gönderildiğinde, birden fazla kart ailesi kayıtlı olması durumunda card_brand parametresi gönderilerek hangi kart ailesinden çekim yapılacağı seçilebilir. Ödeme kuruluşu pos_alias gönderilmesine rağmen card_brand gönderilmemişse en düşük komisyonlu card_brand üzerinden işlem sağlanır.</td></tr><tr><td>price</td><td>decimal</td><td>Evet</td><td>Sepet tutari. item parametresi altında yer alan tutarların toplamı ile eşit olmalıdır.</td></tr><tr><td>paid_price</td><td>decimal</td><td>Evet</td><td>Komisyon ve vade farkı gibi tutarlar Sepet tutarına dahil edilerek gönderilmesi gereken nihai çekim tutarıdır.</td></tr></tbody></table>
