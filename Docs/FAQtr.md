Diğer dillerde okuyun: [English](FAQ.md), [русский](FAQru.md), [Français](FAQfr.md), [Nederlands](FAQnl.md), [українська](FAQuk.md), [Polski](FAQpl.md), [Deutsch](FAQde.md), [Português do Brasil](FAQpt_BRmd)


# Sık Sorulan Sorular

## GitHub veya Discord'da bir soru sormadan önce lütfen bu sayfaya bakın.

<br>

### **1. Uzantı verileri nereden alıyor?**

Google API'leri ve toplanmış verilerin bir kombinasyonu.

Mevcut tüm verileri, Google'ın API'larındaki beğenmeme sayılarını kapatmasından sonra kullanılabilir olması için veritabanımıza kaydediyoruz.

<br>

### **2. Video'nun dislike sayısı neden güncellenmiyor?**

Şu anda video beğenmemeleri önbelleğe alınıyor ve çok sık güncellenmiyor. Her 2-3 günde bir, daha sık değil.

Evet, ideal değil ama durum bu. Bunları ne sıklıkta güncelleyebileceğimizi geliştirmek için çalışıyoruz.

<br>

### **3. Nasıl çalışıyor?**

Uzantı, izlediğiniz videonun kimliğini toplar, API'mizi kullanarak beğenmeme durumunu (ve görüntüleme, beğeni vb. gibi diğer alanları) getirir, eğer video API'miz tarafından ilk kez getiriliyorsa, verileri almak için YouTube API'sini kullanır, ardından verileri önbelleğe alma (yaklaşık 2-3 gün önbelleğe alınır) ve arşivleme amacıyla bir veritabanında depolar ve size döndürür. Eklenti daha sonra beğenilmeyenleri size görüntüler.

<br>

### **4. YouTube API'si dislike sayısını döndürmeyi durdurduktan sonra ne olacak?**

Sunucu tarafında, arşivlenmiş beğenmeme istatistikleri, uzantı kullanıcı verilerinden çıkarılan tahminler ve beğenmemeleri arşivlenmemiş videolar ve eski beğenmeme arşivleri için görüntüleme/beğenme oranlarına dayalı tahminlerin bir kombinasyonunu kullanmaya geçecektir.

<br>

### **5. Beğenmeme sayısı nasıl hesaplanır?**

RYD, beğenmeme sayısını tahmin etmek için kullanıcılarından gelen oyları kullanır.

- Eğer video API kapatıldıktan sonra yüklenmişse:

  $$ \textup{RYD Beğenmeme Sayısı} = \left( \frac{\textup{RYD Kullanıcılarının Dislike Sayısı}}{\textup{RYD Kullanıcıları Like Sayısı}} \right) \times \textup{Genel Like Sayısı} $$

- RYD veritabanında bir şekilde gerçek beğeni ve beğenmeme sayıları varsa (yükleyen tarafından veya arşivden sağlanmışsa), beğenmeme sayısı hem kullanıcıların oylarına hem de arşivlenmiş değere göre hesaplanacaktır. Arşivlenen değer eskidikçe nihai sayım üzerinde daha az etkiye sahip olacaktır.

RYD = Return YouTube Dislike eklentisi

<br>

---

Sayfanın video hali:

[![Return YouTube Dislike nasıl çalışıyor?](https://www.youtube.com/watch?v=GSmmtv-0yYQ)]

---

<br>

## Güvenlik / mahremiyetle ilgili endişelerim var

Daha fazla bilgi için [bu sayfaya](SECURITY-FAQtr.md) bakın.
