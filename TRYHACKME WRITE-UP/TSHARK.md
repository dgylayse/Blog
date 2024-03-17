# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/tryhackme-tshark-wiretup)**

---

[Tryhackme Tshark](https://tryhackme.com/room/tshark) odanın makine çözümü hakkında bir yazı. İyi çalışmalar.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e15b22579f7.jpg)

## GÖREV 2

### SORU 1 : dns.cap dosyasında kaç paket var?

Öncelikle görev dosyasını indirelim.

Terminale yazacağımız kod:

 **tshark -r** **dns.cap**

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e167dced1dc.jpg)

#### CEVAP: 38

### SORU 2: Yakalamada kaç A kaydı var? (Yanıtlar dahil)

Terminale yazacağımız kod:

 **tshark -r** **dns.cap -Y** **"dns.qry.type** **== 1" | wc l**  

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e16988ec21f.jpg)

### CEVAP: 6

SORU 3: En çok hangi A kaydı vardı?

Terminale yazacağımız kod:

 **tshark -r** **dns.cap -Y** **"dns.qry.type** **== 1" -T** **fields -e** **dns.qry.name**

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e16b81c0c74.jpg)

#### CEVAP: GRIMM.utelsystems.local

## GÖREV 3

### SORU 1: Bu yakalamada kaç paket var?

Öncelikle görev dosyasını indirelim.

Terminale yazacağımız kod:

 **tshark -r** **dnsexfil.pcap**

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e173cc74e7f.jpg)
![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e173e76603f.jpg)

#### CEVAP: 125

### SORU 2: Bu pcap'ta kaç DNS sorgusu var? (Cevaplar değil!)

Terminale yazacağımız kod:

 **tshark -r** **dnsexfil.pcap** **dns.flags.response == 0**

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e175ff9c8f3.jpg)
![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e1761fe305e.jpg)

Toplamda 56 tane DNS sorgusu vardır.

#### CEVAP: 56

### SORU 3: Şüpheli sorguların DNS işlem kimliği (onaltılık olarak) nedir?

Bu soruyu wireshark ile çözeceğiz. Wiresharkı açalım. Buradan ICMP protokolü olan 98'e tıklayalım bu paket şüpheli gözüküyor. Bu paketin içindeki alan adı kısmına girelim.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e17825f113d.jpg)

#### CEVAP: 0xbeef

### SORU 4: DNS sorgularından çıkarılan dize nedir?

Dikkatli bakarsak her DNS'nin ilk harfi farklı gerisi aynıdır. Bu tüm harfleri birleştirelim.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e179fd50c6c.jpg)

#### CEVAP: MZWGCZ33ORUDC427NFZV65BQOVTWQX3XNF2GQMDVG5PXI43IGRZGWIL5

### SORU 5: Bayrak nedir?

Önceki soruda bulduğumuz bir hash değeridir. Bu hash değeri base32 ile şifrelenmiştir. Şimdi bu şifreyi kıralım.

![resim](https://sibermetin.com/uploads/images/202207/image_750x_62e17ae5cfc7b.jpg)

#### CEVAP: flag{th1s_is_t0ugh_with0u7_tsh4rk!}

Tshark hakkında daha fazla bilgi edinmek isterseniz [yazıma](https://sibermetin.com/tshar)  bakabilirsiniz.

İyi çalışmalar...
