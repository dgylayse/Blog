# Resim içine nasıl yazı gizlenir? (Steganografi)

**[İçeriğin orijinalini görmek için linke tıklayın](https://medium.com/@aysenurdgyl/resim-i%C3%A7ine-nas%C4%B1l-yaz%C4%B1-gizlenir-steganografi-fbd1574fd9b6)**

---

Steganografi, eski Yunanca’da “gizlenmiş yazı” anlamına gelir. Steganografi bilgiyi gizleme bilimidir. Steganografi’nin şifrelemeye göre en büyük avantajı bilgiyi gören bir kimsenin gördüğü şeyin içinde önemli bir bilgi olduğunu fark edemiyor olmasıdır, böylece içinde bir bilgi aramaz.

Örneğin bir resme çıplak gözle bakılınca pek de göze çarpan bir şey yoktur. Ve böylelikle bu resim önemsenmez orada saklanılan veri de ortaya da çıkmaz.

Peki resim içine nasıl yazı gizlenir ve nasıl okunur?

- Downloads dizinde GizliDosya adlı bir klasör içinde resim.jpg adlı bir resim.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*IMmAw6c2mT-URBND3UGKCw.png)
![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*t9rX-nKyY9qksQl5FOirBw.png)

- Şimdi resim içine yazı yazmak için terminale gelip cd komutuyla Downloads dizisine gireceğiz.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*kWTOQB_ZA8tbv_LSams9hg.png)

- Ardından Downloads dizinindeki GizliDosya klasörüne gireceğiz.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*ToYHRb7NWt1xHpyf5DcL4g.png)

Resime yazı yazmak için girilecek komut ;

    echo “ “ Girilecek veri “ “ >> resim ismi

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*WCp_P5hD2WdCY0K1gkuiFg.png)

- Girdiğimiz veriyi okumak için cat komutunu girmeliyiz.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*em8KCPSPuXjTdDQXqD8ZmQ.png)

- Bu komutu girdikten sonra upuzun kodlar karşımıza çıkacak. Resime yazdığımız veriyi altta bulabiliriz.

![resim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*YAxlDXyAmdFCa7gj_4bOLg.png)
