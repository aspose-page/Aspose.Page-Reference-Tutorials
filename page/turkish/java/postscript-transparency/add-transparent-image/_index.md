---
date: 2025-12-18
description: Aspose.Page for Java kullanarak postscript belgesi oluşturmayı ve şeffaf
  bir görüntü eklemeyi öğrenin. Bu kılavuz, postscript'e görüntü eklemeyi zahmetsiz
  bir şekilde gösterir.
linktitle: Create PostScript Document Java – Add Transparent Image
second_title: Aspose.Page Java API
title: Java ile PostScript Belgesi Oluştur – Şeffaf Görüntü Ekle
url: /tr/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Şeffaf Görüntü Ekleme

## Giriş
Java PostScript dünyasında, belgelerin görsel çekiciliğini artırmak genellikle şeffaf görüntüler eklemeyi içerir. Bu öğretici, güçlü Aspose.Page for Java kütüphanesini kullanarak **create postscript document java** sürecine şeffaf grafikler eklemenizi sağlayacak. Görüntüyü PostScript'e nasıl ekleyeceğinizi, tam olarak nasıl konumlandıracağınızı ve opaklığını nasıl kontrol edeceğinizi göreceksiniz; böylece profesyonel görünümlü sonuçlar elde edebileceksiniz.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Aspose.Page for Java ile bir PostScript belgesine şeffaf PNG ekleme.  
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java (resmi web sitesinden indirin).  
- **Lisans gerekiyor mu?** Üretim için geçici veya tam lisans gereklidir; ücretsiz deneme mevcuttur.  
- **Başka görüntü formatları kullanabilir miyim?** Evet, ancak alfa kanallı PNG şeffaflık için en iyisidir.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 10‑15 dakika.

## Java'da PostScript belgesi nedir?
PostScript belgesi, metin, grafik ve görüntüleri tanımlayan bir sayfa tanımlama dili dosyasıdır. Java kullanarak bu dosyaları programlı bir şekilde oluşturabilir, düzen ve render üzerinde tam kontrol sağlayabilirsiniz. **create postscript document java** anahtar kelimesi bu yeteneği yansıtır.

## Neden şeffaf görüntüler eklenir?
Şeffaf görüntüler, alttaki içeriği gizlemeden grafikler yerleştirmenizi sağlar; su işaretleri, logolar veya dekoratif öğeler için mükemmeldir. Şeffaflık ve hassas konumlandırmanın birleşimi, markaya tutarlı, cilalı belgeler oluşturur.

## Önkoşullar
Öğreticiye başlamadan önce aşağıdaki önkoşulların sağlandığından emin olun:
1. Java Development Kit (JDK): Makinenizde en son JDK'nın yüklü olduğundan emin olun.  
2. Aspose.Page for Java: Aspose.Page for Java kütüphanesini [website](https://releases.aspose.com/page/java/) adresinden indirin ve kurun.  
3. Belge Dizini: Sisteminizde Java PostScript belgelerinizi saklayacağınız bir dizin oluşturun.  
4. Şeffaf Görüntü Dosyası: Öğreticide kullanmak üzere şeffaf bir görüntü dosyası (ör. "mask1.png") hazırlayın.

## Paketleri İçe Aktarma
Java projenizde Aspose.Page for Java tarafından sağlanan işlevselliği kullanmak için gerekli paketleri içe aktarın. Aşağıda tam olarak ihtiyacınız olan import bloğu yer almaktadır:

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Şeffaf bir görüntü ile create postscript document java nasıl oluşturulur?
Aşağıda adım adım bir rehber bulunmaktadır. Her adım kısa bir açıklama ve ardından değiştirilmemiş orijinal kod bloğunu içerir.

### Adım 1: Arka Plan Rengini Ayarla
PostScript belgesini oluşturuyor, bir çıktı akışı açıyor ve şeffaf görüntü için görsel referans olarak kırmızı bir dikdörtgen çiziyoruz.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

### Adım 2: Koordinatları Çevir
Çizim yapmadan önce, görüntünün istediğimiz konumda görünmesi için sayfa üzerindeki orijini uygun bir konuma taşıyoruz.

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

### Adım 3: Görüntü Nesnesi Oluştur
Alfa kanalı içeren PNG dosyasını yüklüyoruz. Bu görüntü, hem opak hem de şeffaf render için kullanılacak.

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

### Adım 4: Opak Görüntü Ekle
İlk olarak, görüntüyü normal bir RGB bitmap olarak çiziyoruz. Bu, daha sonra şeffaflık uyguladığımızda farkı gösterecek.

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

### Adım 5: Şeffaf Görüntü Ekle
Şimdi aynı görüntüyü tam opaklık (255) ya da 0‑255 arasında herhangi bir değerle şeffaflık kontrolü yaparak çiziyoruz. Burada tam opaklık için 255 kullandık, ancak değeri düşürerek geçişli bir etki elde edebilirsiniz.

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

### Adım 6: Kaydet ve Kapat
Son olarak, grafik durumunu geri yüklüyor, sayfayı kapatıyor ve belgeyi diske kaydediyoruz.

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Yaygın Sorunlar ve Çözümleri
- **FileNotFoundException** – `dataDir`'in doğru klasöre işaret ettiğini ve `mask1.png` dosyasının mevcut olduğunu doğrulayın.  
- **ImageIO.read returns null** – PNG'nin geçerli bir formatta olduğundan ve bozuk olmadığından emin olun.  
- **Transparent image appears opaque** – `drawTransparentImage`'in üçüncü parametresini ayarlayın (0 = tamamen şeffaf, 255 = tamamen opak).  

## Sıkça Sorulan Sorular
### Aspose.Page for Java'yı diğer Java kütüphaneleriyle kullanabilir miyim?
Evet, Aspose.Page for Java diğer Java kütüphaneleriyle sorunsuz bir şekilde entegre edilerek belge işleme yetenekleri artırılabilir.

### Aspose.Page for Java için ücretsiz deneme mevcut mu?
Evet, Aspose.Page for Java için ücretsiz denemeye [buradan](https://releases.aspose.com/) erişebilirsiniz.

### Aspose.Page for Java için geçici lisans nasıl alınır?
Geçici lisansı [bu bağlantıdan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### Aspose.Page for Java desteği için forum var mı?
Evet, topluluk desteği ve tartışmalar için [Aspose.Page for Java forumunu](https://forum.aspose.com/c/page/39) ziyaret edebilirsiniz.

### Aspose.Page for Java belgelerini nerede bulabilirim?
Aspose.Page for Java hakkında ayrıntılı bilgi için kapsamlı [belgelere](https://reference.aspose.com/page/java/) bakın.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak **create postscript document java** oluşturmayı ve şeffaf görüntüler eklemeyi başarıyla öğrendiniz. Farklı görüntüler, opaklık seviyeleri ve konumlarla deneyler yaparak markanızın ihtiyaçlarını karşılayan görsel açıdan çarpıcı belgeler oluşturabilirsiniz.

---

**Son Güncelleme:** 2025-12-18  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11 (yazım anındaki en son)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}