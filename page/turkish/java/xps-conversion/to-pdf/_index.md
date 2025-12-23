---
date: 2025-12-23
description: Aspose.Page kullanarak Java’da XPS’yi PDF’ye nasıl dönüştüreceğinizi
  öğrenin. Bu kılavuz, adım adım dönüşümü, XPS’den PDF oluşturmayı ve PDF sayfa numaralarını
  belirtmeyi gösterir.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Java'da XPS'yi PDF'ye Dönüştürme
url: /tr/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS'yi Java'da PDF'ye Dönüştürme

## XPS'yi Java'da PDF'ye Dönüştürme
Java geliştirme dünyasında, **XPS'yi PDF'ye nasıl dönüştürülür** sık sorulan bir sorudur. İster bir belge yönetim sistemi oluşturuyor olun ister yazdırılabilir raporlar üretmeniz gerekiyor olsun, XPS dosyalarını güvenilir bir şekilde dönüştürmek büyük bir fark yaratabilir. Neyse ki, Aspose.Page for Java, sadece birkaç satır kodla **XPS'den PDF oluşturmayı** kolaylaştırır.

## Quick Answers
- **Dönüştürmeyi hangi kütüphane yönetir?** Aspose.Page for Java.
- **Uygulama ne kadar sürer?** Temel bir kurulum için yaklaşık 10‑15 dakika.
- **Lisans gerekir mi?** Değerlendirme için ücretsiz deneme çalışır; üretim için bir lisans gereklidir.
- **Sadece seçili sayfaları dönüştürebilir miyim?** Evet – *specify PDF page numbers* seçeneğini kullanın.
- **Dönüştürme kayıpsız mı?** Kütüphane vektör grafikleri ve metin doğruluğunu korur.

## XPS'den PDF'ye Dönüştürme Nedir?
XPS (XML Paper Specification), Microsoft'un sabit‑düzen belge formatıdır. Bunu PDF'ye dönüştürmek, evrensel olarak kabul edilen PDF standardını kullanarak belgeleri paylaşmanıza, yazdırmanıza veya arşivlemenize olanak tanır.

## Neden Aspose.Page for Java'ı XPS'den PDF oluşturmak için kullanmalısınız?
- **High fidelity** – vektör grafikleri, yazı tiplerini ve düzeni korur.
- **Fine‑grained control** – görüntü kalitesini, sıkıştırmayı ayarlayabilir ve hatta belirli sayfaları seçebilirsiniz.
- **No external dependencies** – saf Java, JDK'yı destekleyen herhangi bir platformda çalışır.

## Ön Koşullar
Başlamadan önce, şunların olduğundan emin olun:

- **Java Development Kit (JDK)** – herhangi bir güncel sürüm (8+ önerilir).
- **Aspose.Page for Java** – kütüphaneyi resmi [documentation](https://reference.aspose.com/page/java/) adresinden indirin.
- Dönüştürmek istediğiniz bir XPS dosyası.

## Paketleri İçe Aktarın
Java projenizde, Aspose.Page for Java ile çalışmak için gerekli paketleri içe aktarın. Bu adım, XPS'den PDF'ye dönüşüm için gereken işlevlere erişim sağlamak açısından kritiktir.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Adım‑Adım Kılavuz

### Adım 1: Belge Dizinini Ayarla
Kaynak XPS dosyanızın bulunduğu klasörün yolunu tanımlayın.

```java
String dataDir = "Your Document Directory";
```

### Adım 2: PDF Çıktı Akışını Başlat
Oluşturulan PDF'yi alacak bir `FileOutputStream` oluşturun.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Adım 3: XPS Belgesini Yükle
XPS dosyasını Aspose.Page kullanarak yükleyin.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Adım 4: PDF Kaydetme Seçeneklerini Başlat  
Dönüşüm için seçenekler oluşturun. Burada **specify PDF page numbers** belirtebilir, görüntü kalitesini ayarlayabilir ve sıkıştırmayı belirleyebilirsiniz.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Adım 5: PDF Oluşturma Aygıtını Oluştur  
PDF çıktısını yazacak bir renderleme aygıtı kurun.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Adım 6: Belgeyi Kaydet  
Son olarak, yapılandırdığınız seçenekler ve aygıtı kullanarak XPS belgesini PDF olarak kaydedin.

```java
document.save(device, options);
```

Bu adımları tekrarlayın, dosya yollarını ve seçenekleri belirli senaryonuza göre ayarlayın.

## XPS Dönüştürürken PDF Sayfa Numaralarını Nasıl Belirlenir
Orijinal XPS'ten yalnızca bir alt küme sayfaya ihtiyacınız varsa, `setPageNumbers` dizisini istediğiniz sayfa indeksleriyle (1'den başlayarak) doldurun. Bu, dosya boyutunu ve işleme süresini azaltmaya yardımcı olur.

## Yaygın Sorunlar ve Sorun Giderme
- **FileNotFoundException** – `dataDir`'in doğru klasöre işaret ettiğini ve XPS dosya adının eşleştiğini doğrulayın.
- **LicenseException** – Üretim kullanımı için geçerli bir Aspose.Page lisansı gereklidir; aksi takdirde kütüphane değerlendirme modunda filigranla çalışır.
- **Low image quality** – Gerekirse `setJpegQualityLevel`'ı artırın veya kayıpsız sıkıştırmaya geçin.

## Sık Sorulan Sorular
### Aspose.Page for Java kullanarak çok sayfalı XPS dosyalarını dönüştürebilir miyim?
Evet, `PdfSaveOptions` içinde **specify PDF page numbers** belirterek (Adım 4'e bakın) ihtiyacınız olan sayfaları dahil edebilirsiniz.

### Ek destek nereden bulabilirim veya Aspose.Page‑ile ilgili soruları nerede tartışabilirim?
Topluluk desteği ve tartışmalar için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

### Aspose.Page for Java için ücretsiz deneme mevcut mu?
Evet, özellikleri bir [free trial](https://releases.aspose.com/) ile keşfedebilirsiniz.

### Aspose.Page for Java için geçici bir lisans nasıl alabilirim?
Geçici lisans detayları için [bu linki](https://purchase.aspose.com/temporary-license/) ziyaret edin.

### Aspose.Page for Java lisansını nereden satın alabilirim?
Lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

---

**Son Güncelleme:** 2025-12-23  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}