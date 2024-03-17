# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/kriptografi)**

---

Bu yazımda size şifreleme bilimi olan kriptografi hakkında bilgi vereceğim. Çok önemli bir konu olmakla birlikte CTF'lerde önemli bir yer kaplıyor. İyi okumalar.

![resim](https://sibermetin.com/uploads/images/202303/image_750x_6426c232d92d1.jpg)

*Yazımıza geçmeden önce bazı kavramların kısaca ne olduğundan bahsedip yeri gelince daha detayları açıklayacağım.*

***Düz Metin (Plain Text):*** Bir metnin henüz şifrelenmemiş halidir.

***Şifreli Metin (Cipher Text):*** Düz bir metni şifreleme algoritmasını kullanarak şifreli bir hale gelmesine denir.

***Şifreleme (Encryption):*** Bir şifre kullanarak verileri şifreli metine dönüştürür.

***Kodlama (Encoding):*** Şifreleme ile aynı şey değildir. Bir veri temsili biçimidir.

***Anahtar (Key):*** Kriptografik verileri kodlayan ve kodunu çözebilen sayı veya harflerden oluşan bilgi parçasıdır.

***Parola (Passhprase):*** Anahtar ile aynı şey değildir. Parola anahtarı korur.

***Asimetrik Şifreleme (Asymmetric Encryption):*** İki anahtar kullanılan şifreleme yöntemidir.

***Simetrik Şifreleme (Symmetric Encryption):*** Tek anahtar kullanılan şifreleme yöntemidir.

***Kaba Kuvvet (Brute Force):*** Tüm permütasyonları tek tek kullanarak kriptografiye saldırma yöntemidir.

***Kriptanaliz (Cryptanalysis):*** Şifrelenmiş metinlerin çözümünü araştıran kriptoloji dalıdır.

***Kriptoloji (Cryptology):*** Şifreleme bilimidir.

***Alice ve Bob:*** Genellikle iletişim kurmak isteyen iki kişiyi temsil eder. Alfabedeki  A ve B harfini temsil ettiği için bu isimler kullanılır.

## KRİPTOGRAFİ NEDİR?

Düz bir metini istenilmeyen kişiler tarafından anlaşılmaması için çeşitli şifreleme algoritmaları kullanılarak şifreli bir metine dönüştüren şifreleme bilimidir. Kriptografi, verilerinin güvenliğini arttırmak için kullanılan bir yöntemdir. Bu bilimle uğraşanlara Kriptograf denir.

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6234856ec539a.jpg)

Kriptografi ve kriptanaliz birbirine zıttır. Kriptograflar yeni şifreleme algoritmaları üretirken Kriptanalistlerde amaç şifreleri kırmaktır.

## KRİPTOGRAFİ NERELERDE KULLANILIR?

- Veri hırsızlığını ve değişikliğini önlemek,

- Kullanıcı kimliğini doğrulamak,

- Web trafiğinin güvenliğini sağlamak,

- Telif hakkıyla korunan yazılım kodunun güvenliğini sağlamak vs için kullanılır.

Kriptografi; askeri haberleşme, elektronik ticaret, dijital paralar, kartlı ödeme sistemleri ve bilgisayar ağları gibi alanlarda kullanılır.

Unutulmamalıdır ki kırılmayacak şifre yoktur. kimi şifreler bir ayda kimi şifreler bir yılda kimisi ise bin yılda kırılır. Bizler şifreleri karmaşıklaştırıp daha zor hale getirerek kırılma süresini arttırırız.

## İLK KRİPTOGRAFİ ÖRNEKLERİ

Kriptografi, ismini Yunanca "gizli" anlamına gelen kryptos ve "yazı" anlamına gelen graphein kelimelerinin birleşiminden almıştır.

İlk kriptografi örnekleri;

**->** Kriptografik obje olarak bilinen Irak'ta 1600'lü yıllara ait bir toprak küpüdür.

**->** Mısır ve Antik Çin mesajları grafik imgelerle yazarlardı.

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6235df7e1dd92.jpg)

**->** Hint medeniyetinde kelimelerin ilk harfi kelimelerin sonuna taşıyıp "-ay" ekini ekleyerek şifrelerlermiş.

Örneğin; Siber Metin **- - - - ->** İbersay Etinmay

**->** Persler "Şah Yazısı" ve "Raz-ı-Seheriye" adlı yöntemler geliştirmişlerdir.

**->** M.Ö. 700'lü yıllarda Spartalar askeri haberleşme için SCYTALE adlı sopalara sarılan şeritlere mesaj yazıyorlardı.

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6235de5be2fc4.jpg)

**->** M.Ö. 600'lü yıllarda İbranicede atbaş adlı alfabenin son harfiyle ilk harfinin yerlerini değiştirilmesine dayalı bir şifreleme yapıyorlarmış.

Örneğin; MERHABA **- - - - ->** A B C D E **.........**  V W X Y Z **- - - - ->** NVISZYZ
..............................................Z Y X W V **.........**  A B C D E...............................

## KRİPTOGRAFİ TÜRLERİ

İki çeşit kriptografi vardır.

**1-** Simetrik Şifreleme

**2-** Asimetrik Şifreleme

### **1- SİMETRİK ŞİFRELEME**

Simetrik şifreleme, bir veriyi şifrelemek ve verinin şifresini çözmek için yalnızca bir anahtar kullanan şifreleme türüdür. Simetrik şifreleme asimetrik şifrelemeden daha hızlıdır. AES, RC4, RC5, RC6, DES ve Blowfish simetrik şifrelemelerdir. En çok kullanılanlar ise AES-128, AES-192 ve AES-256.

![resim](https://sibermetin.com/uploads/images/202203/image_750x_623625fa6e6e6.jpg)

### **2- ASİMETRİK ŞİFRELEME**

Asimetrik şifreleme, bir veriyi şifrelemek ve verinin şifresini çözmek için açık ve özel olmak üzere iki anahtar kullanan şifreleme türüdür. Açık anahtar veriyi şifreler, özel anahtar ise şifreyi çözer. Asimetrik şifreleme simetrik şifrelemeye göre daha karmaşık bir yapıya sahip ve aynı zamanda daha güvenilirdir. Asimetrik şifreleme dijital imzalarda, SSL/TLS , S/MINE, SSH ve OpenPGP gibi protokollerde kullanılır.

![resim](https://sibermetin.com/uploads/images/202203/image_750x_62361b60ea8b1.jpg)

*Şimdi bazı şifreleme çeşitlerini inceliyelim.*

#### SEZAR ŞİFRESİ

MÖ 50-60 yıllarında Roma İmparatoru Jül Sezar, devlet haberleşmelerinde kendi adıyla anılan sezar şifreleme yöntemini kullanmıştır. Sezar şifreleme yöntemi , bir metindeki her harfin kendisinden gelen üçüncü harf ile değiştirilmesiyle yapılan bir şifrelemedir.

Örneğin; ŞİFRE **----->** ÜLHTĞ

![resim](https://sibermetin.com/uploads/images/202203/image_750x_62348593387e1.jpg)

 Harflerin yerlerini değiştirerek şifreleme yapmak hiç de güvenilir bir yöntem değildir. Her dilde bir metin içinde en çok kullanılan harfler vardır. Sezar şifresi ve buna benzeyen şifreleme algoritmalarında en çok tekrar harfleri karşılaştırarak şifreyi çözebiliriz.

#### BASİT MONOALPHABETİC DEĞİŞİM

Bu şifrelemede her harf bir harf ile yer değiştirir.

Örneğin;   Alfabe     A     B      C     Ç    D   ....    V   Y    Z

                Anahtar    G     O      A      L    Ü   ....    T    I     S

Toplamda 29! farklı anahtar olması mümkün. Fakat  Frekans Analizi ile de kolayca kırılabilir.

#### FREKANS ANALİZİ

9.yüzyılda Al-Kindi önermiştir. Dildeki tekrara bağlı bir analizdir. Sezar şifresinde bahsettiğimiz analizdir. Bir dil için yazılmış uzun bir yazıda hangi harfin kaç kere tekrarlandığına bakarak ederek  o dilde en çok kullanılan harfleri analiz eder.

Örneğin; İngilizcede en çok kullanılan harf E ve daha sonra T harfidir. Şifreli metin uzunsa orada en çok kullanılan harf E'ye denk gelir. İkinci olarak en çok tekrar eden harf T'ye denk gelir. Ve bu şekilde devam eder.

İngilizcede en çok kullanılan harfler grafikte gösterildiği gibidir:

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6238cfee280e7.jpg)

Türkçede en çok kullanılan harfler grafikte gösterildiği gibidir:

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6238d403b5932.jpg)

#### ENİGMA

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6238c820c9079.jpg)

Enigma elektrik-mekanik çarklı bir şifreleme makinesidir. Daha çok bankacılık ve askeri alanlarda kullanılmıştır. 2. Dünya savaşında 200.000'den fazla enigma makineleri kullanılmıştır. Enigmanın çalışma mekanizması, dönen silindir ile düz metin her harfi yeni permütasyonla şifrelenmesi şeklindedir. Sonradan İngiltere'de 7000 kişinin çabaları sonucunda Enigma ile şifrelenen metinler çözülmüştür. Ve bunun sonucunda savaşın bitmesinde büyük bir rol almıştır.

#### VİGENERE ŞİFRELEME

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6238d2d80f3fc.jpg)

Vigenere şifrelemesi sezar şifrelemesinin daha karmaşık halidir. Matematiksel olarak şöyle ifade edelim:

**->** m pozitif bir tam sayıdır,

P=C=(Z26)n, ve K(k1,k2,...,km), anahtarı ile aşağıdaki şekilde tanımlanır:

**->** Şifreleme:

- Ek(p1,p2...pm) = (p1+k1,p2+k2...pm+km) (mod 26)

**->** Şifre Çözme:

- Dk(c1,c2 ... cm) = (c1-k1,c2-k2 ... cm-km) (mod 26)

Bunu bir elma örneği ile pekiştirelim.

p=   C  R  Y  P  T  O  G  R  A  P  H  Y

k=   E  L  M  A  E  L  M  A  E  L  M  A

C=  G  B  K  P  X  Z  S  R  E  A  T  Y  

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6238dddf97eab.jpg)
![resim](https://sibermetin.com/uploads/images/202203/image_750x_6238df08e8abc.jpg)
![resim](https://sibermetin.com/uploads/images/202203/image_750x_6238dfb4ab929.jpg)
![resim](https://sibermetin.com/uploads/images/202203/image_750x_6238e046226ac.jpg)

#### HASH

Hash bir veriyi şifreleyip okunamaz hale getiren bir algoritmadır. Hash değeri her veriye özgüdür. İki verinin hash değeri aynı olamaz. SHA-1, SHA,2, MD5, CRC32 hash algoritmalarına örnektir. Bir verinin hash değeri tüm hash algoritmalarında farklı çıkar.

Örneğin; password kelimesini inceleyelim

SHA-1: 5BAA61E4C9B93F3F0862250B6CF8331B7EE68FD8

SHA-2: 5E884898DA28047151D0E56F8DC6292773603D0D6AABBDD62A11EF721D1542D8

MD5: 5F4DCC3B5AA765D61D8327DEB882CF99

CRC32: BBEDA74F

![resim](https://sibermetin.com/uploads/images/202203/image_750x_6234858f37851.jpg)

## ONLİNE ŞİFRE ÇÖZÜCÜLER

**Base64:** aHRocDoc3d 3jdfvjujUGE79nZXQ=

(Sonundaki eşittir sembolünden bunun base64 ile çözülebildiğini anlayabilirsiniz)

**Hexadecimal (Ondalık):**  90349085048956896739ı67

**Octal (Sekizli):** 167 135 103 123 177 134

**Binary (İkili):** 010010110101010101001110000111101001011001010010

Gibi şifrelenmiş yazıları bazı online şifre kırıcı servisler ile şifreyi kırıp verileri elde edebilirsiniz.

### ONLİNE ŞİFRE OLUŞTURMA VE KIRMA SİTELERİNDEN BAZILARI

**->** [Cyber Chef](https://gchq.github.io/CyberChef/)

**->** [vincentcheung.ca](http://www.vincentcheung.ca/jsencryption)

**->** [dcode.fr](https://www.dcode.fr/cipher-identifier)

**->** [crackstation.net](https://crackstation.net)

**->** [encodertool.com](http://encodertool.com/)

**->** [ddecode.com](http://ddecode.com/)

**->** [online-toolz](http://www.online-toolz.com/tools/text-encryption-decryption.php?ln=tr)

**->** [tool.chinaz](http://tool.chinaz.com/tools/scriptencode.aspx)

**->** [hat.sh](https://hat.sh/)

Kriptografiyi daha yakından tanımak isterseniz size sadece kriptografi çalışabileceğiniz güzel bir site buraya bırakıyorum.

**->** [bitdegree](https://www.bitdegree.org/)

### KRİPTOGRAFİ İLE ALAKALI FİLM ÖNERİSİ

**->** Enigma

**->** Cryptogram

**->** The Davinci Code

**->** Cube Zero

**->** Cube

**->** Cube2

**->** Zodiac

**->** A Beautiful Mind

**->** The Imitation Game

### KRİPTOGRAFİ İLE ALAKALI KİTAP ÖNERİSİ

**->** Kriptografi

**->** Bunu Ancak Dr. Ecco Çözer

**->** Dr. Ecco'nun Şaşırtıcı Serüvenleri

**->** Enigma

**->** The Eleventh Hour

**->** Daemon Serisi

**->** Homeland

**->** National Treasure
