---
date: 2026-02-15
description: Aspose.Page Java kullanarak Java PostScript dosyalarına tarama deseni
  eklemeyi öğrenin. Bu adım adım rehber, tam kodu ve ipuçlarını gösterir.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page ile Java PostScript'te Tarama Deseni Nasıl Eklenir
url: /tr/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Çizgi Deseni Nasıl Eklenir

## Giriş
**Aspose.Page Java** ile çalışıyor ve PostScript çıktınıza **çizgi deseni nasıl eklenir** diye merak ediyorsanız, çizgi desenleri hızlı ve esnek bir çözümdür. Bu öğreticide **çizgi desenleri** nasıl eklenir adım adım gösterecek, neden faydalı olduklarını açıklayacak ve tamamen çalıştırılabilir bir kod örneği sunacağız. Sonunda, sadece birkaç Java satırıyla görsel olarak çekici çizgi‑dolgu şekilleri ve metinler oluşturabileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java ( “aspose page java” SDK ).  
- **Hangi görsel etkiyi ekliyoruz?** Çizgi desenleri (ör. çapraz çizgiler, çapraz çapraz).  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme yeterlidir; üretim için lisans gereklidir.  
- **Kaç satır kod?** Yaklaşık 70 satır, net adımlara bölünmüş.  
- **Aynı yaklaşımı PDF'lerde kullanabilir miyim?** Evet—Aspose.Page birden fazla çıktı formatını destekler, PDF dahil.

## Çizgi Deseni Nasıl Eklenir – Genel Bakış
Çizgi desenleri, herhangi bir çözünürlükte temiz renderlanan ve tek renkli yazıcılarda iyi çalışan vektör‑tabanlı dokulardır. Aspose.Page Java kullanarak bu desenleri şekillere, yollara ve hatta metne düşük seviyeli PostScript komutlarıyla uğraşmadan uygulayabilirsiniz.

## Ön Koşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

- **Java Geliştirme Ortamı** – JDK 8 veya üzeri ve tercih ettiğiniz bir IDE.  
- **Aspose.Page for Java kütüphanesi** – En son JAR dosyasını resmi siteden [burada](https://releases.aspose.com/page/java/) indirin.  
- **Yazma izni** – Oluşturulan PostScript dosyasının kaydedileceği klasöre yazma izniniz olsun.

## Paketleri İçe Aktarma
İlk olarak, projenize gerekli sınıfları ekleyin. Bu içe aktarmalar, çizim primitive'lerine, renk işleme ve Aspose.Page API'sine erişim sağlar.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım 1: Başlangıç Parametrelerini Ayarlama
Çıktı akışını oluşturun, sayfa boyutunu (A4) yapılandırın ve her çizgi‑dolgu kareyi çizerken yeniden kullanılacak birkaç düzen değişkeni tanımlayın.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Adım 2: Grafik Durumunu Kaydet ve Çevir
Grafik durumunu kaydetmek, daha sonra orijinal koordinat sistemine dönmemizi sağlar; `translate` ise başlangıç noktasını uygun bir konuma taşır.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Adım 3: Her Desen İçin Kare Oluştur
Her çizgi‑dolgu hücresini temsil edecek yeniden kullanılabilir bir dikdörtgen tanımlayın.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Adım 4: Desen Karesi Çerçevesi İçin Kalemi Ayarla
2 point'lik bir `BasicStroke`, her karenin net bir çerçevesini verir.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Adım 5: Çizgi Desenleri Üzerinde Döngü
`HatchStyle` enum'undaki her değeri döngüye alın, her kareyi karşılık gelen doku ile doldurun ve ardından çerçevesini çizin. Bu, **çizgi deseni ekleme** işlevinin çekirdeğidir.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Adım 6: Grafik Durumunu Geri Yükle
Kare ızgarasını çizmeyi tamamladıktan sonra orijinal koordinat sistemine dönün.

```java
document.writeGraphicsRestore();
```

## Adım 7: Metni Çizgi Deseniyle Doldur
Burada, bir metni çizgi dokusuyla boyamayı gösteriyoruz. Örnek, “ABC” kelimesini çapraz‑çapraz desenle doldurur.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Adım 8: Metni Çizgi Deseniyle Çerçevele
Şimdi aynı metni çerçeveleyeceğiz, ancak bu sefer %70 hatch stilini ve daha kalın bir çizgi kullanacağız.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Adım 9: Belgeyi Kapat ve Kaydet
Sayfayı sonlandırın, dosyayı diske yazın ve kaynakları serbest bırakın.

```java
document.closePage();
document.save();
```

Bu adımları izleyerek, hem şekillere hem de metne uygulanmış tam bir çizgi deseni seti gösteren bir PostScript dosyasına sahip olacaksınız—tümü **aspose page java** tarafından desteklenir.

## Neden Aspose.Page Java ile Çizgi Desenleri Kullanmalı?
- **Görsel ayırt edilebilirlik** – Çizgi dolgular, yazıcılar sadece tek renkli çıktıya sınırlı olsa bile çalışır.  
- **Performans** – Dokular anında üretilir, büyük görüntü dosyalarından kaçınılır.  
- **Çapraz‑format desteği** – Aynı kod, minimal değişiklikle PDF, EPS veya SVG'ye yönlendirilebilir.

## Yaygın Tuzaklar ve İpuçları
- **Dosya yolu hataları** – `dataDir`'in uygun dosya ayırıcıyla (`/` veya `\`) bittiğinden emin olun.  
- **Desteklenmeyen renkler** – Bazı eski PostScript yorumlayıcıları belirli renk uzaylarını işleyemeyebilir; maksimum uyumluluk için temel RGB'yi kullanın.  
- **Lisans uyarıları** – Geçerli bir lisans olmadan örnek çalıştırıldığında çıktı üzerine bir filigran eklenir.

## Sonuç
Çizgi desenlerini entegre etmek, teknik çizimler, haritalar veya Java tarafından üretilen herhangi bir grafiğin okunabilirliğini ve estetiğini büyük ölçüde artırabilir. **Aspose.Page Java** ile düşük seviyeli PostScript komutlarını soyutlayan özlü bir API elde eder, tasarıma odaklanırsınız. Artık **çizgi deseni nasıl eklenir** biliyorsunuz—gereken görünümü elde etmek için farklı `HatchStyle` değerleriyle deneyler yapın.

## Sıkça Sorulan Sorular

**S: Aspose.Page Java'yı diğer Java çerçeveleriyle kullanabilir miyim?**  
C: Evet, kütüphane çerçeve‑bağımsızdır ve Spring, Jakarta EE, Android (sınırlı) ve saf Java SE ile çalışır.

**S: Aspose.Page Java için deneme sürümü mevcut mu?**  
C: Kesinlikle. Ücretsiz 30‑günlük deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Geliştirme için geçici bir lisans nasıl alınır?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) talep edin. Değerlendirme filigranlarını kaldırır.

**S: Daha fazla öğretici ve topluluk desteği nerede bulunur?**  
C: Resmi forumu ziyaret edin: [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) ek örnekler ve S & C için.

**S: Tüm sınıflar ve metodlar için kapsamlı dokümantasyon var mı?**  
C: Evet, tam API referansı [burada](https://reference.aspose.com/page/java/) mevcuttur.

**S: Aynı çizgi desenini PDF yerine PostScript yerine render edebilir miyim?**  
C: Kesinlikle. `PsSaveOptions` yerine `PdfSaveOptions` (veya eşdeğeri) kullanın, kodun geri kalanı değişmeden kalır.

**S: Oluşturulan dosya boş çıkarsa ne yapmalıyım?**  
C: Çıktı akışının yazılabilir bir dizine işaret ettiğini ve `document.save()`'in tüm çizim işlemlerinden sonra çağrıldığını doğrulayın.

---

**Son Güncelleme:** 2026-02-15  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (yazım anındaki en yeni)  
**Yazar:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}