---
title: Java PostScript'te Resim Ekleme
linktitle: Java PostScript'te Resim Ekleme
second_title: Aspose.Page Java API'si
description: PostScript belgelerine resim ekleme hakkındaki bu eğitimde Aspose.Page Java'nın kusursuz entegrasyonunu keşfedin. Belge işleme yeteneklerinizi yükseltin.
type: docs
weight: 10
url: /tr/java/postscript-image-manipulation/add-image/
---
## giriiş
Bu eğitimde Aspose.Page for Java kütüphanesini kullanarak Java PostScript belgesine nasıl resim ekleneceğini inceleyeceğiz. Aspose.Page, PostScript dosyalarıyla çalışmak için çeşitli özellikler sunan, geliştiricilerin belgelerini sorunsuz bir şekilde değiştirmesine ve geliştirmesine olanak tanıyan güçlü bir kitaplıktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Page Java kütüphanesi için. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
- Java programlamanın temel anlayışı.
## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın. Referans olarak aşağıdaki kod parçacığını kullanın:
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Adım 1: Grafik Yazma Kaydetme
İlk adım, grafik kaydının belgeye yazılmasını içerir. Bu, daha sonra yapılan tüm dönüşümlerin veya değişikliklerin gerektiğinde geri alınabilmesini sağlar.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
// Sayfa açıkken yeni PS Belgesi oluşturun
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## 2. Adım: Çevir ve Dönüştür
Daha sonra belgeyi çevirin ve görüntü dosyasından bir BufferedImage nesnesi oluşturun. AffinTransform'u kullanarak ölçeklendirme ve döndürme gibi bir dizi dönüşüm uygulayın.
```java
document.translate(100, 100);
// Görüntü dosyasından BufferedImage nesnesi oluşturun
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Görüntü dönüşümü oluştur
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## 3. Adım: Belgeye Resim Ekleme
Şimdi dönüştürülen görüntüyü belgeye ekleyin.
```java
document.drawImage(image, transform, null);
```
## Adım 4: Grafik Geri Yüklemeyi Yazma
Görüntüyü ekledikten sonra, yapılan değişiklikleri sonlandırmak için grafik geri yüklemesini yazın.
```java
document.writeGraphicsRestore();
```
## 5. Adım: Geçerli Sayfayı Kapatın ve Kaydedin
Geçerli sayfayı kapatın ve belgeyi kaydedin.
```java
document.closePage();
document.save();
```
Birden fazla görüntü eklemek için bu adımları tekrarlayın veya gereksinimlerinize göre dönüşümleri özelleştirin.
## Çözüm
 Tebrikler! Aspose.Page for Java'yı kullanarak Java PostScript belgesine nasıl görsel ekleyeceğinizi başarıyla öğrendiniz. Keşfedin[dokümantasyon](https://reference.aspose.com/page/java/) daha gelişmiş özellikler ve işlevler için.
## SSS
### Aspose.Page for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Page öncelikle Java'yı destekler ancak diğer programlama dilleri için de versiyonlar mevcuttur.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java ile ilgili topluluk desteğini ve tartışmaları nerede bulabilirim?
 Ziyaret edin[Aspose.Page Forumu](https://forum.aspose.com/c/page/39) topluluk desteği için.
### Aspose.Page for Java'yı satın almak için ek kaynaklar var mı?
 Kütüphaneyi satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).