# GOBUSTER

**[İçeriğin orijinalini görmek için linke tıklayın](https://medium.com/@aysenurdgyl/gobuster-537ca8e0fb23)**

---

![RESİM](https://miro.medium.com/v2/resize:fit:720/format:webp/1*XKfuPPSGuxWhreFJDnP9QQ.png)

## GOBUSTER NEDİR?

Gobuster sızma testi araçlarından biridir. Diğer araçlara göre daha hızlıdır ve daha az hata verir. Go diliyle yazılmıştır. Bilgi toplamak için ve dizinleri kontrol etmek için kullanılır.

CTF çözerken de işimize yarayacak güzel bir araçtır.

Aslında gobuster dediğimiz araç bir dizin keşfi yapan brute-force (kaba-kuvvet) saldırı programıdır.

Gobuster; web sitelerindeki dizinleri ve dosyaları tespit eder, sunucudaki VHostları bulur, DNS subdomain taraması yapar.

Kali içerisinde kullanılan dirb aracı, gobuster aracı ile neredeyse aynı işlevdedir. Gobuster mi? Dirb mi? Bu kişiseldeir. Kİmine göre dirb, kimine göre gobuster daha iyidir.

Gobuster sadece terminal üzerinden çalışır. Ara yüzü olmadığından daha hızlıdır. Aynı zamanda açık kaynak kodlu olduğundan geliştirilebilir.

## GOBUSTER KULLANIMI

Gobuster aracı sanal makinenizde yüklü değilse :

    sudo apt-get install gobuster

![RESİM](https://miro.medium.com/v2/resize:fit:640/format:webp/1*dDm_SVWHnPBIRrBxe5ve9Q.png)

### 1- Dizin Bulma (dir)

    gobuster dir -u https://www.örneksite.com -w /usr/share/dirb/wordlists/small.txt

“dir” paremetre ve açıklamaları:

**-e (expented):** Genişletilmiş mod, tam url’leri yazar.
**-x (extensions string):** Aranacak dosya uzantıları (php, txt, html).
**-k (insecuressl):** SSL sertifika doğrulamasını atlar.
**-n (nostatus):** Durum kodlarını yazdırmaz.
**-s (statucodes string):** Olumlu durum kodları.
**-u (url string):** Hedef url yazılır.

### 2- DNS Subdomain

    gobuster dns -d www.örneksite.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

“dns” parametre ve açıklamaları:

**d (domain string):** Hedef etki alanını gösterir.

**-i (showips):** Ip adreslerini gösterir.

**-wilcard:** Özel karakter bulduğunda işleme devam eder.

**c (showcname):** Cname kayıtlarını gösterir.

### 3- Sanal Host Bulma (vhost)

    gobuster vhost -u https://örneksite.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
