# FEX IMAGER KULLANIM KILAVUZU

**[İçeriğin orijinalini görmek için linke tıklayın]([https://medium.com/@aysenurdgyl/chat-gpt-geli%CC%87%C5%9Fti%CC%87ri%CC%87ci%CC%87-moda-ge%C3%A7me-2a1d2e1b48b2](https://medium.com/@aysenurdgyl/fex-imager-kullanim-kilavuzu-e3c0c4ac03a0))**

---

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/0*dLAncYNrEA4qYvSl.jpg)

## İMAJ ALMA

İmaj alma kısaca bir bilgisayarın o andaki tüm C: Sürücüsü ve/veya istenirse diğer sürücülerin bir program aracılığı ile kopyalanarak yedeklenmesi işlemidir. İmaj yükleme ise yedeği alınan bir sürücü alanının bilgisayara veya istenilen yere tekrar yüklenmesi işlemidir.

## FEX IMAGER NEDİR?

FEX Imager, karma kimlik doğrulaması ile bit bazında adli görüntü(imaj) çıkarabilen bir adli bilişim ücretsiz bir yazılımıdır. Fiziksel, mantıksal, dosya ve klasörler, adli imaj ve uzak cihazları alabilir. DD/RAW, E01, L01 formatlarını desteklemektedir. Cihaz sektör boyutunu 512, 2048 veya 4096 sektör boyutunda alacak şekilde ayarlanabilir. FEX Imager, HPA/DCO alanlarının alınmasını desteklememektedir.

**1. Raw ( dd ):** İmaj alma işlemi esnasında herhangi bir sıkıştırma uygulanmaz, elde edilecek imaj dosyası kaynak ile aynı boyuttadır. Ayrıca imaj dosyası içerisinde yalnızca ham veri bulunur, herhangi bir metadata verisi yer almaz.

**2. E01:** Veri dosyaya yazılırken bloklara bölünür ve her bloğa ait hesaplanan checksum değeri verinin arkasına yazılır. Dolayısıyla imaj dosyası yalnızca veriyi değil, metadata ve doğrulama kodlarını da içerir.

Fex imager aracımızı tanıyalım:

## 1. ARAYÜZ

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*-a3J7q3CJMwn5g13Kn-EWQ.png)

Ara yüzünde neler olduğuna bakalım:

**Source:** Kaynaktır yani imajı alınacak verileri buradan yüklüyoruz.

**Imagine Entire Drive:** Cihaz ya da diskin tamamı anlamına gelir.

**Start Sector:** Sektör başlangıcıdır.

**Progress:** Gelişim bize sonucu gösterir.

**Sector Size:** Sektör büyüklüğünü ifade eder.

**End Sector:** Sektör bitişidir.

**Destination:** Hedef

## 2. MENÜLER

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*xhBZXg-pj4OYpf25cdqOHQ.png)

Programın sol tarafında visit website, help, about, exit seçenekleri bulunuyor.

**Visit Website:** Bizi getdataforensics sitesine yönlendiriyor.

**Help:** Fex imagerin kullanım kılavuzunu görebiliyoruz.

**About:** Programın hangi versiyonunu indirdik gibi bize bilgileri gösteriyor.

**Exit:** Programdan çıkışı ifade ediyor.

Programın sağ tarafında kaynaklar bulunuyor. Fiziksel Sürücü, mantıksal Sürücü, bir bölümdeki dosya veya klasörler, hazır bir imaj, Uzak sürücü gibi seçenekleri bulunuyor. Fiziksel ve mantıksal sürücünün aktif olması için programı yönetici olarak çalıştırmalıyız.

## 3. FİZİKSEL SÜRÜCÜ

Fiziksel diskin tamamının kopyalanmasıdır. İmaj olarak en çok tercih edilen denebilir. Cihaz seçimi aşağıdaki gibidir. Biz hard disk 1 ‘i seçtik.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*v3MsFFS3sOcEVLgeDiT1LA.png)

**Add Image:** İmaj eklenecek kısımdır.

**Add RAID:** RAID eklenecek kısımdır.

**Remote:** Uzaktan erişim seçeneğidir.

**Remove:** Seçtiğimiz işlemleri kaldırmak için kullanılır.

**Refresh:** Yenileme için buton

**Label:** Etiketlemek

**Size:** Boyuttur.

**Fs:** Sürücüdeki dosya sistemidir. Örnek verecek olursak FAT, HFS, APFS gibi.

**Device:** Ekranda görüntülenen aygıttır.

**Type:** Sürücünün bilgisayara bağlanma şeklini açıklar.

Ok tuşuna bastıktan sonra bize hard disk 1 ile ilgili bilgiler çıkıyor. Burada sektör başlangıcını ayarlayabiliriz.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Oc0vZh1hmaqB7tdDu7Xc3A.png)

Destination butonuna basıp bir sonraki aşamaya geçtik.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*RVanIe1PrdFymp8eRMFGWA.png)

Bu aşamada imaj tipini, dosya adını, klasörü, alacağımız hash türlerini seçebiliyoruz. Vaka ayrıntıları kısmında vaka adını, inceleyen kişiyi, kanıt numarasını, notlar gibi bilgileri yazıyoruz. Start tuşuna basıp bir sonraki işleme geçiyoruz.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*k5mvu6lsoHx-43HjmB3dCg.png)

Burada işlemin sona erdiği görülmektedir ama daha önce imaj almadığımız için herhangi bir eşleştirme olmadı. Sonuç sayfasındaki bazı ifadelere bakalım:

**Verification finished:** Doğrulama işlemi bitişini belirtir.

**Verification started:** Doğrulama işlemi başlangıç kısmıdır.

**Elapse time:** Geçen zamanı gösterir.

## 4. MANTIKSAL İMAJ

Belirli alandaki verilerin kopyasını aldığımız imaj türüdür.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*U2o6-szge6n_d51t56tlOg.png)

## 5. DOSYA VE KLASÖRLER

İmajı alınacak dosya veya klasörün ekleneceği kısımdır.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*74iMeX7_pqBL6qCPsxIwlg.png)
![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*xtnihgnfwuQse3ZZdf1BlQ.png)
![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*YDXN8K4D9xJaLsaVgpVNug.png)

## 6. ADLİ İMAJ

Bir imajın tekrar imajının alınmasıdır. Kayıtlı olan imaj yüklenerek işleme devam edilir. Ayrıca buna convert işlemi de denebilir. Örnek olarak dd bir imajı sıkıştırmak için e01 imaj formatına dönüştürmektir.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*HHrZqnS7LNFGAGA4KFkA1w.png)

## 7. UZAKTAN BAĞLANTI

Uzaktan bağlantı ile imaj alma işlemidir. Gerekli yerler doldurulur ve işleme devam edilir.

![resim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*HXv2OiIlW4cvE8Ho3HJQAQ.png)

Connect kısmında bağlantı bilgileri girilir. Speed test hız testini görebiliyoruz.

**Checksum Network Packets:** Doğrulama toplamı ağ paketleri

**Port:** Bağlanılacak olan port bilgisi verilir.

**Use Compression:** Sıkıştırma kullanılan kısım.
