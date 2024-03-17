# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/tryhackme-sakura-room-write-up)**

---
[Sakura Room](https://tryhackme.com/room/sakura) odasının makine çözümü hakkında bir yazı. İyi çalışmalar.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63358b31b215c.jpg)

## 1. GÖREV : GİRİŞ

### SORU 1: Başlamaya hazır mısınız?

#### CEVAP: **Let's Go!**

## 2. GÖREV: İPUCU

### SORU 1: Saldırgan hangi kullanıcı adını kullanıyor?

Soruda saldırganın bıraktığı resmin kopyası linkte verilmiştir. Linke basalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63358db028854.jpg)

Linke basınca aşağıdaki görüntüden başka bir şey yok.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63358eb721ee7.jpg)

Bu tür durumlarda ilk başvurmamız gereken şey sayfanın kaynak kodlarıdır. Faremiz ile sağa tıklayıp inceleye basalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63358ede1d6af.jpg)

Ve burada saldırganın kullanıcı adını bulmuş bulunmaktayız.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63358f94513ab.jpg)

#### CEVAP: SakuraSnowAngelAiko

## 3. GÖREV: KEŞİF

### SORU 1: Saldırgan tarafından kullanılan tam e-posta adresi nedir?

Bilgilendirme kısmında da bahsettiği gibi bir kullanıcı adı ile birçok bilgiye ulaşabiliriz. Bulduğumuz kullanıcı adı ile googlede aratalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_633591f942390.jpg)

İlk önce bir GitHuba girelim. Sayfayı ilk açtığımda gözüme ilk ilişen PGP Keys oldu. Buna bir bakalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_633592ef3fb5d.jpg)

Buradan View code kısmına bakalım. Buradan da publickey denen kısma basalım.  

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359338ed1f8.jpg)

Burada bize uzunca bir hash verdiğini görüyoruz.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335957f29700.jpg)

Hashın ilk satırında (----BEGIN PGP PUBLİC KEY BLOCK-----) da  anlaşılacağı üzere bu hash PGP algoritmasınındır. Şimdi bu hashı çözelim bakalım bize ne tür bilgiler verecek. Googleye pgp decoder yazıp ilk siteye girin. Hashın kodunu çözün.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_633595e9380f7.jpg)

Ve işte saldırganın mail hesabı:

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335961312f43.jpg)

#### CEVAP: [SakuraSnowAngel83@protonmail.com](SakuraSnowAngel83@protonmail.com)

### SORU 2: Saldırganın tam gerçek adı nedir?

Saldırganın kullanıcı adını tekrar googleden aradığımızda bir linkedin hesabının olduğu anlaşılıyor.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6336e1a90de93.jpg)

#### CEVAP: Aiko Abe

## 4. GÖREV: AÇIKLA

### SORU 1: Saldırgan hangi kripto para birimi cüzdanına sahiptir?

“Bazı platformlarda, sayfa önbelleğe alınmadıkça veya başka bir platformda arşivlenmedikçe, düzenlenen veya kaldırılan içerik kurtarılamayabilir. Ancak, diğer platformlar düzenlemelerin, silmelerin veya eklemelerin geçmişini görüntülemek için yerleşik işlevselliğe sahip olabilir. Kullanılabilir olduğunda, bu denetim geçmişi, araştırmacıların bir zamanlar muhtemelen yanlışlıkla veya gözetimle dahil edilen ve daha sonra kullanıcı tarafından kaldırılan bilgileri bulmalarını sağlar. Bu tür içerikler genellikle bir soruşturma sırasında oldukça değerlidir”  

Bize böyle bir bilgi verilmiştir. Bu da oluyor ki saldırgan onu takip ettiğimizin farkında ve bazı yerlerden birtakım bilgileri kaldırmış.  Yukarıdaki bilginin de bahsettiği gibi bazı platformlarda silme düzenleme ekleme geçmişi görüntülenebiliyor. Github da bu platformlardan biridir.

Tekrardan saldırganın github hesabına girelim. Buradan github deposuna girip detaylıca bir inceleyelim.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335990b628ff.jpg)

Buradan ETH deposuna girelim. (ETH, ERC-20 kod sistemi sayesinde birçok kripto para biriminin altyapısını oluşturan merkeziyetsiz ve açık kaynak kodlu bir blok zinciridir.)

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335996de13e1.jpg)

Burada bir script vermiş onu açalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_633599a234ea3.jpg)

Sağ üstte 23.01.2021 yılı için bir geçmiş gösteriyor oraya bakalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359a3b24bda.jpg)

Üsttekine bakalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359a5fb878e.jpg)

Burada kırmızı renkle gösterilen kısım silinmiş alan.  Sarı renk ile vurguladığım kısmı googleden aratalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359a8e6a83d.jpg)

Arattığımızda hemen ikinci sitede kripto para birimi ismi gözükmektedir.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359ae3b57e5.jpg)

#### CEVAP: Ethereum

### SORU 2: Saldırganın kripto para cüzdan adresi nedir?

Üstteki resimde kırmızı kısım bu sorunun cevabı.

#### CEVAP: 0xa102397dbeeBeFD8cD2F73A89122fCdB53abB6ef

### SORU 3: Saldırgan 23 Ocak 2021 UTC'de hangi madencilik havuzundan ödeme aldı?

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359c3d4fc6c.jpg)

#### CEVAP: Ethermine

### SORU 4: Saldırgan kripto para birimi cüzdanını kullanarak başka hangi kripto para birimini değiştirdi?

Saldırganın kripto para cüzdan adresini googleden arattığımıza ikinci siteyi açalım. Siteyi açtığımızda karşımıza bir arama çubuğu var .
![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359ccb63f59.jpg)

Buraya “0xa102397dbeeBeFD8cD2F73A89122fCdB53abB6ef “ yapıştıralım. Karşımıza çıkan sayfada işaretlediğim kısıma basalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359d0539ebc.jpg)

Sayfa bize hesap hareketlerini gösteriyor. Biraz sayfayı inceleyelim. İncelediğimizde burada faklı bir kripto para birimini görmekteyiz.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359d3c668f5.jpg)

#### CEVAP: Tether

## 5. GÖREV: ALAY

### SORU 1: Saldırganın şu anki Twitter tanıtıcısı nedir?

Saldırgan tarafından bize gönderilen mesaja bakalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359dee957e2.jpg)

Saldırganın mesajı: "Ne yaptığını görmediğimi sanma! Beni yakalamayacaksın BTW. Ben zaten gidiyorum . Evine dön, baaaayyyyy! "

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359e59dd727.jpg)

Resimdeki kullanıcı adını twitterda aratalım.  Karşımıza böyle bir tweet çıkıyor. Tweeti atan kullanıcının sayfasına gidelim.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359e7a54059.jpg)

Ve karşımızda  şuanki Twitter tanıtıcısı :

![resim](https://sibermetin.com/uploads/images/202209/image_750x_63359f17ddb59.jpg)

#### CEVAP: SakuraLoverAiko

### SORU 2: Saldırganın WiFi SSID'lerini ve şifrelerini kaydettiği konumun URL'si nedir?

Saldırganın tweetlerini incelediğimizde şöyle bir tweet karşımıza çıkıyor:

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a139de37a.jpg)

Tweet : ” Artık yeni telefonlar aldığımda Ap’lerimi unutmak yok !”  Saldırgan bu tweetin altına bir tweet daha atmış. Ve burada DEEP PASTE büyük yazmış.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a185d0815.jpg)

Bu da demek oluyor ki deep webden DeepPaste sitesine gidip tweette verilen hashı orada aratmak.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a1b11470c.jpg)

Ben bayağı duckduckgo üzerinden bu siteyi aradım bulamadım. Zaten ipucunda deep webe girmek istemeyenler için link vermiş. Biz oradan yararlanalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a1e5701b0.jpg)

Verilen linke girelim.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a2069f887.jpg)

Soru bizden url istiyor.  Üstteki arama çubuğunun yanındaki kutuya da hashı yazacağız ve işteee cevap

#### CEVAP: [http://depasteon6cqgrykzrgya52xglohg5ovyuyhte3ll7hzix7h5ldfqsyd.onion/show.php?md5=0a5c6e136a98a60b8a21643ce8c15a74](http://depasteon6cqgrykzrgya52xglohg5ovyuyhte3ll7hzix7h5ldfqsyd.onion/show.php?md5=0a5c6e136a98a60b8a21643ce8c15a74)

### SORU 3: Saldırganın Ev Wifi'si için BSSID nedir?

Bu soruyu çözmek için wigle.net sitesinden yararlanacağız. Ve aynı zamanda bu soruyu çözebilmeniz için  hesap açmanız gerek.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a2c88986c.jpg)

Görselde işaretlediğim yere girelim. SSID / Network Name (exact match) yazan kutucuğa “DK1F-G” yazalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a2f25a656.jpg)

Ve işte cevap:

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a31766228.jpg)

#### CEVAP: 84:af:ec:34:fc:f8

## 6. GÖREV: EVE DÖNÜŞ

### SORU 1: Saldırganın uçuşa binmeden önce fotoğraf paylaştığı konuma en yakın havaalanı hangisidir?

Saldırganın tweetlerinden birinde uçağa binmeden önce paylaştığı fotoğraf var.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a441a62df.jpg)

Tweette Bethesda’da olduğunu söylüyor. Hemen googleden “Bethesda airport” diye aratalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a46bd6754.jpg)

#### CEVAP: DCA

### SORU 2: Saldırganın son yatışı hangi havaalanındaydı?

Saldırganın tweetlerinden birinde bir otel var.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a51d20fe4.jpg)

Otelin üzerinde yazan yazıyı hemen googlede aratalım.  

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a54c8c0a0.jpg)

Burada Haneda bilgisine ulaşıyoruz.

#### CEVAP: HND

### SORU 3: Saldırganın son uçuşunda olduğu gibi paylaştığı haritada hangi göl görülebilir?

Tweetindeki haritadan yararlanacağız.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a5d440a9e.jpg)

Bu görseli web'de arayalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a607e594f.jpg)

Karşımıza böyle bir sayfa gelecek.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a63abcf06.jpg)

Buradan haritalara girelim. Haritalar kısmında katmanlar kısmından uydu görünüm yapalım çünkü sorudaki görsel de uydu görünümdedir bulmamız daha kolaylaşır.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a6504ebba.jpg)

Biraz inceleyerek görselde verilen kısmı bulabiliriz.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a67910bdd.jpg)

#### CEVAP: Lake Inawashiro

### SORU 4: Saldırgan muhtemelen hangi şehri "ev" olarak görüyor?

Tekrar wigle.net sitesine gidelim.  

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a71968df3.jpg)

Sonra :

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a7378e923.jpg)

Önceki görevde bulduğumuz BSSID buraya yazalım.

![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a75d4b319.jpg)

Veee sorumuzun cevabı burada.
![resim](https://sibermetin.com/uploads/images/202209/image_750x_6335a76743a14.jpg)

#### CEVAP: Hirosaki

Odamızın çözümünü bitirdik...

Buraya kadar vakit ayırıp okuduğunuz için teşekkür ederim.
