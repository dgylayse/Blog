# NMAP

**[İçeriğin orijinalini görmek için linke tıklayın](https://medium.com/@aysenurdgyl/nmap-1bdc12bcde3b)**

---

![resim](https://miro.medium.com/v2/resize:fit:616/format:webp/0*e16qFLM1HFmRnxSL.jpg)

Siber saldırıları analiz edebilmek amacıyla 7 aşamadan oluşan Cyber Kill Chain modeli bulunmaktadır. Aşamalar;

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/0*s8Lq4b9317hGMuzy.png)

- Reconnaissance ( keşif )
- Weaponization ( silahlanma )
- Delivery ( iletme )
- Exploitation ( sömürme )
- Installation ( yükleme )
- Command and control, c2 ( komuta kontrol )
- Actions on objectives ( eylem )

Keşif siber saldırı öncesi en önemli aşamadır. Bu aşamada genel tarama yapılır veya belirli bir hedefe yönelik olarak bilgi toplanır.

Keşif aşamasında kullanılan en önemli araçlardan biridir Nmap.

Nmap aracı ile hedef alınan sistemin port bilgilerine, çalışan servislerine ve versiyonlarına, işletim sistemi bilgilerine vs bilgilere ulaşabiliriz.

Şimdi nmap’ın çalışma mantığına geçelim.

Nmapı parametresiz şekilde taratırsak, nmap bize popüler olan bin portu tarar ve hangi çalışan servisler varsa bize çıktı olarak verir. Bu yüzden parametre belirterek tarama yaparsak daha fazla ve iyi sonuçlar alırız.

    nmap <ip adresi>

Hedef makinemizin ip adresi 10.10.228.244 olsun.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*wlygNteuF3aAhWi5Bs8gFQ.png)

65535 portun hepsini taramak için ise -p- parametresini kullanmalıyız.

    nmap -p- <ip adresi>

Tüm portlar yerine belirli bir aralıktaki portları taramak istersen örneğin 20 ile 100 arasındaki portları taramak istersek :

    nmap -p 20-100 <ip adresi>

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*JZ0ZW81UYj-JN682X4Jq1Q.png)

Sadece istediğimiz portları tararken yazdığımız portların arasına virgül koymamız yeterlidir. Örneğin sadece 21,22,80 portunu taramak istersek:

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*XA7yClsUFf4_ib8BUvsQ_w.png)

Hedef sistemde çalışan servis versiyonları zafiyet tespiti için önemli bir bilgidir. Bu versiyon bilgilerine -sV parametresi ile ulaşırız.

    nmap -sV <ip adresi>

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*_yucfX1Umhi_NmjgJsqmHg.png)

Tüm portların versiyon bilgilerini öğrenmek biraz zaman alır. Bu yüzden belirli bir portun versiyonunu alırken örneğin 21 ile 80'nin:

    nmap -sV -p 21,80 <ip adresi>

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*hRe6YEjX12_k8cBebKO7nQ.png)

Hedef sistemin işletim sistem bilgisi ve sürüm bilgisini öğrenmek için -O parametresini kullanarak öğrenebiliriz.

    nmap -O <ip adresi>

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*u2-6Vk0jqW-85YxjQ4LY4Q.png)

Daha detaylı taramalar yapmak için -sV, -O, -p- parametrelerini aynı anda kullanabiliriz.

    nmap -sV -O -p- <ip adresi>

Yukarıdaki üç parametre yerine direkt -A parametresini kullanarak da detaylı bir tarama yapabiliriz. -A parametresi ile taramaya agresif tarama denir.

    nmap -A <ip adresi>

![resim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*q6mMiKhP15cZ01JyAYScIg.png)

Son olarak -sC parametresinden bahsedeceğim. -sC parametresi bir script taramasıdır. Hedef sistemde güvenlik açıkları tespit eder.

Nmap parametreleri hakkında daha fazla bilgi almak istiyorsanız terminale:

    nmap -h

yazmanız yeterli.

Yazımı okuduğunuz için teşekkürler. İyi çalışmalar.
