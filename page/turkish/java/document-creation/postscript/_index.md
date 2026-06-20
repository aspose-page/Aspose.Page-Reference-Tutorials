---
date: 2026-06-20
description: Aspose.Page kullanarak A4 sayfa boyutunu ayarlamayı, Java'da PostScript
  dosyaları oluşturmayı ve özel yazı tipleri eklemeyi öğrenin. Ücretsiz deneme sürümünü
  bugün deneyin!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Java'da PostScript ile Belge Oluşturma
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java'da A4 sayfa boyutunu ayarlama ve Aspose.Page ile PostScript oluşturma
url: /tr/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Aspose.Page ile A4 sayfa boyutunu ayarlama ve PostScript oluşturma

## Giriş
Java'dan PostScript dosyaları oluştururken **a4 sayfa boyutunu ayarlamanız** gerekiyorsa, Aspose.Page düşük‑seviye detayları gizleyen hızlı ve güvenilir bir API sunar. Bu öğreticide tüm iş akışını—bir PostScript belgesi oluşturma, A4 sayfa boyutlarını yapılandırma ve gerektiğinde **özel yazı tipleri ekleme**—adım adım inceleyeceğiz. Sonunda, herhangi bir Java projesine ekleyebileceğiniz hazır bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **Java'da PostScript oluşturan kütüphane nedir?** Aspose.Page for Java.  
- **Bu kılavuz hangi sayfa boyutunu hedefliyor?** A4 (210 mm × 297 mm).  
- **Kendi yazı tiplerimi gömebilir miyim?** Evet – kaydetme seçeneklerinde ek yazı tipleri klasörünü ayarlayın.  
- **Üretim için lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; ücretsiz deneme mevcuttur.  
- **Hangi Java sürümleri destekleniyor?** Java 8 ve üzeri.

## Java'da a4 sayfa boyutunu ayarlama ve postscript oluşturma
Aspose.Page kütüphanesini yükleyin, `PsSaveOptions`'ı A4 sabitleriyle yapılandırın ve belgeyi bir dosyaya yazın – tümü on satırdan az kodla. Bu doğrudan yaklaşım doğru sayfa boyutlarını garanti eder ve ek yapılandırma gerektirmeden özel yazı tipleri eklemenizi sağlar.

## Postscript A4 boyutu nedir?
PostScript A4 boyutu, PostScript sayfa tanımlama dilinde ifade edilen ISO 216 standardıdır (210 mm × 297 mm). Yazıcıların ve görüntüleyicilerin yorumladığı basılabilir alanı tanımlar ve platformlar arasında tutarlı bir yerleşim sağlar. PostScript, sayfa içeriğini cihaz‑bağımsız bir şekilde tanımladığından, A4 boyutunu kullanmak, belgenin dünya çapında herhangi bir A4‑uyumlu yazıcı veya görüntüleyicide aynı şekilde görünmesini garanti eder.

## Postscript sayfa boyutunu ayarlamak için neden Aspose.Page kullanmalı?
Aspose.Page **30+ PostScript operatörünü** destekler ve belgeyi belleğe tamamen yüklemeden **500 MB**'a kadar dosyalar oluşturabilir. Bu, büyük iş yüklerini verimli bir şekilde işlerken sayfa boyutları üzerinde hassas kontrol sağlar. Kütüphane ayrıca karmaşık PostScript sözdizimini soyutlar, kaynakları otomatik olarak yönetir ve yüksek‑performanslı akış sağlar; bu da hem basit tek‑sayfalı broşürler hem de karmaşık çok‑sayfalı raporlar için idealdir.

## Java'da özel yazı tipleri ekleme
Kendi tipografik yazı tiplerinizi gömmek, oluşturulan belgenin herhangi bir yazıcı veya görüntüleyicide tasarlandığı gibi tam olarak görünmesini sağlar ve Aspose.Page belirtilen klasördeki yazı tiplerini otomatik olarak keşfeder. Ek bir yazı tipleri klasörü kaydederek, herhangi bir TrueType veya OpenType yazı tipini kullanabilir, yedekleme ikamelerini önleyebilir ve tüm çıktı cihazları arasında marka tutarlılığını koruyabilirsiniz.

## Önkoşullar
- Java programlama konusunda çalışan bir bilgi.  
- Aspose.Page for Java yüklü. Bunu [buradan](https://releases.aspose.com/page/java/) indirebilirsiniz.  
- `necessary_fonts` adlı (veya tercih ettiğiniz başka bir ad) klasör, gömmek istediğiniz tüm özel yazı tiplerini içerir.

## Paketleri İçe Aktar
Java projenizde, gerekli Aspose.Page sınıflarını içe aktarın:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Şimdi örneği net, numaralı adımlara ayıralım.

### Adım 1: Belge Dizini Ayarla
`OUTPUT_DIR` sabiti, kütüphaneye oluşturulan dosyanın nereye yazılacağını söyler.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Adım 2: Yazı Tipi Klasörünü Tanımla
`FONTS_FOLDER`, özel TrueType veya OpenType yazı tiplerinizi tutan dizini gösterir.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Adım 3: PostScript Belgesi için Çıktı Akışı Oluştur
`FileOutputStream`, nihai PostScript A4 çıktısını alacak bir akış açar.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Adım 4: A4 Boyutlu Kaydetme Seçenekleri Oluştur
`PsSaveOptions`, hedef sayfa boyutunu belirlemenizi sağlar.  
**Tanım:** `PsPageSize`, A4, Letter ve Legal gibi standart sayfa‑boyutu sabitlerini içeren bir enumerasyondur.  
`options.setPageSize(PsPageSize.A4)` ayarı, belgeyi standart A4 boyutlarına yapılandırır.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Adım 5: Sayfa Kenar Boşluklarını Ayarla ve Özel Yazı Tipi Klasörünü Ekle
`options.setMargins(0, 0, 0, 0)` tam kenara kadar sayfa için tüm kenar boşluklarını kaldırır ve `options.setAdditionalFontsFolder(FONTS_FOLDER)` özel yazı tiplerinizi kaydeder.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Adım 6: Çok Sayfalı veya Tek Sayfalı PS Belgesi Oluştur
`PsDocument document = new PsDocument(outputStream, options)` belgeyi oluşturur. `PsDocument`, bir veya birden fazla sayfa içerebilen bir PostScript belgesini temsil eder. Çok‑sayfalı çıktı için `multiPaged` değerini `true` olarak ayarlayın.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Adım 7: Mevcut Sayfayı Kapat ve Belgeyi Kaydet
`document.close()` çağrısı dosyayı sonlandırır ve **PostScript A4 boyutu** çıktısını diske yazar.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Yaygın Sorunlar ve İpuçları
- **Yazı tipi görünmüyor mu?** Yazı tipi dosyasının desteklenen bir TrueType veya OpenType formatında olduğunu ve `FONTS_FOLDER`'ın bir eğik çizgi (`/`) ile bittiğini doğrulayın.  
- **Kenar boşlukları hâlâ görünüyor mu?** `PsDocument` oluşturulmadan **önce** `options.setMargins(...)` çağırın.  
- **Çok‑sayfalı çıktı boş görünüyor mu?** İhtiyacınız olan her ek sayfa için `document.newPage()` çağırmayı unutmayın.

## Sıkça Sorulan Sorular

**Q: PostScript belgemde özel yazı tipleri kullanabilir miyim?**  
A: Evet, kaydetme seçeneklerinde ek yazı tipleri klasörünü ayarlayın (Adım 5'e bakın) ve Aspose.Page yazı tiplerini otomatik olarak gömer.

**Q: Aspose.Page for Java için bir deneme sürümü mevcut mu?**  
A: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**Q: Tam API referansına nasıl erişebilirim?**  
A: Belgeleri [buradan](https://reference.aspose.com/page/java/) inceleyin.

**Q: Aspose.Page for Java için lisansı nereden satın alabilirim?**  
A: Lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**Q: Topluluktan yardım almak için nereden sorabilirim?**  
A: Aspose.Page forumunu [forum](https://forum.aspose.com/c/page/39) ziyaret edin.

**Q: Çok‑sayfalı PostScript dosyaları oluşturabilir miyim?**  
A: Kesinlikle—Adım 6'da `multiPaged` değerini `true` olarak ayarlayın ve her ek sayfa için `document.newPage()` çağırın.

## Sonuç
Bu adımları izleyerek artık **a4 sayfa boyutunu nasıl ayarlayacağınızı** ve Java'da Aspose.Page ile **PostScript** dosyaları oluşturacağınızı biliyorsunuz; ayrıca **java'da özel yazı tipleri ekleme** ve sayfa‑boyutu seçeneklerini kontrol etme yeteneğine sahipsiniz. Aspose.Page ağır işleri halleder, böylece belgelerinizin içeriğine odaklanabilirsiniz.

---

**Son Güncelleme:** 2026-06-20  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Page Java Öğreticisi – PostScript'te Sayfa Eklerken Özel Sayfa Boyutu Ayarlama](/page/java/postscript-page-manipulation/add-pages2/)
- [Aspose.Page for Java ile PostScript'e Metin Ekleme](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Öğreticisi - PostScript'i PDF'e Dönüştürme](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```