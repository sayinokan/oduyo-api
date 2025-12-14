---
description: Tanımlanmış olan taksitler hakkında detaylı bilgi döndürür.
---

# Taksit Sorgulama

### <mark style="color:blue;">URL</mark>

Taksit sorgulamak için kullanılan endpoint ve http metod bilgisi aşağıda yer aldığı gibidir.



<table><thead><tr><th width="175.3097476496784">HTTP Metod</th><th width="614.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="https://www.siteadi.com/api/v1/payment/payment_create"><mark style="color:red;"><code>https://www.siteadi.com/api/v1/</code></mark></a><mark style="color:red;"><code>gateway/get_installments</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İstek Parametreleri</mark> <a href="#url" id="url"></a>

<table><thead><tr><th width="162">Parametre Adı</th><th width="92">Tipi</th><th width="84">Zorunlu</th><th>Açıklama</th></tr></thead><tbody><tr><td>price</td><td>decimal</td><td>Evet</td><td>Gönderilen fiyata göre taksit bilgilerini döndürür.</td></tr><tr><td>currency_type</td><td>option</td><td>Hayır</td><td>Yalnızca belirli bir para birimini destekleyen poslara ait taksit ve komisyon bilgisi görüntülenmek isteniyorsa bu parametre kullanılabilir.(TRT/USD/EUR) şeklinde kullanılmalıdır.Pos eklenirken seçilebilen tüm para birimleri desteklenmektedir.</td></tr><tr><td>bin_no</td><td>integer</td><td>Hayır</td><td>Bin numarası(Kredi kartının ilk 8 hanesi) gönderilerek çekim yapılabilecek taksit/komisyon seçeneklerinin görüntülenmesi sağlanır.</td></tr><tr><td>best_of_rate</td><td>boolean</td><td>Hayır</td><td>Sadece en iyi oranlı taksit seçenekleri gösterilmek istenirse *<strong>true*</strong> gönderilmelidir.Örneğin Bonus kart ile çekim yapılmak isteniyor; Denizbank ve Garanti posları tanımlı ise iki pos üzerinde tanımlanmış komisyon oranları kıyaslanarak her bir taksit için en uygun komisyon oranlı pos hangisi ise o görüntülenir.2 taksit oranı Garanti oranından iyi ve Garanti'nin 3 taksit oranı Denizbank oranından iyi ise bu durumda Denizbank'ın 2. ve 3.taksitleri gösterilir.Denizbank'ın 3. ve Garanti'nin 2.taksitleri gösterilmez.</td></tr><tr><td>pos_alias</td><td>string</td><td>Hayır</td><td>Belirli bir pos'a ait taksit ve komisyon bilgilerinin listelenmesi için kullanılabilir.</td></tr></tbody></table>

### <mark style="color:blue;">Dönüş Parametreleri</mark> <a href="#url" id="url"></a>

İptal işlemine ait bilgiler data parametresi altında dizi olarak dönülmektedir.

<table><thead><tr><th width="180">Parametre Adı</th><th width="114">Tipi</th><th>Açıklama</th></tr></thead><tbody><tr><td>price</td><td>decimal</td><td>Gönderilen tutar bilgisi döndürür.</td></tr><tr><td>currency_type</td><td>string</td><td><p>Para birimi;   </p><p>• TRY                                                            •   • • • </p><p>• USD</p><p>• EUR</p></td></tr><tr><td>bank_name</td><td>string</td><td>Banka yada ödeme kuruluşu adı</td></tr><tr><td>bank_id</td><td>string</td><td>Banka yada ödeme kuruluşu id bilgidi</td></tr><tr><td>force_3ds</td><td>string</td><td>3d işlemi zorunlu kılma durumu; 1 ->EVET 2 -> HAYIR</td></tr><tr><td>cvc_required</td><td>number</td><td>CVC Kodu zorunlu kılma durumu; 1 ->EVET 2 -> HAYIR</td></tr><tr><td>pos_alias</td><td>boolean</td><td>Sistem tarafından oluşturulan benzersiz POS kimliği</td></tr><tr><td>installments</td><td>array</td><td>Kart ailesi ile indexlenmiş diziler altında Taksit sayısı ile indexlenmiş diziler dönülmektedir.Bu dizilerin içerisinde aşağıdaki bilgiler yer almaktadır. Parametre adı; installment_no -> taksit sayısı, installment_price -> taksit tutarı, total_price ->toplam tutar, pos_alias ->pos benzersiz kimliği</td></tr></tbody></table>