# Wifi Olduğu Halde Bilgisayarın İnternete Bağlanamama Problemi

**[İçeriğin orijinalini görmek için linke tıklayın](https://medium.com/@aysenurdgyl/wifi-oldu%C4%9Fu-halde-bilgisayara-i%CC%87nternet-ba%C4%9Flanamama-problemi-fe60385462c5)**

---

Wifiniz var fakat bilgisayarınızla bağlanamıyor musunuz? O halde şu adımları uygulayarak probleminizi çözebilirsiniz:

Arama kutusuna şunu yazın;

    inetcpl.cpl

Açılan pencereden

    gelişmiş >> sıfırla

şeklinde girin.

Cmd yönetici olarak açın aşağıdaki komutları girin her bir komuttan sonra entere basın:

    netsh int ip reset a.txt

    netsh winsock reset

    netsh winhttp reset Proxy

    netsh advfirewall reset

    ipconfig /flushdns

Bilgisayarı yeniden başlatarak durumu kontrol edin.

*Denetim masası* > *Arama kutusuna sorun giderme yazın* > *Sorun gidermeye tıklayın* > *Ağ ve internet* > *Buradan ağ sorunlarını düzeltin*
