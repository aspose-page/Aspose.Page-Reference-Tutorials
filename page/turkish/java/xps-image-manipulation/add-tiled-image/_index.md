---
date: 2025-12-28
description: Aspose.Page kullanarak Java'da XPS belgesi oluşturmayı ve adım adım rehberimizle
  döşeli resmi zahmetsizce eklemeyi öğrenin.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Java'da Döşeli Görüntü ile XPS Belgesi Nasıl Oluşturulur
url: /tr/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Belgesi Oluşturma ve Java'da Döşeli Görüntü Ekleme

## Giriş
Modern Java geliştirmesinde, **XPS belgesi** dosyalarını programlı olarak oluşturma yeteneği, özellikle bunları döşeli görüntüler gibi grafiklerle zenginleştirmeniz gerektiğinde değerli bir beceridir. Aspose.Page for Java bu süreci basitleştirir, düşük seviyeli dosya işlemleriyle uğraşmak yerine görsel tasarıma odaklanmanızı sağlar. Bu öğreticide, bir XPS belgesi nasıl oluşturulur, **döşeli görüntü** nasıl eklenir ve sonuç nasıl kaydedilir, tüm bunları net, adım adım kod örnekleriyle öğreneceksiniz.

## Hızlı Yanıtlar
- **Aspose.Page ne yapar?** Java'da XPS belgeleri oluşturmak ve manipüle etmek için yüksek seviyeli bir API sağlar.  
- **Bir görüntüyü döşeyebilir miyim?** Evet – `XpsImageBrush` ile `XpsTileMode.Tile` kullanın.  
- **Lisans gerekiyor mu?** Üretim kullanımı için geçici veya ticari bir lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** JDK 8 ve üzeri uyumludur.  
- **Uygulama ne kadar sürer?** Temel bir döşeli‑görüntü senaryosu için yaklaşık 10–15 dakika.

## “XPS belgesi oluşturma” nedir?
XPS (XML Paper Specification) dosyası, PDF'ye benzer sabit düzenli bir belge formatıdır. XPS belgesini programlı olarak oluşturmak, Java kodundan doğrudan yazdırılabilir, cihaz bağımsız dosyalar üretmenizi sağlar.

## Neden döşeli bir görüntü eklenir?
Bir görüntüyü döşemek, grafiği tanımlı bir alanda tekrar eder ve bu, arka planlar, filigranlar veya desen dolguları için mükemmeldir. Aspose.Page’in `XpsTileMode.Tile` özelliğini kullanarak bunu sadece birkaç kod satırıyla gerçekleştirebilirsiniz.

## Ön Koşullar
1. **Java Development Kit (JDK)** – JDK 8 veya daha yeni bir sürüm yüklü.  
2. **Aspose.Page for Java** – [web sitesinden](https://releases.aspose.com/page/java/) indirin.  
3. **Yazılabilir bir dizin** – oluşturulan XPS dosyasının kaydedileceği yer.

## Paketleri İçe Aktarma
Java projenizde, gerekli sınıfları içe aktarın:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Adım Adım Kılavuz

### Adım 1: Projenizi Kurun
Aspose.Page JAR dosyalarını projenizin sınıf yoluna ekleyin ve içe aktarma ifadelerinin hatasız derlendiğini doğrulayın.

### Adım 2: XPS Belgesi Oluşturun
Yeni bir `XpsDocument` nesnesi oluşturun. Bu, tüm sayfaları, yolları ve kaynakları tutacak temel kapsayıcıdır.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Adım 3: Döşeli Görüntü Yolunu Tanımlayın
Döşemek istediğiniz görüntüyü (ör. `R08LN_NN.jpg`) `dataDir` tarafından referans verilen dizine yerleştirin. Görüntü, bir fırça deseni olarak kullanılacak.

### Adım 4: Döşeli Görüntü Ekle
Dikdörtgen bir yol oluşturun ve bunu bir `XpsImageBrush` ile doldurun. Döşeme modunu `Tile` olarak ayarlayarak, görüntü dikdörtgen boyunca tekrar eder.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Adım 5: Belgeyi Kaydedin
XPS dosyasını diske kaydedin. Çıktı dosyası, az önce tanımladığınız döşeli görüntüyü içerecek.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Aynı XPS belgesi içinde diğer sayfalara veya şekillere **döşeli görüntü eklemeniz** gerektiğinde bu adımları tekrarlayın.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| Görüntü görünmüyor | Dosya yolunun (`dataDir + \"R08LN_NN.jpg\"`) doğru olduğundan ve görüntünün erişilebilir olduğundan emin olun. |
| Döşeme deseni uzamış görünüyor | `Rectangle2D` kaynak ve hedef değerlerini ayarlayarak döşeme boyutunu kontrol edin. |
| Opaklık etkisiz | Fırçanın opaklığının **döşeme modu** yapılandırmasından **sonra** ayarlandığından emin olun. |

## Sıkça Sorulan Sorular

### Aspose.Page tüm Java sürümleriyle uyumlu mu?
Aspose.Page çeşitli Java sürümleriyle çalışacak şekilde tasarlanmıştır. Uyumluluğu kontrol etmek için belgeleri [buradan](https://reference.aspose.com/page/java/) inceleyin.

### Aspose.Page'i ticari projelerde kullanabilir miyim?
Evet, Aspose.Page ticari lisanslar sunar. Lisansları [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

### Ücretsiz deneme mevcut mu?
Evet, Aspose.Page özelliklerini ücretsiz deneme ile [buradan](https://releases.aspose.com/) keşfedebilirsiniz.

### Topluluk desteği ve tartışmalarını nerede bulabilirim?
Aspose.Page topluluğu ile [forumda](https://forum.aspose.com/c/page/39) etkileşime geçin.

### Aspose.Page için geçici bir lisans nasıl alabilirim?
Geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-28  
**Test Edilen:** Aspose.Page for Java 24.12 (latest)  
**Yazar:** Aspose  

---