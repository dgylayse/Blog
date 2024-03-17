# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/portswigger-api-testing-write-up)**

---
![resim](https://sibermetin.com/uploads/images/202312/image_750x_65889ade72109.jpg)

## Lab 1: Belgeleri Kullanarak Bir API Uç Noktasından Yararlanma

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658880005d816.jpg)

Burp aracını açıp giriş kısmından kullanıcı bilgisini girip giriş yapalım. (“ wiener: peter ”)

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888052a5a11.jpg)

Giriş yaptıktan sonra e-posta adresini güncellememiz istenecek.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588809a0871d.jpg)

 Rastgele bir mail adresi girelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588811dcc3d8.jpg)

Rastgele bir mail adresi girerek girişin başarılı olduğunu Burp Suite aracımızdan görebiliriz. Şimdi Request kısmını Repeater kısmına göndererek işe koyulalım.

Test amaçlı tekrar bir istek gönderelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588815c66e04.jpg)

Bu sefer GET metoduyla ile istek atalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588818a4f524.jpg)

GET isteğinde mail kısmına ihtiyacımız yok. Bu kısmı sildiğimiz halde istek attığımızda bilgiler hâlâ görünüyor.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658881b753243.jpg)

Çerez bilgisini silerek GET isteği atmayı deneyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658881f29d6ec.jpg)

Cevap olarak yetkisiz olduğumu söylüyor. Kullanıcı adını “carlos ” olarak değiştirip istek atalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588822068b26.jpg)

Girişimizi başarılı bir şekilde gerçekleştirmiş bulunmaktayız. Kullanıcıyı silersek laboratuvarı çözüme kavuşturmuş olacağız. DELETE metodu ile kullanıcıyı silelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658882556b94a.jpg)

Cevap kısmında kullanıcıyı sildiğimizi görebiliyoruz. Şimdi 2. laboratuvarımıza geçebiliriz.

## Lab 2: Sorgu Dizesinde Sunucu Tarafı Parametre Kirliliğinden Yararlanma

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888a4f70473.jpg)

Burp aracını açıp giriş kısmından kullanıcı bilgisini girip giriş yapalım. (“ wiener: peter ”)

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888a8eb70f0.jpg)

Girdiğimiz kullanıcı adı ya da şifrenin hatalı olduğunu söyleyen bir uyarı alıyoruz. Şifreyi unuttum kısmına girelim. Kullanıcı adı kısmına “administrator” yazalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888aea9a7a1.jpg)

Aşağıdaki görselde görünen mail hesabına şifreyi değiştirmek için bağlantı gönderildi. Amacımız o bağlantıya sahip olmak.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888b255b0c5.jpg)

Burp Suite aracından “forgot-password” kısmını repeatera yollayalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888b5515ba0.jpg)

Geçersiz bir kullanıcı adı kullanıp hata alıp almadığına bakalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888b895fbc7.jpg)

Bir hata verdiğini gördük. “#” karakterini kullanarak sunucu tarafı sorgu dizesini kesmeyi deneyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888ce652a3e.jpg)

Bir hata ile karşılaştık. Şimdi parola sıfırlama için kullanılan “reset_token” parametresini kullanıp istek atalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888d18b2a18.jpg)

Şimdi parametre değerini şu şekilde değiştirip tekrar istek atalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888d458f2a4.jpg)

Geçerli bir alan türü olması için parametreye “field” eklemeliyiz. Şimdi istek atalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888d6dd8b9d.jpg)

Result kısmındaki değeri adres çubuğuna ekleyip girelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888d94199fb.jpg)

Karşımıza  şifreyi değiştirmek için bir sayfa açılıyor. Rastgele bir şifre oluşturabiliriz.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888dcee3cb3.jpg)

Şifreyi değiştirdik. Şimdi de tekrar login kısmına gelip “administrator” kullanıcı adı ve belirlediğim şifre ile giriş yapalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888df7c92e9.jpg)

Önümüze çıkan sayfada Admin panel yazan kısmına girelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888e31d93f2.jpg)

Carlos kullanıcısını silerek laboratuvarı çözüme kavuşturabiliriz.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888e5a3af38.jpg)

Şimdi 3. laboratuvara geçebiliriz.

## Lab 3: Kullanılmayan Bir API Uç Noktasını Bulma ve Bunlardan Yararlanma

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888e97f1154.jpg)

Burp aracını açıp giriş kısmından kullanıcı bilgisini girip giriş yapalım. (“ wiener: peter ”)

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888ebdb398c.jpg)

Ana sayfaya gidip ceketi sepete ekleyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888ef561938.jpg)

Sepete gidip sipariş vere tıkladığımızda yeterli kredinin olmadığını söylüyor.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888f2534dd5.jpg)

Burp Suite aracından HTTP history kısmını incelediğimizde /api/products/1/price kısmı gözümüze çarpıyor. Bunu repeatera yollayıp inceleyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888f708c420.jpg)

Bir GET isteği yolladığımızda ürün fiyatını ve mesajını gösteriyor. Biz bu ürün fiyatını 0 olarak değiştirip sipariş etmeye çalışacağız.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888f9d8537e.jpg)

Şimdi diğer istek metotlarını deneyelim ilk olarak POST metotundan başlayalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888fbb7c2e9.jpg)

POST metotunu kullandığımızda izin verilmedi uyarısı ile karşılaşıyoruz. Şimdi diğer metotumuz olan PATCH kullanalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588900a8ad7d.jpg)

PATCH isteği yolladığımızda  sadece “Content-Type: application/json” desteklediğini söylüyor. Biz de request kısmına  “Content-Type: application/json” ekleyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588903a5e061.jpg)

Ekledikten sonra tekrar istek attığımızda dahili servis hatası verdi. “price: 0” değerini ekleyerek fiyatın 0 olmasını sağlayalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588906503d2c.jpg)

Tekrar istek attığımızda cevap olarak ürünün fiyatını 0$ olarak verdi. Şimdi siparişimizi yapabiliriz.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588909929075.jpg)

 Siparişimizi verdiğimize göre 4. laboratuvarımıza geçebiliriz.

## Lab 4: Toplu Atama Güvenlik Açığından Yararlanma

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658891306acc0.jpg)

Burp aracını açıp giriş kısmından kullanıcı bilgisini girip giriş yapalım. (“ wiener: peter ”)

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65888ebdb398c.jpg)

Giriş yaptıktan sonra home sayfasına gidip deri ceketi sepete ekleyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588915f54327.jpg)

Sepete gidip sipariş vere tıkladığımızda satın alma işlemi için yeterli kredinin olmadığını söyleyen bir uyarı veriyor.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658891c620451.jpg)

Burp Suite aracından api isteklerini incelemek için repeatere atalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658891fb1b873.jpg)

İstek attığımızda gelen cevapta indirim yüzde dğerinin 0 olduğınu gösteren bir değişken vardır. Bu yüzdenin değerini 100 yaparsak ürünü sipariş edebiliriz.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588924b97e07.jpg)

Ürünün değerini değiştirebilmek için POST metodunu repeatera atmamız lazım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658892b2b2a29.jpg)

Şimdi GET methodundaki repeaterda indirim ile alakalı kodu kopyalayım POST methodunun repeater kısmına yapışturalım ve değeri 100 diyerek değiştirelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65889323bb873.jpg)
![resim](https://sibermetin.com/uploads/images/202312/image_750x_658893464a8ed.jpg)

İsteği yolladığımızda bu laboratuvarı da çözmüş olmaktayız. İşte şimdi son laboratuvarımıza geçebiliriz.

## Lab 5: REST URL'sinde Sunucu Tarafı Parametre Kirliliğinden Yararlanma

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658893f883940.jpg)

 Burp aracını açıp giriş kısmından kullanıcı bilgisini girip giriş yapmalıyız fakat sadece administrator kullanıcı adına sahibiz. Şifreyi unuttum kısmına basıp kullanıcı adını girelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588941abdc5b.jpg)

 Kullanıcı adını girdikten sonra mail hesabına giriş yapmak için bir bağlantı gönderildi. Amacımız bu bağlantıyı elde etmek.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588943c23330.jpg)

Burp Suite aracından HTTP history kısmından POST metotu olarak görünen /forgot-password kısmını repeatera yollayıp inceleyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588946646fa4.jpg)

 POST isteğini gönderelim. Maile giriş bağlantısı yolladı.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588949ea314f.jpg)

Bir üst dizine çıkmak için kullanılan ../ ifadeyi kullanıcı adı değeri yaparak istek atalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658894c0d43c9.jpg)

Burada bir hata verdi. Bu hata ile sunucu yoluna girdiğini görebiliriz. ../../../../ ifadesini kullanarak daha da ilerisine gitmeye çalışalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658894e661f42.jpg)

 URL yoluna bazı yaygın API tanımı dosya adları ekleyelim. Örneğin openapi.json.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588950d2f972.jpg)

İstek attıktan sonra API uç noktasını içeren bir hata ile karşılaşıyoruz. Bu hatadan yararlanarak kullanıcı adı değerini “../../v1/users/administrator/field/passwordResetToken#” yapıp istek atalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65889537bd7e4.jpg)

Cevap olarak bize bir token değeri verdi. Biz bu token değerini URL’ye ekleyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_6588955eed72a.jpg)

Karşımıza yeni şifre belirlememiz için bir sayfa çıkıyor. Rastgele bir şifre belirleyelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_65889585a177e.jpg)

 Belirlediğimiz şifre ile administrator kullanıcı adı ile giriş yapalım.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658895ad9820e.jpg)

Admin paneline girelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658895dc71cf4.jpg)

 Admin panelinden Carlos kullanıcısını silelim.

![resim](https://sibermetin.com/uploads/images/202312/image_750x_658895fe709a1.jpg)

API testing çözümlerini böylece tamamlamış olduk.
