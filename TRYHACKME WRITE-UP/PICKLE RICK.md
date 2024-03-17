# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/tryhackme-pickle-rick-write-up)**

---
Herkese merhabalar. Bu yazıda Tryhackme [Pickle Rick](https://tryhackme.com/room/picklerick) odasının çözümünü yaptım. Umarım yararlı olur.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_64873383bae1d.jpg)

Bir makine çözümü yaparken ilk yapmamız gereken nmap ile IP taramasıdır.

Benim ip adresim:

![resim](https://sibermetin.com/uploads/images/202306/image_750x_6487348a09b39.jpg)

    sudo nmap 10.10.146.14

Tarama sonucu ssh ve http portlarının açık olduğu anlaşılıyor. Bir nmap taraması sonucunda http portu açık ise bu ip adresine ait bir site var demektir. Firefox ile ip adresine ait siteye bakalım.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_648736a288690.jpg)

Şimdi de bu sitenin kaynak koduna bakalım.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_6487374aeae4a.jpg)

Kaynak kodunda bize bir kullanıcı adı verdi. Kullanıcı adı verdiğine göre bu sitede login sayfası olmalı. Gobuster aracı ile dizin taraması yapalım.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_6487466bbe481.jpg)

Burada robots.txt dizinini görüyoruz. Öncelikle ona bakalım.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_64874712dae2f.jpg)

 Az önce kullanıcı adı bulmuştuk, muhtemelen bu da şifresidir. login.php dizinine gidip deneyelim.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_6487484aa30f2.jpg)

Şifreyi girdiğimizde böyle bir ekran bizi karşılıyor:

![resim](https://sibermetin.com/uploads/images/202306/image_750x_648748c83fc7c.jpg)

Bu bir komut satırı. Öncelikle ls komutunu kullanalım:

![resim](https://sibermetin.com/uploads/images/202306/image_750x_64874a4c1cb7e.jpg)

İçinde önemli 2 dosya bulduk.

1-  Sup3rS3cretPickl3Ingred.txt

2- clue.txt

Bunları sırasıyla inceleyelim.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_64874bc3f0576.jpg)

İşte ilk flag ortaya çıktı.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_64874fe2750b3.jpg)

Diğer bileşen için dosya sistemine bakın yazıyor.

Aşağıdaki komutta, kök dizine taşınmak, tüm dosyaları uzun biçimde (ls -al) listelemek ve doğru klasörde (pwd) olduğumuzdan emin olmak için çalışma dizinini yazdırmak için bir dizin geçişi yapıyoruz.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_64875211e71fe.jpg)

Burada çok fazla klasör var ancak şu anda ikisi bizim için yararlıdır. Birincisi, her Linux sisteminde kullanıcının bir ev dizinine sahip olduğu homedir. İkincisi, yalnızca yönetici aracılığıyla erişilebilen roottur.

Şimdi home dizinine girmeye çalışalım.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_648755254834e.jpg)

Burada iki klasör olduğunu görüyoruz. Ubuntu işletim sistemindendir, rick klasörünü kurcalayalım.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_648755e152ab6.jpg)

Burada ikinci malzemeler yazıyor.

less komutunu kullanarak ikinci maddeyi açıyoruz.

Not: Dosya adı, boşluk nedeniyle tırnak içindedir.

![resim](https://sibermetin.com/uploads/images/202306/image_750x_64875730b4646.jpg)

Veeee 2. flag.

Şimdi 3. flagı bulmaya çalışalım. Öncelikle buradaki yetkilerimize bakalım:

    sudo -l  

![resim](https://sibermetin.com/uploads/images/202306/image_750x_648758487e4a2.jpg)

Ekran çıktısında (ALL) NOPASSWD: ALL görüyoruz. Bu da herhangi bir komutu şifre kullanmadan çalıştırabileceğimiz anlamına geliyor.

Şimdi sudo komutunu root dosyası ile listeleyelim:

![resim](https://sibermetin.com/uploads/images/202306/image_750x_648759489a8fb.jpg)

3rd.txt dosyasında 3. flag vardır. Flagi bulmak için :

![resim](https://sibermetin.com/uploads/images/202306/image_750x_64875a3784091.jpg)

Ve işte karşımızda son flag.

Oda çözümü bu kadardı. İyi çalışmalar dilerim :)
