---
date: 2025-12-09
description: Java ile PostScript belgesi oluşturmayı ve Aspose.Page kullanarak görüntüyü
  çevirip döndürmeyi öğrenin; sorunsuz görüntü işleme için.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Java ile PostScript Belgesi Oluştur – Java PostScript'te Resim Ekle
url: /tr/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript Belgesi Oluşturma Java – Java PostScript'te Görüntü Ekleme

## Giriş
Bu öğreticide, **PostScript belge Java** oluşturmayı ve Aspose.Page for Java kütüphanesini kullanarak görüntüleri gömmeyi öğreneceksiniz. Belgeyi ayarlamaktan **görüntüyü çevirme ve döndürme** gibi dönüşümler uygulamaya kadar her adımı birlikte inceleyeceğiz. Sonunda, programlı olarak zengin PostScript dosyaları oluşturabilecek ve görüntü yerleşimini tam ihtiyaçlarınıza göre özelleştirebileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gereklidir?** Aspose.Page for Java  
- **Birden fazla görüntü ekleyebilir miyim?** Evet – dönüşüm ve çizim adımlarını tekrarlayın  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme test için çalışır; üretim için lisans gereklidir  
- **Hangi Java sürümü destekleniyor?** Java 8 ve sonrası  
- **Görüntü döndürme destekleniyor mu?** Kesinlikle – `AffineTransform.rotate()` kullanın  

## Java'da PostScript belgesi oluşturmak nedir?
PostScript belgesi, metin, grafik ve görüntüleri tanımlayan bir sayfa tanımlama dili dosyasıdır. Aspose.Page kullanarak, bu dosyaları Java'da programlı olarak oluşturabilir, düzen, grafik durumu ve görüntü işleme üzerinde tam kontrol sahibi olabilirsiniz; bir PostScript yorumlayıcıya ihtiyaç duymazsınız.

## Görüntü işleme için Aspose.Page neden kullanılmalı?
- **High‑level API:** Karmaşık PostScript komutlarını basitleştirir.  
- **Cross‑platform:** Java'yı destekleyen herhangi bir işletim sisteminde çalışır.  
- **Full graphics state control:** Grafikleri kolayca kaydedebilir, geri yükleyebilir, çevirip, ölçeklendirebilir ve döndürebilirsiniz.  
- **No external dependencies:** Görüntü yükleme ve dönüşümü dahili olarak yönetir.  

## Önkoşullar
Kodun içine dalmadan önce şunların kurulu olduğundan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü olduğundan emin olun.  
- Aspose.Page for Java kütüphanesi. Bunu [buradan](https://releases.aspose.com/page/java/) indirebilirsiniz.  
- Java programlamaya temel bir anlayış.  

## Paketleri İçe Aktarma
Başlamak için, Java projenizde gerekli paketleri içe aktarın. Aşağıdaki kod parçacığını referans olarak kullanın:

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
İlk adım, belgeye grafik kaydetme komutunu yazmayı içerir. Bu, sonradan yapılan herhangi bir dönüşüm veya değişikliğin gerektiğinde geri alınabilmesini sağlar.

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

## Adım 2: Çevirme ve Dönüştürme (görüntüyü çevirme ve döndürme)
Sonra, belgeyi çevirin ve görüntü dosyasından bir `BufferedImage` nesnesi oluşturun. `AffineTransform` kullanarak ölçekleme ve döndürme gibi bir dizi dönüşüm uygulayın. İşte **görüntüyü çevirme ve döndürme** işleminin gerçekleştiği yer.

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
Görüntüyü ekledikten sonra, yapılan değişiklikleri tamamlamak için grafik geri yükleme komutunu yazın.

```java
document.writeGraphicsRestore();
```

## Adım 5: Mevcut Sayfayı Kapat ve Kaydet
Mevcut sayfayı kapatın ve belgeyi kaydedin.

```java
document.closePage();
document.save();
```

Bu adımları tekrarlayarak birden fazla görüntü ekleyebilir veya gereksinimlerinize göre dönüşümleri özelleştirebilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **FileNotFoundException:** `dataDir` yolunun bir dosya ayırıcı (`/` veya `\\`) ile bittiğinden ve görüntü dosya adının tam olarak eşleştiğinden emin olun.  
- **ImageIO.read returns null:** Görüntü formatının desteklendiğini (ör. JPEG, PNG) doğrulayın.  
- **Incorrect rotation angle:** `AffineTransform.rotate` radyan bekler. Gerekirse dereceyi radyana çevirin (`Math.toRadians(degrees)`).  

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java'ı diğer programlama dilleriyle kullanabilir miyim?**  
A: Aspose.Page öncelikle Java'yı destekler, ancak diğer programlama dilleri için de sürümler mevcuttur.

**S: Aspose.Page for Java için ücretsiz deneme mevcut mu?**  
A: Evet, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.Page for Java için geçici lisans nasıl alabilirim?**  
A: Geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

**S: Aspose.Page for Java ile ilgili topluluk desteği ve tartışmaları nerede bulabilirim?**  
A: Topluluk desteği için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

**S: Aspose.Page for Java satın almak için ek kaynaklar var mı?**  
A: Kütüphaneyi [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak **PostScript belge Java** oluşturmayı ve görüntüleri gömmeyi başarıyla öğrendiniz. Vektör grafikleri, metin renderleme ve özel sayfa boyutları gibi daha gelişmiş özellik ve işlevler için [belgelere](https://reference.aspose.com/page/java/) göz atın.

---

**Son Güncelleme:** 2025-12-09  
**Test Edilen:** Aspose.Page for Java 23.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}