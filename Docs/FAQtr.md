Diğer dillerde okuyun: [English](FAQ.md), [русский](FAQru.md), [Français](FAQfr.md), [Nederlands](FAQnl.md), [українська](FAQuk.md), [Polski](FAQpl.md), [Deutsch](FAQde.md), [Português do Brasil](FAQpt_BRmd)


# Sık Sorulan Sorular

## GitHub veya Discord'da bir soru sormadan önce lütfen bu sayfaya bakın.

<br>

### **1. Uzantı verileri nereden alıyor?**

Google API'leri ve toplanmış verilerin bir kombinasyonu.

Mevcut tüm verileri, Google'ın API'larındaki beğenmeme sayılarını kapatmasından sonra kullanılabilir olması için veritabanımıza kaydediyoruz.

<br>

### **2. Video beğenmeme sayısı güncellenmiyor?**

Şu anda video beğenmemeleri önbelleğe alınıyor ve çok sık güncellenmiyor. Her 2-3 günde bir, daha sık değil.

Evet, ideal değil ama durum bu. Bunları ne sıklıkta güncelleyebileceğimizi geliştirmek için çalışıyoruz.

<br>

### **3. Nasıl çalışıyor?**

Uzantı, izlediğiniz videonun kimliğini toplar, API'mizi kullanarak beğenmeme durumunu (ve görüntüleme, beğeni vb. gibi diğer alanları) getirir, eğer video API'miz tarafından ilk kez getiriliyorsa, verileri almak için YouTube API'sini kullanır, ardından verileri önbelleğe alma (yaklaşık 2-3 gün önbelleğe alınır) ve arşivleme amacıyla bir veritabanında depolar ve size döndürür. Eklenti daha sonra beğenilmeyenleri size görüntüler.

<br>

### **4. YouTube API'si beğenmeme sayısını döndürmeyi durdurduktan sonra ne olacak?**

Sunucu tarafında, arşivlenmiş beğenmeme istatistikleri, uzantı kullanıcı verilerinden çıkarılan tahminler ve beğenmemeleri arşivlenmemiş videolar ve eski beğenmeme arşivleri için görüntüleme/beğenme oranlarına dayalı tahminlerin bir kombinasyonunu kullanmaya geçecektir.

<br>

### **5. Beğenmeme sayısı nasıl hesaplanır?**

RYD uses the votes from its users to extrapolate the dislike count.

- If the video was uploaded after the API was shut down:

  $$ \textup{RYD Dislike Count} = \left( \frac{\textup{RYD Users Dislike Count}}{\textup{RYD Users Like Count}} \right) \times \textup{Public Like Count} $$

- If the RYD database somehow had the actual like and dislike count (provided by the uploader or from the archive), the dislike count will be calculated based on both - the users' votes and the archived value. The archived value will have less influence on the final count as it ages.

<br>

---

This in video form

[![IReturn YouTube Dislike Explained](https://yt-embed.herokuapp.com/embed?v=GSmmtv-0yYQ)](https://www.youtube.com/watch?v=GSmmtv-0yYQ)

---

<br>

## Güvenlik / gizlilikle ilgili endişelerim var

Daha fazla bilgi için [bu sayfaya](SECURITY-FAQtr.md) bakın.
