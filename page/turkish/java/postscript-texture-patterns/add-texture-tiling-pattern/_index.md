---
title: Java PostScript'te Doku Döşeme Deseni Ekleme
linktitle: Java PostScript'te Doku Döşeme Deseni Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java ile PostScript belgelerine zahmetsizce doku döşeme desenleri ekleyin. Yaratıcı olanaklar için kusursuz entegrasyon kılavuzumuzu keşfedin.
weight: 10
url: /tr/java/postscript-texture-patterns/add-texture-tiling-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Doku Döşeme Deseni Ekleme

## giriiş
Java geliştirme alanında, PostScript belgelerinde karmaşık desenler ve dokular oluşturmak yaygın bir gereksinimdir. Aspose.Page for Java, bu görevi zahmetsizce gerçekleştirmede değerli bir araç olduğunu kanıtlıyor. Bu eğitimde, Aspose.Page'i kullanarak Java PostScript belgesine doku döşeme deseni ekleme sürecinde size rehberlik edeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java programlama dilinin temel anlayışı.
- PostScript belge yapısına aşinalık.
-  Aspose.Page for Java kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
## Paketleri İçe Aktar
Java projeniz için gerekli paketleri içe aktararak başlayın:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 1. Adım: PostScript Belgesi Oluşturun
Çıkış akışını ve kaydetme seçeneklerini belirterek yeni bir PostScript belgesi oluşturarak başlayın. Gerekli yolların yapılandırıldığından emin olun.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
// Sayfa açıkken yeni PS Belgesi oluşturun
PsDocument document = new PsDocument(outPsStream, options, false);
// Sayfa açıkken yeni PS Belgesi oluşturun
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Adım 2: Grafik Ortamını Ayarlayın
Orijini çevirerek ve doku görüntü dosyasından BufferedImage oluşturarak grafik ortamını ayarlayın.
```java
document.writeGraphicsSave();
document.translate(200, 100);
// Görüntü dosyasından BufferedImage nesnesi oluşturun
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
## Adım 3: Doku Fırçası Oluşturun
Dokunun kaplayacağı alanı belirterek görüntüden bir doku fırçası tanımlayın.
```java
// Genişliği iki katına çıkan görüntü alanı oluşturun
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Görüntüden doku fırçası oluşturun
TexturePaint paint = new TexturePaint(image, imageArea);
```
## Adım 4: Şekilleri Çizin ve Doldurun
Bir dikdörtgen oluşturun ve onu tanımlanmış doku fırçasıyla doldurun. Ek olarak, görsel çekicilik için şekli çizin ve ana hatlarını çizin.
```java
// Dikdörtgen oluştur
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Bu doku fırçasını geçerli boya olarak ayarla
document.setPaint(paint);
// Dikdörtgeni doldur
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
## Adım 5: Doku Desenli Metin Ekleme
Belgeye metin ekleyin ve onu doku deseniyle doldurun/konturlayın. Yazı tipini, konumu ve diğer parametreleri gerektiği gibi özelleştirin.
```java
// Metni doku deseniyle doldurun
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Metni doku deseniyle ana hatlarıyla belirtin
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Adım 6: Kaydet ve Kapat
Mevcut sayfayı kapatarak, belgeyi kaydederek ve sorunsuz bir yürütme sağlayarak süreci sonlandırın.
```java
// Geçerli sayfayı kapat
document.closePage();
// Belgeyi kaydet
document.save();
```
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak Java PostScript belgesine başarıyla doku döşeme deseni eklediniz. Daha fazla özelleştirme seçeneğini keşfetmekten ve bu güçlü kitaplığın tüm potansiyelini açığa çıkarmaktan çekinmeyin.

## SSS'ler
### Aspose.Page for Java yeni başlayanlar için uygun mu?
Kesinlikle! Aspose.Page for Java, kapsamlı belgeler sunarak her düzeydeki geliştiricinin erişebilmesini sağlar.
### Aspose.Page for Java'yı mevcut Java projeme entegre edebilir miyim?
 Evet, sağlanan belgeleri takip ederek Aspose.Page for Java'yı projenize kolayca entegre edebilirsiniz.[Burada](https://reference.aspose.com/page/java/).
### Aspose.Page ile ilgili soruları nerede bulabilirim veya tartışabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) toplulukla etkileşime geçmek ve yardım istemek.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Ziyaret etmek[bu bağlantı](https://purchase.aspose.com/temporary-license/) geçici lisans almak için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
