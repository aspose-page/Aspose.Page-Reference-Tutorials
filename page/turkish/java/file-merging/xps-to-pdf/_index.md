---
date: 2025-11-29
description: Aspose.Page Java ile Java'da XPS'yi PDF olarak nasıl kaydedeceğinizi
  öğrenin. Verimli XPS'ten PDF'e dönüşüm ve PDF sıkıştırma ayarları için adım adım
  rehberimizi izleyin.
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java kullanarak Java'da XPS'yi PDF'ye dönüştür
url: /tr/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Aspose.Page Java Kullanarak XPS'yi PDF'ye Dönüştürme

## Giriş
Bu öğreticide, **Java'da Aspose.Page Java kullanarak XPS'yi PDF'ye nasıl dönüştüreceğinizi** öğreneceksiniz, Java belge dönüşümü için tasarlanmış sağlam bir kütüphane. Faturaları toplu işleme, yazdırılabilir raporlar oluşturma veya sadece eski XPS dosyalarını taşıma ihtiyacınız olsun, Aspose.Page Java işi hızlı, güvenilir ve tamamen yapılandırılabilir hâle getirir.

## Hızlı Yanıtlar
- **XPS'den PDF'ye dönüşümü hangi kütüphane yönetir?** Aspose.Page Java  
- **Temel bir dönüşüm ne kadar sürer?** Tek sayfalık XPS dosyası için genellikle bir saniyenin altında.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme çalışır; üretim için lisans gereklidir.  
- **PDF sıkıştırmasını kontrol edebilir miyim?** Evet – görüntü ve metin sıkıştırmasını ayarlamak için `PdfSaveOptions` kullanın.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri (JDK 11+ önerilir).

## Aspose.Page Java Nedir?
Aspose.Page Java, geliştiricilerin XPS belgelerini programlı olarak oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan **yüksek performanslı bir API**'dir. XPS'yi PDF, PNG, JPEG ve diğer formatlara render etmeyi desteklerken **PDF sıkıştırmasını ayarlama** gibi çıktı ayarları üzerinde ayrıntılı kontrol sağlar.

## Aspose.Page Java'yı XPS‑to‑PDF dönüşümü için neden kullanmalısınız?
- **Sıfır bağımlılık renderleme** – yerel kütüphaneler veya harici araçlar yok.  
- **Doğru düzen koruması** – PDF çıktısı orijinal XPS görünümünü yansıtır.  
- **PDF çıktısı üzerinde tam kontrol** – görüntü kalitesini ayarlayabilir, sıkıştırma algoritmalarını seçebilir ve render edilecek belirli sayfaları seçebilirsiniz.  
- **Çapraz platform** – herhangi bir standart JDK ile Windows, Linux ve macOS'ta çalışır.

## Önkoşullar
Başlamadan önce, şunların olduğundan emin olun:

1. **Java Development Kit (JDK) 8+** – performans ve güvenlik için en yeni JDK önerilir.  
2. **Aspose.Page for Java kütüphanesi** – resmi [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) adresinden JAR'ı indirin.  
3. Bir **IDE** (IntelliJ IDEA, Eclipse, VS Code) veya basit bir metin düzenleyici artı komut satırı yapı araçları (Maven/Gradle).

## Paketleri İçe Aktarma
Java sınıfınıza gerekli importları ekleyin, böylece XPS belgeleri ve PDF çıktısı ile çalışabilirsiniz.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Adım‑Adım Kılavuz

### Adım 1: Belge Dizin Yolunu Ayarlayın
Kaynak XPS dosyanızı içeren ve PDF'nin kaydedileceği klasörü tanımlayın.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Adım 2: PDF Çıktı Akışını Başlatın
`FileOutputStream` oluşturun ve hedef PDF dosyasına işaret etsin.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Pro ipucu:** Akışı otomatik olarak kapatmak ve kaynak sızıntılarını önlemek için `try‑with‑resources` kullanın.

### Adım 3: XPS Belgesini Yükleyin
Kaynak XPS dosyasını yükleyerek bir `XpsDocument` nesnesi oluşturun.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Adım 4: PDF Kaydetme Seçeneklerini Başlatın (PDF Sıkıştırmasını Ayarlayın)
PDF'nin nasıl sıkıştırılacağını yapılandırın. Bu adım, görüntüler ve metin için **PDF sıkıştırmasını ayarlamanıza** olanak tanır; kaliteyi kaybetmeden dosya boyutunu azaltır.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Neden önemli:** JPEG kalitesini ve sıkıştırma türlerini ayarlamak, 10 MB bir PDF'yi 2 MB'nin altına küçültebilir ve ihtiyacınız olan görsel sadakati korur.

### Adım 5: PDF Formatı için Render Cihazı Oluşturun
`PdfDevice`, render edilen sayfaları PDF çıktı akışına aktarır.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Adım 6: Belgeyi Kaydedin
Son olarak, yapılandırılmış seçenekleri kullanarak XPS içeriğiniye render edin.

```java
document.save(device, options);
```

> **Sonuç:** Çalıştırdıktan sonra, `XPStoPDF.pdf` `dataDir` klasöründe görünecek ve belirttiğiniz sıkıştırma ayarlarıyla dönüştürülmüş sayfaları içerecektir.

## Yaygın Sorunlar ve Çözümler

| Sorun | Nedeni | Çözüm |
|-------|--------|-------|
| **`FileNotFoundException`** | Yanlış `dataDir` yolu | Dizin mevcut mu ve uygulamanın okuma/yazma izinlerine sahip olup olmadığını doğrulayın. |
| **Boş PDF sayfaları** | `PdfDevice` başlatması eksik | `PdfDevice`'ın çıktı için kullanılan aynı `FileOutputStream` ile oluşturulduğundan emin olun. |
| **Büyük PDF boyutu** | Varsayılan sıkıştırma düşük | `setJpegQualityLevel` değerini artırın veya daha düşük kalite seviyeli `PdfImageCompression.Jpeg`'e geçin. |
| **Sadece bazı sayfalar görünüyor** | `setPageNumbers` filtresi sayfaları dışlıyor | Diziyi tüm gerekli sayfa numaralarını içerecek şekilde ayarlayın veya tüm sayfaları dışa aktarmak için çağırmayı kaldırın. |

## Sıkça Sorulan Sorular

**S: Aspose.Page Java farklı Java sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Page Java Java 8'den Java 21'e kadar, hem Oracle hem de OpenJDK dağıtımlarıyla desteklenir.

**S: Dönüştürülen PDF için sıkıştırma ayarlarını özelleştirebilir miyim?**  
C: Kesinlikle. Step 4'te gösterildiği gibi JPEG kalitesini, görüntü sıkıştırma tipini ve metin sıkıştırmasını ayarlamak için `PdfSaveOptions` kullanın.

**S: Ek destek veya topluluk tartışmalarını nerede bulabilirim?**  
C: Topluluk yardımı, kod örnekleri ve sorun giderme ipuçları için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

**S: Aspose.Page için ücretsiz bir deneme mevcut mu?**  
C: Evet, tamamen işlevsel bir denemeyi [Aspose download page](https://releases.aspose.com/) adresinden indirebilirsiniz.

**S: Aspose.Page için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisans [buradan](https://purchase.aspose.com/temporary-license/) talep edilebilir.

## Sonuç
**Aspose.Page Java**'yi kullanarak, **XPS'yi PDF olarak kaydetmeyi** sorunsuz bir şekilde yapabilir ve çıktıdaki sayfa seçimi ile sıkıştırmaya kadar her yönü kontrol edebilirsiniz. Bu öğretici, XPS‑to‑PDF dönüşümünü Java uygulamalarınıza entegre etmek için ihtiyacınız olan her şeyi kapsadı; ister tek seferlik bir araç, ister büyük ölçekli belge işleme hattı oluşturuyor olun.

---

**Son Güncelleme:** 2025-11-29  
**Test Edilen:** Aspose.Page for Java 24.10  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}