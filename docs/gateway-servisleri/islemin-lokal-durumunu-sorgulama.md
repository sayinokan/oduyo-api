---
description: İşlemin sunucu tarafındaki durumunun sorgulanması için kullanılır
---

# İşlemin lokal durumunu sorgulama

### <mark style="color:blue;">URL</mark>

!!! note
	```text
	Lokal durum sorgulama işlemi için kullanılan endpoint ve http metod bilgisi aşağıda yer aldığı gibidir.
	```



<table><thead><tr><th width="175.3097476496784">HTTP Metod</th><th width="614.4285714285713">URL</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>POST</code></mark></td><td><a href="https://www.siteadi.com/api/v1/payment/payment_create"><mark style="color:red;"><code>https://www.siteadi.com/api/v1/</code></mark></a><mark style="color:red;"><code>gateway/local_status</code></mark></td></tr></tbody></table>

### <mark style="color:blue;">İstek Parametreleri</mark> <a href="#url" id="url"></a>

Çekim işlemleri listeleme işlemi için isteklerde gönderilmesi beklenen parametreler ve sorgu örneği aşağıda belirtilmiştir.

<table><thead><tr><th width="137">Parametre Adı</th><th width="92">Tipi</th><th width="84">Zorunlu</th><th>Açıklama</th></tr></thead><tbody><tr><td>payment_id</td><td>integer</td><td>Evet</td><td><p></p><pre data-overflow="wrap" data-full-width="false"><code><strong>Durumu öğrenilmek istenen ödeme işleminin benzersiz id'si.
</strong></code></pre><p><br></p></td></tr></tbody></table>

### <mark style="color:blue;">Dönüş Parametreleri</mark> <a href="#url" id="url"></a>

```
İade işlemine ait bilgiler data parametresi altında dizi olarak dönülmektedir.
```

\


<table><thead><tr><th width="199">Parametre Adı</th><th width="91">Tipi</th><th>Açıklama</th></tr></thead><tbody><tr><td>callback_status</td><td>string</td><td>Başlatılan ödeme işleminin bankadan dönen sonucu; Dönüş parametresi açıklaması -> payment_failure=Ödeme başlatılamadı,           error=Ödeme tamamlanamadı,                completed=Ödeme tamamlandı, already_returned=Ödeme tamamlanamadı</td></tr><tr><td>complete_status</td><td>string</td><td><p>Ödeme işleminin son durumu;</p><p>Dönüş Parametresi-></p><p>failure=Ödeme başlatılamadı,</p><p>error=Ödeme tamamlanamadı,</p><p>waiting=Ödeme onaylama işlemi bekleniyor,</p><p>completed=Ödeme alındı,</p><p>cancelled=Ödeme alındı ve ödeme işlemi iptal edildi,</p><p>refunded=Ödeme alındı ve iade işlemi yapıldı,</p><p>partial_refunded=Ödeme alındı ve kısmi iade işlemi yapıldı.</p></td></tr></tbody></table>