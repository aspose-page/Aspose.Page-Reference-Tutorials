---
title: Java PostScript'te Hatch Deseni Ekleme
linktitle: Java PostScript'te Hatch Deseni Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page'i kullanarak Java PostScript belgelerine büyüleyici tarama desenlerini nasıl ekleyeceğinizi öğrenin. Görsel içeriğinizi zahmetsizce yükseltin.
weight: 10
url: /tr/java/postscript-hatch-patterns/add-hatch-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Hatch Deseni Ekleme

## giriiş
Java programlama dünyasında görsel öğelerin geliştirilmesi geliştiricilerin ortak bir gereksinimidir. İlgi çekici görsel geliştirmelerden biri, PostScript belgelerine tarama desenlerinin eklenmesidir. Bu eğitim, Aspose.Page for Java'yı kullanarak tarama desenleri ekleme sürecinde size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki ayarlara sahip olduğunuzdan emin olun:
- Java Geliştirme Ortamı: Hazır bir Java geliştirme ortamınız olduğundan emin olun.
-  Aspose.Page for Java Library: Aspose.Page for Java kütüphanesini indirip yükleyin. Gerekli dosyaları bulabilirsiniz[Burada](https://releases.aspose.com/page/java/).
## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın. Aşağıdaki kod parçacığını kullanın:
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
## Adım 1: Başlangıç Parametrelerini Ayarlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
// Sayfa açıkken yeni PS Belgesi oluşturun
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## 2. Adım: Grafik Durumunu Kaydedin ve Çevirin
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## Adım 3: Her Desen için Kare Oluşturun
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## Adım 4: Desen Kare Anahattı için Kalemi Ayarlayın
```java
BasicStroke stroke = new BasicStroke(2);
```
## Adım 5: Hatch Desenlerini Yineleyin
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (verilen kodla devam edin)
}
```
## Adım 6: Grafik Durumunu Geri Yükleyin
```java
document.writeGraphicsRestore();
```
## Adım 7: Metni Hatch Deseniyle Doldurun
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## Adım 8: Hatch Desenli Metni Anahat
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## Adım 9: Belgeyi Kapatın ve Kaydedin
```java
document.closePage();
document.save();
```
Bu adımları takip ettiğinizde Aspose.Page'i kullanarak Java PostScript belgenize başarıyla tarama desenleri ekleyeceksiniz.
## Çözüm
Tarama desenleri gibi görsel öğelerin dahil edilmesi, Java uygulamalarınızın çekiciliğini önemli ölçüde artırabilir. Aspose.Page for Java, bu süreci sorunsuz hale getirerek görsel açıdan etkileyici PostScript belgelerini zahmetsizce oluşturmanıza olanak tanır.
## SSS
### Aspose.Page for Java'yı diğer Java çerçeveleriyle birlikte kullanabilir miyim?
Evet, Aspose.Page for Java, çeşitli Java çerçeveleriyle sorunsuz bir şekilde entegre olacak şekilde tasarlanmıştır.
### Aspose.Page for Java'nın deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java için daha fazla eğitim ve desteği nerede bulabilirim?
 Keşfedin[Java forumu için Aspose.Page](https://forum.aspose.com/c/page/39) öğreticiler ve topluluk desteği için.
### Aspose.Page for Java'ya yönelik kapsamlı bir dokümantasyon kaynağı var mı?
 Evet, belgelere bakın[Burada](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
