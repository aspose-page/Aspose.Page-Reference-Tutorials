---
date: 2025-12-14
description: Aspose.Page for Java kullanarak Java’da metin rengini nasıl ayarlayacağınızı,
  PostScript’e metin eklemeyi ve zengin belge stilizasyonu için kenar çizgili metin
  uygulamayı öğrenin.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page ile Java’da Metin Rengini Ayarlama – Metin Manipülasyonu Rehberi
url: /tr/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Text Color Java with Aspose.Page – Metin Manipülasyonu Rehberi

## Giriş
Aspose.Page for Java kullanarak PostScript dosyalarıyla çalışırken **set text color java** hakkında adım adım rehberimize hoş geldiniz. Aspose.Page for Java, geliştiricilerin **generate postscript file** belgeleri oluşturmasına, yazı tiplerini manipüle etmesine ve metni hassas bir şekilde biçimlendirmesine olanak tanıyan güçlü bir kütüphanedir. Bu öğreticide metin eklemeyi, rengini değiştirmeyi, boyutunu ayarlamayı ve hatta **apply stroke text** ile cilalı bir görünüm elde etmeyi öğreneceksiniz.

## Hızlı Yanıtlar
- **Java'da metin rengini ayarlamamı sağlayan kütüphane nedir?** Aspose.Page for Java.
- **Sistem yazı tiplerini ve özel yazı tiplerini kullanabilir miyim?** Evet, her ikisi de desteklenir.
- **Metin boyutunu nasıl değiştiririm?** `Font` veya `DrFont` oluştururken yazı tipi boyutunu belirterek.
- **Metni aynı anda kontur ve dolgu ile işlemek mümkün mü?** Kesinlikle – `fillAndStrokeText` kullanın.
- **Bu öğreticinin çıktısı hangi formatta?** Bir PostScript (`.ps`) belgesi.

## “set text color java” nedir?
Java'da metin rengini ayarlamak, render motorunun (burada Aspose.Page) sayfaya karakter çizerken kullandığı `Color` nesnesini tanımlamak anlamına gelir. Bu işlem, özellikle **postscript documents** programlı olarak oluşturulurken görsel olarak ayırt edilebilir belgeler yaratmak için gereklidir.

## Neden Aspose.Page for Java kullanmalı?
- **Tam kontrol** yerel bir PostScript yorumlayıcıya ihtiyaç duymadan PostScript üretimi üzerinde.
- **Sistem ve harici yazı tipleri desteği**, ihtiyacınız olan herhangi bir tipografiyi gömebilmenizi sağlar.
- **Kolay API** doldurmak, kontur eklemek ve **fill and stroke text** için, stil konusunda esneklik sağlar.
- **Çapraz platform** uyumluluğu – bir kez yazın, Java çalıştığı her yerde çalıştırın.

## Önkoşullar
Before diving in, make sure you have:

- Java programlama temelleri hakkında temel bilgi.
- Aspose.Page for Java kütüphanesi yüklü. Bunu [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) adresinden indirebilirsiniz.
- Gerekli yazı tipleri belirtilen klasörde mevcut. Ek detaylar [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) içinde.

## Paketleri İçe Aktarma
In your Java project, import the necessary packages for Aspose.Page for Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Adım 1: Belgeyi Oluşturma
First, we create a new **PostScript document** and configure the output options.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Sistem Yazı Tipi Kullanarak Text Color Java Nasıl Ayarlanır
Now we demonstrate **set text color java** with a system‑provided font.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **İpucu:** `fillText` yöntemi, bir `Color` argümanı geçmezseniz mevcut rengi otomatik olarak kullanır; varsayılan olarak siyah olur.

## Özel Yazı Tipi Kullanma ve Metin Boyutunu Değiştirme
You can also **change text size** and use a custom font stored in your fonts folder.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Konturlama (Stroke) Metni – Stroke Text Uygulama
Outlining text gives it a crisp edge. Here we **apply stroke text** using a `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Özel Yazı Tipi ile Konturlama
The same technique works with custom fonts.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Adım 6: Belgeyi Kaydet
Finally, close the page and write the file to disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Font not found** | Yazı tipi dosyasının `necessary_fonts` içine yerleştirildiğinden ve klasör yolunun `options.setAdditionalFontsFolders` ile doğru eklendiğinden emin olun. |
| **Color not applied** | `fillText` veya `outlineText` metodunun `Color` argümanı içeren aşırı yüklemesini çağırdığınızı doğrulayın. |
| **Stroke appears too thin** | `BasicStroke` genişliğini artırın (ör. `new BasicStroke(3)`). |
| **Document not opening** | Oluşturulan `.ps` dosyasının doğru uzantıyla kaydedildiğini ve görüntüleyicinizin PostScript'i desteklediğini kontrol edin. |

## Sıkça Sorulan Sorular

**Q:** Aspose.Page for Java ile kendi özel yazı tiplerimi kullanabilir miyim?  
A: Evet, `DrFont` sınıfında yazı tipi adını ve boyutunu belirterek özel yazı tiplerini kullanabilirsiniz.

**Q:** Metnin rengini nasıl değiştirebilirim?  
A: Metni doldururken veya konturlarken `Color` sınıfını kullanarak istediğiniz rengi ayarlayabilirsiniz.

**Q:** Bir PostScript belgesine birden fazla sayfa eklemek mümkün mü?  
A: Kesinlikle! Belge oluşturma ve kaydetme adımlarını tekrarlayarak birden fazla sayfa oluşturabilirsiniz.

**Q:** `ExternalFontCache` sınıfının amacı nedir?  
A: `ExternalFontCache`, özel yazı tiplerini alıp metin manipülasyonu için kullanılabilir olmasını sağlar.

**Q:** Konturlu metne farklı stroke'lar uygulayabilir miyim?  
A: Evet, `Stroke` sınıfı ve `Color` sınıfı ile stroke genişliğini ve rengini özelleştirebilirsiniz.

## Sonuç
Tebrikler! Artık Aspose.Page for Java kullanarak **set text color java**, yazı tipi boyutlarını değiştirme, **apply stroke text** ve **create postscript document** dosyaları oluşturma konusunda bilgi sahibisiniz. Farklı yazı tipleri, renkler ve kontur stilleriyle deneyler yaparak profesyonel görünümlü PostScript çıktıları elde edebilirsiniz.

---

**Son Güncelleme:** 2025-12-14  
**Test Edilen Versiyon:** Aspose.Page for Java 23.12 (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}