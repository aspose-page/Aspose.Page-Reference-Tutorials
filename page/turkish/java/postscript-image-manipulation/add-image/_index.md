---
date: 2026-02-15
description: Aspose.Page for Java kullanarak PostScript Java belgeleri oluşturmayı
  ve görüntü çevirme ve döndürme ile PostScript belge dosyaları üretmeyi öğrenin.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: PostScript Java Oluştur – Java PostScript’te Görsel Ekle
url: /tr/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript Java Oluştur – Java PostScript'te Görüntü Ekle

## Giriş
Bu öğreticide, **postscript java** belgeleri oluşturmayı ve Aspose.Page for Java kütüphanesini kullanarak görüntüleri gömmeyi öğreneceksiniz. Yeni bir PostScript dosyası başlatmaktan **translate and rotate image** dönüşümlerini uygulamaya kadar her adımı adım adım inceleyeceğiz. Sonunda, PostScript dosyalarını programlı olarak üretebilecek ve görüntü yerleşimini piksel‑tam doğrulukla kontrol edebileceksiniz—otomatik raporlama, baskı iş akışları veya Java’dan **generate postscript document** çıktısı almanız gereken herhangi bir senaryo için mükemmel.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Birden fazla görüntü ekleyebilir miyim?** Evet – dönüşüm ve çizim adımlarını tekrarlayın  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme yeterli; üretim için lisans gereklidir  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri  
- **Görüntü döndürme destekleniyor mu?** Kesinlikle – `AffineTransform.rotate()` kullanın  

## create postscript java nedir?
Bir **create postscript java** işlemi, metin, vektör grafikleri ve raster görüntüleri kodlayan bir PostScript sayfa tanım dosyası üretir. Aspose.Page ile bu dosyaları doğrudan Java kodundan oluşturabilir, yerleşim, ölçekleme ve döndürme üzerinde tam programatik kontrol sağlayabilirsiniz; ayrı bir PostScript yorumlayıcıya ihtiyaç duymazsınız.

## Aspose.Page'i görüntü işleme için neden kullanmalısınız?
- **Yüksek‑seviye API:** Düşük‑seviye PostScript komutlarını basit Java metodlarına dönüştürür.  
- **Çapraz‑platform:** Java destekleyen herhangi bir işletim sisteminde çalışır.  
- **Tam grafik‑durumu kontrolü:** Grafikleri istediğiniz gibi kaydedebilir, geri yükleyebilir, çevirtebilir, ölçeklendirebilir ve döndürebilirsiniz.  
- **Harici bağımlılık yok:** Görüntü yükleme, format dönüşümü ve gömme işlemlerini dahili olarak yönetir.

## Önkoşullar
Kodlamaya başlamadan önce şunların yüklü olduğundan emin olun:

- Sisteminizde Java Development Kit (JDK) kurulu olmalı.  
- Aspose.Page for Java kütüphanesi. İndirmek için [buraya](https://releases.aspose.com/page/java/) tıklayın.  
- Java programlamaya temel bir anlayış.

## Paketleri İçe Aktarma
Başlamak için Java projenizde gerekli paketleri içe aktarın. Aşağıdaki kod parçacığını referans olarak kullanın:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım 1: Grafik Kaydetme Yazma
İlk adım, belgeye grafik kaydetme komutunu yazmaktır. Bu, sonradan yapılan dönüşüm veya değişikliklerin gerektiğinde geri alınabilmesini sağlar.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Adım 2: Çevirme ve Dönüştürme (translate and rotate image)
Sonra, belgeyi çevirin ve görüntü dosyasından bir `BufferedImage` nesnesi oluşturun. `AffineTransform` kullanarak ölçekleme ve döndürme gibi bir dizi dönüşüm uygulayın. İşte **translate and rotate image** işleminin gerçekleştiği yer.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Adım 3: Görüntüyü Belgeye Ekle
Şimdi, dönüştürülmüş görüntüyü belgeye ekleyin.

```java
document.drawImage(image, transform, null);
```

## Adım 4: Grafik Geri Yükleme Yazma
Görüntüyü ekledikten sonra, yapılan değişiklikleri sonlandırmak için grafik geri yükleme komutunu yazın.

```java
document.writeGraphicsRestore();
```

## Adım 5: Geçerli Sayfayı Kapat ve Kaydet
Geçerli sayfayı kapatın ve belgeyi kaydedin.

```java
document.closePage();
document.save();
```

Bu adımları tekrarlayarak birden fazla görüntü ekleyebilir veya gereksinimlerinize göre dönüşümleri özelleştirebilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **FileNotFoundException:** `dataDir` yolunun bir dosya ayırıcı (`/` veya `\\`) ile bittiğinden ve görüntü dosya adının tam olarak eşleştiğinden emin olun.  
- **ImageIO.read null döndürüyor:** Görüntü formatının desteklendiğini (ör. JPEG, PNG) doğrulayın.  
- **Yanlış döndürme açısı:** `AffineTransform.rotate` radyan bekler. Gerekirse dereceyi radyana çevirin (`Math.toRadians(degrees)`).

## Sık Sorulan Sorular

**S: Aspose.Page for Java’yı başka programlama dilleriyle kullanabilir miyim?**  
C: Aspose.Page öncelikle Java’yı destekler, ancak diğer programlama dilleri için de sürümler mevcuttur.

**S: Aspose.Page for Java için ücretsiz bir deneme mevcut mu?**  
C: Evet, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.Page for Java için geçici bir lisans nasıl alınır?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Aspose.Page for Java ile ilgili topluluk desteği ve tartışmalara nereden ulaşabilirim?**  
C: Topluluk desteği için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

**S: Aspose.Page for Java satın almak için ek kaynaklar var mı?**  
C: Kütüphaneyi [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak **postscript java** belgeleri oluşturmayı ve görüntüleri gömmeyi başarıyla öğrendiniz. Daha gelişmiş özellikler ve işlevler için [belgelere](https://reference.aspose.com/page/java/) göz atın; vektör grafikleri, metin işleme ve özel sayfa boyutları gibi konulara da ulaşabilirsiniz.

---

**Son Güncelleme:** 2026-02-15  
**Test Edilen Versiyon:** Aspose.Page for Java 23.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}