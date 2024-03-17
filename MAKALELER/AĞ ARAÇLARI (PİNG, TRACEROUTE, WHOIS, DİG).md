# AĞ ARAÇLARI (PİNG, TRACEROUTE, WHOIS, DİG)

**[İçeriğin orijinalini görmek için linke tıklayın](https://medium.com/@aysenurdgyl/a%C4%9F-ara%C3%A7lari-pi%CC%87ng-traceroute-whois-di%CC%87g-4ae600d2a286)**

---

Bu yazımda basit komut satırı ağ araçlarına kısaca değineceğim.

![resim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*qG2NJ2YQ0p8vSxik3-_f6Q.png)

## 1- PİNG

Ping başka bir kaynağa bağlantının mümkün olup olmadığını test eder. Tanım olarak bir bilgisayardan alınan veri paketlerini ilgili sunucuya iletilmesinde geçen süreye verilen ad diyebiliriz.

cmd komut istemine ya da linux terminaline;

    ping < IP adresi > 
ya da

    ping < web sitesinin adı >

şeklinde yazarsak paketlerin iletimi sırasında geçen süreyi verecektir.

Bunu bir örnekle göstermek istiyorum.

Google bir ping atalım.

![resim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*bWMIy7UWCFJouGUr3yYzJg.png)

Burada google web sitesinin adı ile ping attık. IP adresi ile de atalım.

*Google ip adresleri :* 8.8.8.8 , 8.8.4.4

![resim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*NdI7Ek588CGF4E8Fhfbn0g.png)

Ping miktarı arttıkça “lag” adı verilen gecikmeler yaşanır. Bu gecikmeler bazen her ne kadar milisaniyelik gecikmeler de olsa çevrimiçi oyunlarda çok rahatsız edici olabiliyor.

## 2- TRACEROUTE

Türkçe sözcük anlamı olarak iz yolu anlamına gelir. Genel olarak tanımı bir sunucuya ulaşırken gönderilen paketlerin geçtiği yolları gösterir.

Akılda kalması için şöyle düşünebilirsiniz. Route; rota, yol anlamlarına gelmektedir. Biz herhangi bir sunucuya istek yolladığımızda oraya ulaşana kadar nerelerden geçtiğini gösterir.

Linux ile :

    traceroute <IP adresi ya da web sitesi adı>

CMD komut satırı ile:

    tracert <IP adresi ya da web sitesi adı>

CMD komut satırı ile google istek attım toplam 11 yerden geçmiş:

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*lGd2V16A1OTWOfB2lstL5Q.png)

Aynı zamanda her geçtiği yerde ne kadar süre harcadığını da gösteriyor.

## 3- WHOIS

Whois sorgusu ile bir sitenin kayıt ve bitiş süresini, host edildiği firmanın name server bilgilerini verir. Bir siteyi whois sorgusuyla sorgulatırsak o domain kimin adına kayıtlı mail adresi, telefon numarası, domaini host eden hosting firmasının bilgilerine ulaşabiliriz.

    whois <sitenin adı>

Yine google üzerinden bir örnek sorgulama göstereyim.

![resim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*KNWH8Brs-1zHCZdee16k0A.png)

Yukarıda bahsettiğim bilgileri terminalden kolayca görebiliyoruz.

## 4- DİG

Dig aracı Etki Alanı Adı Sistemini sorgular. Ağ sorunlarını gidermek ve eğitim amaçları için kullanışlıdır. Bir işletim sistemi dosyasından gelen istekleri okuyarak toplu modda çalışabilir.

    dig <site adı>

![resim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*y-8Dq9OVJbLDxWabpXgy4Q.png)

Yazımı okuduğunuz için teşekkürler. Herkese iyi çalışmalar…
