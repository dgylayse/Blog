# **[İçeriğin orijinalini görmek için linke tıklayın](https://sibermetin.com/portswigger-write-up-information-disclosure)**

---
![resim](https://sibermetin.com/uploads/images/202311/image_750x_655292e0b3ab8.jpg)

Bu laboratuvarları çözmek için Burp Suite aracına ihtiyacımız var. Burp Suite aracını açtıktan sonra Proxy -> Intercept -> Open browser yolunu izleyerek tarayıcıyı açıp laboratuvar linkine gireceğiz.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528770359c8.jpg)

Hazırsak başlayalım.

## LAB : Information Disclosure in Error Messages

Burp Suite tarayıcısından lab ortamına girelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_655287dd0ae55.jpg)

Burp Suite aracına geri dönüp Target menüsüne girelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528801293cf.jpg)

Product ID=1 olan hostu seçelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_6552882702b74.jpg)

Sağa tıklayıp send to repeater seçeneğini seçelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_6552884e63d9b.jpg)

Repeater menüsüne girelim. Bu sayede istek içerisindeki değerleri değiştirip uygulamanın verdiği yanıtları analiz edebiliriz.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_655288918120c.jpg)

Product ID değerini x yaparak hata vermesini sağlayacağım.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_655288c30e39f.jpg)

Bu hata ile beraber bize apache sürüm bilgisi sızdırıldı.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_6552890588434.jpg)

## LAB : Information Disclosure on Debug Page

Burp Suite tarayıcısından lab ortamına girelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_6552895e43416.jpg)

Sayfa kaynağını incelediğimizde böyle bir şey karşımıza çıkıyor:

![resim](https://sibermetin.com/uploads/images/202311/image_750x_6552899b0c942.jpg)

Bu dizini siteye ekleyince böyle bir sayfayla karşılaşıyoruz.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_655289e5c3499.jpg)

Bunu Burp Suite browser ile açalım.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528a015e856.jpg)

Aşağıdaki sırayı takip ederek Repeater menüsüne gidelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528a5ecce48.jpg)

Buradan istek gönderelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528a8f52813.jpg)

Response (cevap) kısmına gidip SECRET_KEY arayalım. SECRET_KEY aramamızın sebebi:

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528abdec414.jpg)

Ve flag:

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528ae618de7.jpg)

## LAB : Source Code Disclosure Via Backup Files

Burp Suite tarayıcısından lab ortamına girelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528b4378c66.jpg)

Sitenin robotx.txt dizinini inceleyelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528b62ba966.jpg)

/backup adlı bir dizini olduğunu görüyoruz. Bu dizine gidelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528b90d27b5.jpg)

Burp Suite tarayıcısından bu dizinle girelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528bb3ba114.jpg)

Burp Suiteye dönüp /backup olan kısma send to repeater seçeneğine basıp Repeater menüsüne girip istek atacağız.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528bde21915.jpg)

/backup kısmına o dizinde bulduğumuz dosyanın adını girip istek atalım.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528bfc9e5c0.jpg)

Cevap kısmında flagi buluyoruz.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528c1ab7eb8.jpg)

## LAB : Authentication Bypass Via Information Disclosure

Burp Suite tarayıcısından lab ortamına girelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528c5b76a49.jpg)

/admin dizinine gidelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528ca4dde31.jpg)

Proxy -> HTTP history kısmına gidip istek gönderelim.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528dbbaed25.jpg)

Cevap bu şekilde döner:

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528dd9d9fc3.jpg)

İstek attığımız kısımda (request) GET isteğini silip TRACE kullanacağız.
TRACE isteği gönderdiğinizde, sunucu isteği aldığınız gibi size geri gönderir, bu da web sunucusu ve istemci arasındaki iletişimi izlemek ve hata ayıklama yapmak için kullanışlıdır.
TRACE isteği, güvenlik açıklarına neden olabileceği için genellikle güvenlik testlerinde kullanılır. Özellikle sunucu yanıtlarının istemcilere aktarılması sırasında gizli bilgilerin sızmasını önlemek için sunucu tarafında devre dışı bırakılmalıdır.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528e28747d2.jpg)

Cevap kısmında “ X-Custom-IP-Authorization: ” kısmını kopyalayalım.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528e43e8af3.jpg)

Proxy -> Proxy Settings

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528e6fac051.jpg)

Match and replace rules kısmına gelip add tuşuna basalım.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528eaf31b6e.jpg)

Replace kısmına yapıştırıp 127.0.0.1 yazıp OK butonuna bastıktan sonra admin kısmına erişebiliriz.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528edfababd.jpg)

Artık admin panelindeyiz. Carlos kullanıcısını silersek bu lab görevini tamamlamış oluruz.

![resim](https://sibermetin.com/uploads/images/202311/image_750x_65528f088c7a5.jpg)
