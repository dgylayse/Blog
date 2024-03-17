# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/tshark)**

---

Bu yazı sizlere Tshark hakkında bilgi verecektir. İyi okumalar.

![resim](https://sibermetin.com/uploads/images/202208/image_750x_62f934e027175.jpg)

## TSHARK NEDİR?

Tshark bir Adli Bilişim Uzmanının bilmesi gereken bir araçtır.

Tshark, açık kaynak kodlu bir sniffer aracıdır. Wireshark tarafından geliştirilmiştir. .pcap dosyalarını okuyabilir. Tcpdump ile benzer çalışma prensibine sahiptir fakat Tshark’ın Tcpdump’tan farklı olarak bazı güçlü kod çözücüleri ve filtreleri vardır.

Bir avantaj olarak, bir ağda olası bir saldırı işareti olan olağandışı miktarda veri trafiği varsa, Tshark çok geç olmadan bunu anlamamıza yardımcı olabilir ve saldırı sonlandırılabilir.

Tshark, Wireshark ile aynı amaca hizmet eden bir analiz programıdır. İkisi de ağda olup biteni anlamamızı sağlar. Bir diğer deyişle ağdaki paketleri dinler ve yerel ağdaki ağ trafiğini yakalarlar.

Tshark, Wireshark’ın komut satırı versiyonudur. Wireshark arayüze sahip iken Tshark terminalde çalışır. Wireshark’ta bulunan çoğu özellik Tshark’ta da vardır.

## WİRESHARK VARKEN NEDEN TSHARK?

Wireshark, grafik arayüzüne sahip bu da CPU’yu biraz yoruyor. CPU biraz yorulduğundan bazı durumlarda paketleri yakalarken kayıplar yaşanıyor. Böyle sıkıntılar yaşamamak için ve kaynakları daha optimize bir şekilde kullanabilmek için Trafik Analiz Uzmanları tarafından genellikle terminal üzerinden paket yakalamak için tercih ediliyor.

Sonuç olarak Tshark, Wireshark’a göre daha performanslı ve komut satırı esnekliği olduğundan tercih edilir.

### Tshark Kurulumu

**sudo apt-get** **install tshark**

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e2112b03079.jpg)

Tshark arayüzünü kontrol etmek için:

**tshark** **-D**

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e2113055f2f.jpg)

Tshark yardım menüsü:

**tshark** **-h**

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e211366aa49.jpg)

Tshark birçok parametreye sahiptir. Hiçbir parametreyi kullanmadan tshark çalıştırılırsa ilk aktif ağ birimi üzerinden geçen trafiği bize verir.

Örnek olsun diye googleye ping atalım ve tsharkta inceleyelim:

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e2113d0afe9.jpg)

Eğer çıktıları ekranda değil de bir dosya içerisinde görmek istiyorsanız:

**tshark -w** **dosya_ismi**

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e211423fb9c.jpg)

Şimdi bazı parametreleri inceleyelim:

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e21147afcbf.jpg)

 **-i**  bulunduğumuz ağı canlı olarak incelememizi sağlıyor.

 **-w** çıktıyı dosya olarak incelememizi sağlıyor.

 **-V**  detaylı çıktı almamızı sağlıyor.

 ![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e2114cd0031.jpg)

 **-r**  ile incelenecek dosyayı okur.

**-c**  ile kaç adet paket inceleneceğini seçebiliriz.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e2115356a4c.jpg)

 **-f**  ile belirli bir portun ağ trafiğini yakalayabiliriz.

Ayrıca eğer -f parametresi -i parametresinden önce kullanılırsa tüm ağ arayüzlerini kapsamış olur.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e2115ab20c8.jpg)

 -T  parametresi ile çıktıyı istediğimiz şekil ile görebiliriz.

 -T x  ile seçeneklerin neler olduğunu görebiliriz.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e2116152738.jpg)

Örnek kullanım olarak burada çıktıyı pdml şeklinde vermesini  sağladık. PDML (Packet Details Mark-Up Language) yani paket detaylı işaretleme dilidir. Pdml ayrıntılı bir çıktı verir.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e211670cefc.jpg)

Burada Wireshark tarafından tanıtılan görüntüleme methodunu kullandık. Böyle yaparak direkt sadece GET isteklerine ulaşabiliriz.

**tshark broadcast** ile Broadcast paketlerini yakalayabiliriz.

**tshark ip6** ile Ipv6 paketlerini yakalayabiliriz.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e2116d368f6.jpg)

 **tshark -r dosya_adi -q -z io,phs**  yakalanan veya kaydedilen trafiğin istatiğini verir.
