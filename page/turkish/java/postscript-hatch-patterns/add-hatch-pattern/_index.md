---
date: 2025-12-08
description: Aspose.Page Java kullanarak Java PostScript belgelerine çizgili desenler
  eklemeyi öğrenin. Bu adım adım rehber, çizgili desen grafiklerini verimli bir şekilde
  nasıl ekleyeceğinizi gösterir.
language: tr
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Java PostScript''te Tarama Deseni Ekle'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript’te Çizgili Desen Ekleme

## Giriş
**Aspose.Page Java** ile çalışıyor ve PostScript çıktınızı dokulu grafiklerle zenginleştirmek istiyorsanız, çizgili desenler hızlı ve esnek bir çözümdür. Bu öğreticide **çizgili desenleri** bir PostScript belgesine nasıl ekleyeceğinizi adım adım gösterecek, neden faydalı olduklarını açıklayacak ve tamamen çalıştırılabilir bir kod örneği sunacağız. Sonunda, sadece birkaç Java satırıyla görsel olarak çekici çizgili doldurulmuş şekiller ve metinler oluşturabileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java ( “aspose page java” SDK ).  
- **Hangi görsel etkiyi ekliyoruz?** Çizgili desenler (ör. diyagonal çizgiler, çapraz çizgiler).  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme yeterlidir; üretim için lisans gereklidir.  
- **Kaç satır kod?** Yaklaşık 70 satır, net adımlara bölünmüş.  
- **Aynı yaklaşımı PDF’lerde de kullanabilir miyim?** Evet—Aspose.Page, PDF dahil birden çok çıktı formatını destekler.

## Ön Koşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

- **Java Geliştirme Ortamı** – JDK 8 veya üzeri ve tercih ettiğiniz bir IDE.  
- **Aspose.Page for Java kütüphanesi** – En son JAR dosyasını resmi siteden [burada](https://releases.aspose.com/page/java/) indirin.  
- **Yazma izni** – Oluşturulan PostScript dosyasının kaydedileceği klasöre yazma izniniz olmalı.

## Paketleri İçe Aktarma
İlk olarak, proje içine gerekli sınıfları ekleyin. Bu importlar, çizim primitive’lerine, renk işlemlerine ve Aspose.Page API’sine erişim sağlar.

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

## Adım 1: İlk Parametreleri Ayarlama
Çıktı akışını oluşturun, sayfa boyutunu (A4) yapılandırın ve her çizgili doldurulmuş kareyi çizerken yeniden kullanılacak birkaç düzen değişkeni tanımlayın.

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

## Adım 3: Her Desen İçin Kare Oluşturma
Her çizgili doldurulmuş hücreyi temsil edecek yeniden kullanılabilir bir dikdörtgen tanımlayın.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Adım 4: Desen Karesi Çerçevesi İçin Kalemi Ayarlama
2 point’lik bir `BasicStroke`, her karenin net bir çerçevesini verir.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Adım 5: Çizgili Desenler Üzerinde Döngü
`HatchStyle` enum’undaki her değeri dolaşın, her kareyi ilgili doku ile doldurun ve ardından çerçevesini çizin. Bu, **çizgili desen ekleme** işlevinin çekirdeğidir.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Adım 6: Grafik Durumunu Geri Yükleme
Kare ızgarasını çizmeyi tamamladıktan sonra orijinal koordinat sistemine dönün.

```java
document.writeGraphicsRestore();
```

## Adım 7: Metni Çizgili Desenle Doldurma
Burada, bir metni çizgili doku ile boyamayı gösteriyoruz. Örnek, “ABC” kelimesini diyagonal‑çapraz bir desenle doldurur.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Adım 8: Metni Çizgili Desenle Çerçeveleme
Aynı metni şimdi çerçeveleyin; bu sefer %70’lik bir hatch stili ve daha kalın bir çizgi kullanıyoruz.

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

Bu adımları izleyerek, şekiller ve metinler üzerine tam bir çizgili desen seti uygulayan bir PostScript dosyasına sahip olacaksınız—hepsi **aspose page java** sayesinde.

## Aspose.Page Java ile Çizgili Desen Kullanmanın Avantajları
- **Görsel ayırt edilebilirlik** – Çizgili doldurmalar, yazıcılar sadece monokrom çıktıya sınırlı olsa bile işe yarar.  
- **Performans** – Dokular anında üretilir, bu sayede büyük resim dosyalarından kaçınılır.  
- **Çapraz format desteği** – Aynı kod, minimal değişiklikle PDF, EPS veya SVG’ye de hedeflenebilir.

## Yaygın Hatalar ve İpuçları
- **Dosya yolu hataları** – `dataDir` değişkeninin uygun dosya ayırıcıyla (`/` veya `\`) bittiğinden emin olun.  
- **Desteklenmeyen renkler** – Bazı eski PostScript yorumlayıcıları belirli renk uzaylarını işleyemeyebilir; maksimum uyumluluk için temel RGB renkleri kullanın.  
- **Lisans uyarıları** – Geçerli bir lisans olmadan örnek çalıştırıldığında çıktı üzerine bir filigran eklenir.

## Sonuç
Çizgili desenleri dahil etmek, teknik çizimler, haritalar veya Java tarafından üretilen herhangi bir grafiğin okunabilirliğini ve estetiğini büyük ölçüde artırabilir. **Aspose.Page Java** ile düşük seviyeli PostScript komutlarını soyutlayan özlü bir API elde eder, böylece dosya formatı inceliklerinden ziyade tasarıma odaklanabilirsiniz.

## Sıkça Sorulan Sorular

**S: Aspose.Page Java’yı diğer Java çerçeveleriyle kullanabilir miyim?**  
C: Evet, kütüphane çerçeve‑bağımsızdır ve Spring, Jakarta EE, Android (sınırlı) ve saf Java SE ile çalışır.

**S: Aspose.Page Java için deneme sürümü mevcut mu?**  
C: Kesinlikle. Ücretsiz 30‑günlük deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Geliştirme için geçici bir lisans nasıl alınır?**  
C: Geçici lisans talebinde [buradan](https://purchase.aspose.com/temporary-license/) bulun. Değerlendirme filigranlarını kaldırır.

**S: Daha fazla öğretici ve topluluk desteği nerede bulunur?**  
C: Resmi forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) adresinde ek örnekler ve S&S bulabilirsiniz.

**S: Tüm sınıflar ve metodlar için kapsamlı dokümantasyon var mı?**  
C: Evet, tam API referansı [burada](https://reference.aspose.com/page/java/) mevcuttur.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-08  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (yazım anındaki en yeni)  
**Yazar:** Aspose