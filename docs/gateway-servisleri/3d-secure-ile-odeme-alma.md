# 3D Secure İle Ödeme Alma

3D Secure ile yapılan ödemelerin tamamlanabilmesi için 2 endpoint'e istek atılması gerekmektedir.

* 3d Secure Ödeme Başlatma
* 3d Secure Ödeme Onaylama

Bu iki adımda gönderilen isteklerden herhangi birinde sorun olması durumunda ödeme tamamlanmayacaktır.&#x20;

\*3d Secure Ödeme Başlatma\* adımda ödeme işlemi başlatılarak çekim işlemi hazır duruma getirilir.

\*3d Secure Ödeme Onaylama\* adımında ise ilk adımda başlatılan işlem onaylanarak ücretin tahsil edilmesi sağlanır.



### <mark style="color:blue;">URL</mark>

3d Secure Ödeme Başlatma için kullanılan endpoint ve http metod bilgisi aşağıda yer aldığı gibidir.

<table><thead><tr><th width="150">HTTP Metod</th><th width="426.4285714285714">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><mark style="color:red;"><code>https://www.siteadi.com/api/v1/gateway/payment_3d</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İstek Parametreleri</mark>

Çekim işlemleri listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

<table><thead><tr><th width="186">Parametre Adı</th><th width="103">Tipi</th><th width="80">Zorunlu</th><th>Açıklama</th></tr></thead><tbody><tr><td>pos_alias</td><td>string</td><td>Hayır</td><td>Çekim işleminin yapılacağı pos kimliği.Gönderilmemmesi durumundayönetim panelinde yer alan veriler kullanılarak 'Akıllı Pos Yönlendirme' özelliği ile en uygun pos üzerinden çekim işlemi gerçekleştirilecektir.</td></tr><tr><td>card_brand</td><td>string</td><td>Hayır</td><td>Çekim işleminin yapılacağı pos'un kart ailesi bilgisidir.Bankaya air pos_alias gönderildiğinde bu parametrenin gönderilmesine gerek yoktur.Ödeme kuruluşuna ait pos_alias gönderildiğinde,birden fazla kart ailesi kayıtlı olması durumunda card_brand parametresi gönderilerek hangi kart ailesine çekim yapılacağı seçilebilir.Ödeme kuruluşu pos_alias gönderilmesine rağmen card_branc gönderilmemişse en düşük komisyonlu card_brand üzerinden işlem sağlanır.</td></tr><tr><td>price</td><td>decimal</td><td>Evet</td><td>Sepet tutarı.item parametresi altında yer alan tutarların toplamı ile eşit olmalıdır.</td></tr><tr><td>paid_price</td><td>decimal</td><td>Evet</td><td>Komisyon ve vade farkı gibi tutarlar sepet tutarına dahil edilerek gönderilmesi gereken nihai çekim tutarıdır.</td></tr><tr><td>installment_count</td><td>integer</td><td>Evet</td><td>Taksit sayısı.Tek çekim için 1 gönderilmelidir.</td></tr><tr><td>currency_type</td><td>integer</td><td>Evet</td><td>Para birimi; TRY,USD,EUR</td></tr><tr><td>customer_id</td><td>integer</td><td>Hayır</td><td>Ödüyo üzerindeki cari id'dir.</td></tr><tr><td>buyer_member_id</td><td>integer</td><td>Hayır</td><td>Üye oluşturma endpoint'i üzerinden oluşturduğunuz üyenin İd bilgisidir.</td></tr><tr><td>name</td><td>string</td><td>Hayır</td><td>Ödemeyi yapan müşteri adı</td></tr><tr><td>surname</td><td>string</td><td>Hayır</td><td>Ödemeyi yapan müşteri soyadı</td></tr><tr><td>client_ip</td><td>string</td><td>Evet</td><td>Ödemeyi yapan müşteri ip adresi</td></tr><tr><td>callback_url</td><td>string</td><td>Evet</td><td>Ödeme işlemi sonucunun bildireceği dönüş url</td></tr><tr><td>card</td><td>array</td><td>Evet</td><td>Ödeme işleminin yapılacağı kart bilgileridir; Parametreler -> holder_name(string) =Kart sahibi, number(integer)=Kart numarası, expiry_month(string)=Kart SKT ay,expiry_year(string)=Kart SKT yıl, cvc(string)=Kart güvenlik kodu</td></tr><tr><td>items</td><td>array</td><td>Evet</td><td>Ödeme işlemine dahil edilen ürün/hizmet; Parametreler -> name(string) =ürün/hizmet adı, price(decimal)=tutar,quantity(integer)=adet</td></tr></tbody></table>

### <mark style="color:blue;">Sonuç Parametreleri</mark>

Ödeme Başlatma işlemine ait detaylar data parametresi altında dizi olarak dönülmektedir.



<table><thead><tr><th width="192.39507525927533">Parametre Adı</th><th width="264.07985888816484">Tipi</th><th>Açıklama</th></tr></thead><tbody><tr><td>html_form</td><td>string</td><td>base64_encode ile şifrelenmiş html form bilgisi.</td></tr><tr><td>payment_id</td><td>integer</td><td>Başlatılan ödeme işleminin benzersiz id'si.</td></tr><tr><td>pos_alias</td><td>string</td><td>Ödemenin başlatıldığı pos kimlik bilgisi.</td></tr><tr><td>card_brand</td><td>string</td><td>İşlemin yapıldığı kart ailesi.</td></tr><tr><td>commission_rate</td><td>string </td><td>İşlemin yapılacağı komisyon oranı.</td></tr></tbody></table>
