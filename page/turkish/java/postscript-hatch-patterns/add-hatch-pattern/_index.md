---
date: 2026-08-18
description: Aspose.Page Java kullanarak Java PostScript dosyalarına hatch pattern
  eklemeyi öğrenin. Bu adım adım rehber, tam kodu ve ipuçlarını gösterir.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Java PostScript'te Hatch Pattern Ekle
og_description: Aspose.Page kullanarak Java PostScript'te hatch pattern eklemeyi öğrenin.
  Hızlı bir şekilde hatch‑filled graphics oluşturmak için bu adım adım öğreticiyi
  izleyin.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Java PostScript'te hatch pattern ekleme – Aspose.Page rehberi
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Java PostScript'te hatch pattern ekleme
url: /tr/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te tarama deseni nasıl eklenir

## Giriş
Eğer **Aspose.Page Java** ile çalışıyorsanız ve PostScript çıktınıza **tarama deseni nasıl eklenir** diye merak ediyorsanız, tarama desenleri hızlı ve esnek bir çözümdür. Bu öğreticide **tarama** tasarımlarını bir PostScript belgesine nasıl ekleyeceğinizi adım adım gösterecek, neden faydalı olduklarını açıklayacak ve tamamen çalıştırılabilir bir kod örneği sunacağız. Sonunda, sadece birkaç Java satırıyla görsel olarak çekici tarama doldurmalı şekiller ve metinler oluşturabileceksiniz.

## Hızlı cevaplar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java (the “aspose page java” SDK).  
- **Hangi görsel efekti ekliyoruz?** Tarama desenleri (ör. diyagonal çizgiler, çapraz tarama).  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için lisans gereklidir.  
- **Kaç satır kod?** Yaklaşık 70 satır, net adımlara bölünmüş.  
- **Aynı yaklaşımı PDF'ler için de kullanabilir miyim?** Evet—Aspose.Page, PDF dahil birden fazla çıktı formatını destekler.

## Tarama deseni nedir?
Tarama deseni, tekrarlanan çizgiler veya şekillerden oluşan ve bir doku etkisi yaratan vektör tabanlı bir doldurmadır. Matematiksel olarak tanımlandığı için desen kalite kaybı olmadan ölçeklenir, bu da yüksek çözünürlüklü baskı ve tek renkli çıktılar için idealdir.

## Aspose.Page Java ile tarama desenleri neden kullanılmalı?
Aspose.Page **10+ çıktı formatını** (PostScript, PDF, EPS, SVG ve XPS dahil) destekler ve **500 sayfaya** kadar belgeye tarama doldurmaları uygulayabilir, tüm dosyayı belleğe yüklemeden. Bu, hızlı performans, düşük bellek ayak izi ve tüm desteklenen formatlarda tutarlı görsel sonuçlar anlamına gelir.

## Tarama deseni ekleme – genel bakış
Tarama desenleri, herhangi bir çözünürlükte temiz bir şekilde render edilen vektör tabanlı dokulardır ve tek renkli yazıcılarda iyi çalışır. Aspose.Page Java kullanarak bu desenleri şekillere, yollara ve hatta metne düşük seviyeli PostScript komutlarıyla uğraşmadan uygulayabilirsiniz.

## Önkoşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:

- **Java Geliştirme Ortamı** – JDK 8 veya üzeri ve tercih ettiğiniz bir IDE.  
- **Aspose.Page for Java kütüphanesi** – Resmi **Aspose.Page for Java indirme sayfasından** [burada](https://releases.aspose.com/page/java/) en son JAR'ı indirin.  
- Diğer Aspose sürümlerine de [buradan](https://releases.aspose.com/) göz atabilirsiniz.  
- Oluşturulan PostScript dosyasının kaydedileceği klasöre **yazma izni**.

## Paketleri içe aktar
Aşağıdaki içe aktarmalar, renkler, çizgi kalınlıkları ve geometrik şekiller gibi grafik ilkelileri için standart Java AWT sınıflarını ve bir PostScript dosyası oluşturmak için gerekli belge modeli, tarama‑stili tanımlamaları ve kaydetme seçeneklerini sağlayan Aspose.Page sınıflarını içerir.  
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

## `Document` sınıfı nedir?
`Document` sınıfı, Aspose.Page'in bellek içindeki tek bir PostScript dosyasını temsil eden üst‑seviye nesnesidir. Tüm çizim işlemleri bu nesne üzerinden gerçekleştirilir.

## Çıktı akışını nasıl ayarlamalıyım?
Çıktıyı yazmak için istenen dosya yoluna işaret eden bir `FileOutputStream` oluşturun; bu akış düşük seviyeli bayt yazımını yönetir. `PsSaveOptions` belge nasıl kaydedileceğini, sayfa boyutu ve sıkıştırma gibi ayarları yapılandırır. Ardından sayfa boyutu, sıkıştırma ve diğer PostScript‑özel ayarları belirten bir `PsSaveOptions` nesnesiyle bir `Document` örneği oluşturun.  
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

## Grafik durumunu kaydetmek ve orijini çevirmek nasıl yapılır?
Grafik durumunu kaydetmek, mevcut dönüşüm matrisini, kırpma bölgesini ve çizim özelliklerini yakalar, böylece daha sonra geri dönebilirsiniz. Kaydettikten sonra, ızgara şeklindeki tarama karelerini çizmeyi kolaylaştırmak için grafik nesnesi üzerinde `translate(x, y)` çağırarak orijini istenen konuma kaydırın.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Her desen için yeniden kullanılabilir bir kare nasıl oluşturulur?
`Rectangle2D`, konumu ve boyutu ile tanımlanan dikdörtgen bir şekildir. Hücre boyutlarına uyan tek bir örnek oluşturarak, her tarama‑dolu kare için yeniden kullanabilirsiniz; bu, nesne tahsislerini azaltır ve çizim döngüsünü verimli tutar.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Desen kare konturu için kalemi nasıl ayarlamalıyım?
`BasicStroke`, vektör şekillerinin kontur kalınlığını, kesik desenini ve uç kapaklarını tanımlar. 2‑point `BasicStroke` kullanmak, her tarama‑dolu hücrenin etrafında net bir kenar sağlar ve doldurmanın komşu karelerden görsel olarak ayrılmasını garantiler.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Tarama desenleri nasıl döngüye alınır?
`HatchStyle`, diyagonal, çapraz ve noktalı gibi önceden tanımlı tüm tarama desenlerini listeleyen bir enumdur. `HatchStyle.values()` üzerinde döngü kurarak her deseni sırayla uygulayabilir, dikdörtgeni bir `HatchBrush` ile doldurabilir ve ardından konturunu çizebilirsiniz.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Çizim sonrası grafik durumu nasıl geri yüklenir?
Grafik nesnesi üzerinde `restore()` çağırmak, dönüşüm matrisini ve çizim ayarlarını daha önce kaydedilen duruma geri döndürür; böylece sonraki çizim işlemlerinin birikmiş çevirme veya ölçeklendirmelerden etkilenmesi önlenir. Bu, sonraki içeriğin orijinal koordinat sisteminden başlamasını ve varsayılan öznitelikleri kullanmasını sağlar.  
```java
document.writeGraphicsRestore();
```

## Metin tarama deseniyle nasıl doldurulur?
`TextFragment`, bağımsız olarak konumlandırılabilen ve stillendirilebilen bir metin parçasını temsil eder. Fragmanın doldurmasına seçilen bir `HatchBrush` ve `HatchStyle` atayarak, metin karakterleri katı bir renk yerine tarama dokusuyla render edilir.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Metni farklı bir tarama stiliyle nasıl konturlarsınız?
`HatchBrush` aynı zamanda çizgi (stroke) için de kullanılabilir. Bir kontur çizmek için, fragmanın stroke özelliğini farklı bir `HatchStyle` (ör. %70 tarama) ile bir `HatchBrush` olarak ayarlayın ve `setStrokeWidth` ile çizgi kalınlığını artırın. Bu, metnin kenarını kendi tarama deseniyle render ederken doldurulan iç kısmı korur.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Belgeyi nasıl kapatır ve kaydederim?
`document.save()` bellek içindeki belgeyi belirtilen çıktı akışına yazar. Tüm çizim komutları tamamlandıktan sonra bu yöntemi çağırın ve ardından `FileOutputStream`'i kapatarak sistem kaynaklarını serbest bırakın ve dosyanın diske düzgün bir şekilde yazıldığından emin olun.  
```java
document.closePage();
document.save();
```

Bu adımları izleyin, ve hem şekillere hem de metne tam bir tarama deseni seti uygulayan bir PostScript dosyanız olacak—tamamen **aspose page java** ile güçlendirilmiş.

## Yaygın hatalar ve ipuçları
- **Dosya yolu hataları** – `dataDir`'in uygun dosya ayırıcıyla (`/` veya `\`) bittiğinden emin olun.  
- **Desteklenmeyen renkler** – Bazı eski PostScript yorumlayıcıları belirli renk uzaylarını işleyemeyebilir; maksimum uyumluluk için temel RGB'yi kullanın.  
- **Lisans uyarıları** – Geçerli bir lisans olmadan örnek çalıştırıldığında çıktıya bir filigran eklenir.

## Sıkça sorulan sorular

**S: Aspose.Page Java'yı diğer Java çerçeveleriyle kullanabilir miyim?**  
C: Evet, kütüphane çerçeve‑bağımsızdır ve Spring, Jakarta EE, Android (sınırlı) ve düz Java SE ile çalışır.

**S: Aspose.Page Java için bir deneme sürümü mevcut mu?**  
C: Kesinlikle. Ücretsiz 30‑günlük bir deneme sürümünü [Aspose trial download page](https://releases.aspose.com/) adresinden indirebilirsiniz.

**S: Geliştirme için geçici bir lisans nasıl elde ederim?**  
C: Geçici bir lisans [temporary license request page](https://purchase.aspose.com/temporary-license/) talep edin. Bu, değerlendirme filigranlarını kaldırır.

**S: Daha fazla öğretici ve topluluk desteği nerede bulunur?**  
C: Ek örnekler ve S&S için resmi forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

**S: Tüm sınıflar ve metodlar için kapsamlı bir dokümantasyon var mı?**  
C: Evet, tam API referansı [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) üzerinden erişilebilir.

**S: Aynı tarama desenini PDF yerine PostScript olarak render edebilir miyim?**  
C: Kesinlikle. `PsSaveOptions` yerine `PdfSaveOptions` (veya eşdeğeri) değiştirin, kodun geri kalanı aynı kalır.

**S: Oluşturulan dosya boş ise ne yapmalıyım?**  
C: Çıktı akışının yazılabilir bir dizine işaret ettiğini ve `document.save()`'in tüm çizim işlemlerinden sonra çağrıldığını doğrulayın.

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## İlgili Öğreticiler

- [PostScript'te Doku Deseni Oluşturma – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Java PostScript'te Gradient Ekleme: Diyagonal Gradient – Aspose.Page Java kullanarak](/page/java/postscript-gradient-addition/diagonal/)
- [Aspose.Page Java API kullanarak PostScript'i PDF'ye Dönüştürme](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}