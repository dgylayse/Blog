# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/tryhackme-brooklyn-nine-nine-write-up)**

---
Merhabalar bu yazıda [Brooklyn Nine Nine](https://tryhackme.com/room/brooklynninenine) zafiyetli makinenin çözümünü ele aldım. Detaylı bir açıklama yaptım iyi çalışmalar dilerim :)

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e250aa8d207.jpg)

Makinemizi başlatıp ip adresimizi öğrenelim.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e2511677845.jpg)

Nmap taraması ile açık portlarını tespit edelim.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e251470340f.jpg)
![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e251564fe4b.jpg)

80 portu yani http açık olduğuna göre bu ip adresine ait bir web sayfası vardır.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e25f31c6cac.jpg)

Böyle düz bir sayfa karşımıza çıktı. Kaynak koduna bakalım bir ipucu olabilir.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e25ebd14547.jpg)

Yorum satırı : Steganografiyi hiç duydun mu?

Steganografi veri gizleme bilimidir. Bu konu hakkında bilginiz yoksa [STEGANOGRAFİ - Siber İçerik Platformu](https://sibermetin.com/steganografi) yazımda detaylıca bakabilirsiniz.

Şimdi de 21.porttaki ftp açığını inceleyelim. Kullanıcı adı nmap taraması yaparken görmüştük Anonymous ve şifreye gerek yok.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e25ed5a4665.jpg)

İçinde ne olduğunu görmek için ls komutunu yazalım. lcd komutunu kullanarak makinemin dizinini değiştirdim ve buradaki txt dosyasını get ile indirdiğimde Pictures klasörüne inecektir.

**lcd :** FTP ortamından çıkmadan, kendi makinanızda dizin değiştirmenizi olanaklı kılar.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e26207d807e.jpg)

Dosya indi :)

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e263d3a3278.jpg)
![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e264e258105.jpg)
![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e264f25e5ee.jpg)

Şimdi hydra aracını kullanarak Jake'nin şifresini kıralım ve Holt'u çıldırtalım :D

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e26576ae6f9.jpg)

Şifresi gerçekten de çok güçlüymüş :DDD

ssh ile Jake'nin makinesine erişme vakti.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e265e00f94e.jpg)

ls yapıp içine baktığımızda bir şey yok. cd .. komutu ile önceki dizine gelip ls yazdığımızda 3 tane kullanıcı görüyoruz. Buradan yetki yükseltme yapmalıyız ve önce sudo -l kullanarak hangi yetkilere sahip olduğumuza bakacağız.

Süper herhangi bir şifreye ihtiyacımız yok (NOPASSWD) . less komutuyla nasıl yetki yükseltebileceğimize bakalım.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e265f62ebf8.jpg)

Yetki yükseltmek için yardımcı olabilecek  gerçekten harika bir kaynak :))

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e266c97a110.jpg)

usr/bin/less kısmındaki less komutunu kullanacağız. Arama yerine less yazıp Sudo butonuna basmamız yeterli :)

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e26713979bd.jpg)

İlk komutu terminale yapıştıralım.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e267756f2b0.jpg)

Bize böyle bir çıktı verecek. 2. komutu en altta yapıştırıp çıkalım.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e267c83d176.jpg)

root.txt dosyasına ulaşabilmemiz için root klasörüne gitmeliyiz.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e2680f3c8b5.jpg)

Geriye kaldı user.txt dosyamız. home dizinine gidip ls yazarak kullanıcıların olduğu kısmına gidelim. Önceki notta Holt'u kızdırmaktan bahsediyordu. Bu yüzden Holt kullanıcısına girelim. Evet user.txt buradaymış.

![resim](https://sibermetin.com/uploads/images/202308/image_750x_64e2687a5cc61.jpg)

Çözümün sonuna geldik. Umarım sevgili okurlar size bu yazıyla bir şeyler katabilmişimdir. İyi çalışmalar dilerim :)))
