# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/steganografi)**

---

![resim](https://sibermetin.com/uploads/images/202204/image_750x_62658a6b335d0.jpg)

## STEGANOGRAFİ NEDİR?

Latincede "steganos" görünmeyen, steganografi de gizlenmiş yazı demek. Kısacası steganografi veri gizleme bilimidir. Steganografi bir verinin başka bir veri içine gözle görülmeyecek şekilde gizlenmesidir.

Steganografi yöntemi ile veriler 3. şahısların eline geçmiş olsa bile sadece dış kapağı görülebilecek, gerçek bilgiler görülmeyecektir.

Steganografide gizlenecek veriler genellikle görüntü, video ve seslerin içine saklanır. Örneğin bir resim içine bir metin saklayabilirsiniz. Aynı zamanda resim içerisinde resim de saklayabilirsiniz.

Resim içine gizlenmiş metin;

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263e6e26f7a1.jpg)

Resim içine gizlenmiş resim;

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263e768d3d8d.jpg)

Bu örneklerden de anlaşılacağından masum görünen resimlerin çok da masum olmadığı.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263e7b2bb6e3.jpg)

Kriptografi, düz bir metini istenilmeyen kişiler tarafından anlaşılmaması için çeşitli şifreleme algoritmaları kullanılarak şifreli bir metine dönüştüren şifreleme bilimidir.

Kriptografide veriler göz önündedir fakat şifreli biçimdedir. Steganografi, kriptografiden farklı olarak gizli mesajları göz önünde bulundurmuyor olmasıdır.

Steganografi kriptografi gibi şifreleme bilimi değildir!

Hiçbir gizli veri çözülemez değildir. Steganografide de şifreleme tekniklerinde de amaç,  bit veriyi olabilecek en iyi şekilde gizlemektir.

## STEGANOGRAFİ  TARİHÇESİ

Steganografi eski çağlarda da oldukça kullanılmıştır. Bazıları;

Yunan tarihçisi Herodot’un eserinde Pers saldırısının öncesinde İran’da bulunan casus, kölesinin istila uyarısını kafa derisine kazıtmıştır. Daha sonra kölenin saçının uzamasıyla kölesini Yunanistan’a göndermiştir. Bu şekilde, mesaj dikkat çekmeden gerekli yere ulaşabilmiş, ulaştığında da kölenin saçları tekrar kesilerek uyarı okunabilmiştir.
Eski Yunanistan’da insanlar mesajları tahtaya yazıp üzerini mumla kaplarlardı. Böylece cisim kullanılmamış bir tablete benzerdi öte yandan mumun eritilmesiyle birlikte içindeki gizli mesaj okunabilirdi.

Dünya Savaşı sırasında, New York’taki, Japon milli ajanı (Velvalee Dickinson) oyuncak bebek pazarlamacısı kılığı altında saklanmaktaydı. Bu ajan, Amerikan ordusunun hareketlerini bebek siparişi içeren mektuplar içine saklayarak Güney Amerika’daki adreslere gönderiyordu.

Özellikle 1960’larda mor ötesi boya ile yazı yazabilen sprey ve kalemler moda idi. Bu kalemlerin yazdığı yazılar, sadece bir mor ötesi ışıkla görülebiliyordu.

İletişimin gizliliği için steganografi kullanılır. Steganografi 90’lı yıllarından sonra adını duyurdu. 11 Eylül saldırıları ve Amerikan hükümetinin uzun yıllardır uyguladığı güçlü kriptografik algoritma ihracının sınırlandıran yasası steganografinin ismini duyurmasına etkili oldu.

11 Eylül saldırısından bir kare;

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263e8dc81066.jpg)

## GENEL STEGANOGRAFİ MODELİ

Steganografi 3 temel elemandan oluşmaktadır. Bunlar; gizli mesaj, stego key ve medya dosyasıdır. Gizli mesaj, gönderici tarafından alıcıya güvenli bir şekilde aktarılmak istenilen mesajdır. Stego key, gönderici ve alıcı arasında gönderilme mesajının gizleme işlemi için kullanılan bilgiyi içerir. Medya nesnesi, verinin stego key vasıtası ile gizleneceği formattır. Günümüz teknolojisinde veriler dijital ortamlarda saklanmaktadır. Veriler alışveriş yapılırken tüm dijital dosyalar bitler şeklinde saklanmaktadır. Bunun sayesinde herhangi bir resim, video, ses dosyası içerisine gizlenme işlemi yapılabilmektedir.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263e9b6688fd.jpg)

## STEGANOGRAFİK TEKNİKLER

Steganografi incelenirken 3 temel hususa dikkat edilmelidir.

**1.** **Değişimin Fark Edilmemesi İlkesi**

İnsan duyularıyla algılanamayacak şekilde gizlenmiş olmalı. Aksi takdirde 3. kişiler veriye kolaylıkla erişim sağlayabilir.

**2.** **Saklanabilecek Veri Miktarı İlkesi**

Saklanacak verinin miktarı arttıkça örtü veri (yani veriyi gizleyeceğim yer; resim, ses, video vs) üzerindeki değişim insan duyularıyla algılanabilecek durumlara gelir.

**3.** **Dayanıklık İlkesi**

Gizli verinin alıcı tarafından örtü veri içinde çıkartılıp erişebileceğini düşünürsek pek de dayanıklı olmadığını anlayabiliriz.

Tüm bu koşullar ve ikilemler dâhilinde her türlü saldırıya göğüs gerebilecek bir algoritma henüz yayınlanmamıştır. Ancak, çeşitli düzeydeki ihtiyaçlar doğrultusunda önerilen algoritmalar başarılı olarak kullanılabilir.

Steganografide kullanılan yöntemler;

- Değiştirmeye dayalı yöntemler
- İşaret işlemeye dayalı yöntemler
- İstatistiksel yöntemler
- Diğer yöntemler

## STEGANOGRAFİYİ NEREDE KULLANIYORUZ?

Herhangi bir üreticinin üretmiş olduğu görüntü, video veya ses gibi nesnelerde bir ticari işaret veya özelliğin gizlice depolanmasına damgalama (Watermarking), seri numarası veya diğer karakteristik bir özelliğin nesneye gizlenmesine de parmak izi (finger print) denilmektedir. Damgalama ve parmak izi işlemleri ile korsan işlerin önüne geçmek ve yasal sürece yardımcı olarak telif hakları ihlallerinin önüne geçilmesi için oluşturulmaktadır. Bu yöntemler vasıtası ile bir bilgiyi gizleyerek başka bir yere taşımak yerine ürünlerin sahiplik haklarının veya çoğaltılma izinlerinin korunması sağlanmıştır. Bu sayede aslında gizlenecek veri sayesinde gizlenen medyanın haklarının korunması amaçlanmış olmaktadır.

Watermarking örneği;

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263eabf86515.jpg)

## STEGANOGRAFİ ARAÇLARI

Stegonografi, eski zamanlardan beri başkalarının görmesini istemedikleri mesajları iletmek için kullanılmıştır. Günümüzde aynı amaç için kullanılıyor fakat şimdi çok daha gelişmiş araçlara sahibiz. Şimdi bu araçları inceliyelim;

### **1. STEGHIDE**

En çok kullanılan steganografi araçlarından biridir. Bir dosya içerisine veri gizlemek için kullanılan bir araçtır. Linux  ve Windows için C++ dilinde yazılmıştır.

Steghide toolunu kullandığımız linux’a terminal üzerinden kurabiliriz.

**sudo** **apt** **install steghide**

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263eb65a997f.jpg)

Terminale steghide yazarak tüm seçeneklerin listesini verir.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263ec324c15d.jpg)

Steghide parametreleri;

**Embed:** Dosya içine veri gömmek için kullanılır. Bu komut ile parola girilerek veri gizlenilebilir.

**Extract:** Gizlenen veriyi dosya içinde çıkartmaya yarayan komuttur.

**İnfo:** Gömülü veriler içeren bir dosyayı ayıklamadan önce bu dosya hakkında bilgi almak için bu komut kullanılır.

**Encinfo:** Desteklenen şifreleme algoritmalarının ve kullanılabilecek modların listesini görüntüler.

**Version:** Steghide versiyon bilgisini görüntüler.

**License:** Steghide lisans bilgisini görüntüler.

**Help:** Aracın tüm parametreleri hakkında detaylı bilgi verir.

Steghide aracını ses dosyaları için **“–wav “** ve **“–au”** formatlar kullanılır.

Wav: Bu formattaki ses dosyaları sıkıştırılmamış haldedir. Bu nedenle boyutları çok büyüktür.

Au: Bu formattaki dosyalar, basit tipte ses veya müzik dosyasıdır. Sun Microsystems veya Unix sistemlerinde kullanılmaktadır.

### **2. ZSTEG**

PNG ve BMP dosyaları için kullanılan steganografi tooludur. Linux terminali üzerinden kurmak için ;

 **sudo gem** **install zsteg**

 ![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263eca499d1d.jpg)

### **3. EXIFTOOL**

Görüntü, ses, video ve PDF meta verilerini okumak, yazmak ve işlemek için ücretsiz ve açık kaynaklı bir yazılım programıdır.

Fakat kendi başına bir steganografi toolu değildir.

Exiftool Linux terminalinden kurmak için:

**sudo apt** **install exiftool**

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6263ed4509205.jpg)

### **4. STEGOVERİTAS**

Hemen hemen her görüntü dosyasını destekleyen bir toldur. Stegoveritas'ın renk düzeltme görüntüleri gibi başka özellikleri de vardır.

Linux terminalinden kurmak için bu komut yazılır:

**pip3 install** **stegoveritas**

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626415b69cd64.jpg)

### **4. SPEKTROGRAM**

Bir ses dosyasının gizli bir görüntüyü gizlemesine olanak sağlayan bir tooldur.

Peki nasıl kullanırız?

*Sonic Visualizer'ı açmalıyız en başta;*

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626416326173d.jpg)

*Oradan Dosya->Aç'a tıklayıp ve ardından dahil edilen wav1 dosyasını seçmeliyiz;*

![resim](https://sibermetin.com/uploads/images/202204/image_750x_6264165b9c94d.jpg)

*Oradan Katman-> Spektrogram* *Ekle'ye tıklamalıyız*

![resim](https://sibermetin.com/uploads/images/202204/image_750x_62641682d0e05.jpg)

## STEGANOGRAFİ SİTE ÖNERİSİ

- [futureboy.us](https://futureboy.us/stegano/decinput.html)

- [aperisolve.fr](https://aperisolve.fr/bf47ce257589f70221cbaae40fae0989)

- [academo.org](https://academo.org/demos/spectrum-analyzer/)
