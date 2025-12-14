---
description: >-
  API sorguları yaparken body içerisinde oturum bilgilerini göndermeniz
  gerekmektedir.
---

# Filtreleme Parametreleri

### <mark style="color:blue;">İşlem Parametreleri</mark>

Listeleme servislerinde istek sorgusunda kullanılan parametrelerle ilgili detaylar ve örnekler aşağıda belirtilmiştir.

```
{
    "filters":"",
    "params" :"",
    "limit":"1000",
    "offset" : "0",
    "sorting":[{"field": "id", "sort": "ASC"}]
}
```

<table><thead><tr><th width="150">Tag</th><th>Açıklama</th></tr></thead><tbody><tr><td><code>filters</code></td><td>Listelemek istediğiniz kolon veya belirli bir veriyi çekebilmek için kullanılabilen filtreleme alanıdır.</td></tr><tr><td><code>params</code></td><td>Listelenecek kolonları ifade eder.</td></tr><tr><td><code>limit*</code></td><td>Listelemek istediğiniz veri sayısını ifade eder.</td></tr><tr><td><code>offset*</code></td><td>Listelemek istediğiniz veri işlem numarasının (id) başlangıç değerini ifade eder.</td></tr><tr><td><code>sorting</code></td><td>Listelemek istediğiniz verilerin sıralama standardını ifade eder.</td></tr></tbody></table>

{% hint style="info" %}
&#x20;limit ve offset parametreleri zorunlu parametrelerdir.
{% endhint %}

<mark style="color:blue;">Filtreleme Örneği</mark>

Filters alanı kullanarak istenilen bir kolonda belirlenen veriye uygun kaydın getirilmesi istenmektedir.

```
{
    "filters":[{"field": "id", "operator": "=", "value":"1"}],
    "params" :"",
    "limit":"",
    "offset" : "",
    "sorting":""
}
```

<table><thead><tr><th width="150">Tag</th><th width="290.8910891730195">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td>field</td><td>Listelemek istediğimiz verilerin ait olduğu kolonları ifade eder.</td><td><strong>String</strong></td></tr><tr><td>operator</td><td>Field ve value değerleri arasındaki eşleştirme ifadelerini parametre olarak alır.</td><td><strong>"=", "OR =", ">", "OR >", "&#x3C;", "&#x3C;=", "OR &#x3C;", ">=", "OR >=", "&#x3C;=", "OR &#x3C;=", "&#x3C;>", "OR &#x3C;>", "IN", "OR IN", "NOT LIKE", "NOT IN", "OR NOT IN", "LIKE", "OR LIKE", "OR NOT LIKE", "LIKE AFTER", "LIKE BEFORE", "LIKE NONE"</strong></td></tr></tbody></table>

<mark style="color:blue;">Filtreleme Örneği 2</mark>

Params alanı kullanılarak listelenecek alanlar arasında yalnızca "id" kolonunun listelenmesi beklenmektedir.

<pre class="language-javascript"><code class="lang-javascript"><strong>{
</strong>    "filters":"",
    "params" : {"colums": ["id"]},
    "limit":"",
    "offset" : "",
    "sorting":""
}
</code></pre>

<table><thead><tr><th width="150">Tag</th><th width="351.3333333333333">Açıklama</th><th>Format</th><th data-hidden></th></tr></thead><tbody><tr><td>colums</td><td>Listelemek istediğiniz kolonları ifade eder.</td><td><strong>String</strong></td><td></td></tr></tbody></table>

<mark style="color:blue;">Filtreleme Örneği 3</mark>

Limit alanı kullanılarak listeden belirtilen sayı miktarınca kayıt listelenmesi beklenmektedir.

```
{
    "filters":"",
    "params" : "",
    "limit":"100",
    "offset" : "",
    "sorting":""
}
```

<mark style="color:blue;">Filtreleme Örneği 3</mark>

Offset alanı kullanılarak listelenecek verilerin tablo pk id numarasının belirtilen değerden başlanarak listelenmesi beklenmektedir.

```php
{
    "filters":"",
    "params" : "",
    "limit":"",
    "offset" : "0",
    "sorting":""
}
```

<mark style="color:blue;">Filtreleme Örneği 4</mark>

Sorting alanı kullanılarak listelenecek verilerin belirlenen bir sıralama dahilinde listelenmesi beklenmektedir.

```
{
    "filters":"",
    "params" :"",
    "limit":"",
    "offset" : "",
    "sorting":[{"field": "id", "sort": "ASC"}]
}
```

<table><thead><tr><th width="150">Tag</th><th width="376.50982594048287">Açıklama</th><th>Format</th></tr></thead><tbody><tr><td>field</td><td>Listelemek istediğimiz verilerin ait olduğu kolonları ifade eder.</td><td><strong>String</strong></td></tr><tr><td>sort</td><td>Listelemek istediğimiz verilerin hangi sıralama formatı ile sıralanacağını ifade eder.</td><td><strong>"asc",                        "desc"</strong></td></tr></tbody></table>