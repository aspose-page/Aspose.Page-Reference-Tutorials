---
date: 2026-02-13
description: Aspose.Page kullanarak Java PostScript'te şekli degrade ile doldurmayı
  ve degrade ile daire çizmeyi öğrenin. Kod ve ipuçlarıyla adım adım rehber.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Şekli Gradyanla Doldur: Java PostScript Radyal Örneği'
url: /tr/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Doldur Şekli Gradyan ile: Java PostScript Radial Örneği

## Giriş
Bu öğreticide, Aspose.Page for Java kullanarak bir PostScript belgesi için radial gradyan örneği oluşturarak **fill shape with gradient** nasıl yapılacağını öğreneceksiniz. Projeyi kurmaktan, pürüzsüz bir radial gradyanla doldurulmuş bir daireyi renderlemeye kadar her adımı adım adım göstereceğiz—böylece Java uygulamalarınıza anında göz alıcı grafikler ekleyebilirsiniz.

## Hızlı Yanıtlar
- **Bu öğretici ne oluşturur?** Radial gradyanla doldurulmuş bir daire içeren bir PostScript dosyası (`.ps`).  
- **Hangi kütüphane gereklidir?** Aspose.Page for Java (en son sürüm).  
- **Uygulama ne kadar sürer?** Çalışan bir örnek için yaklaşık 10‑15 dakika.  
- **Lisans gerekli mi?** Üretim kullanımı için geçici veya tam lisans gerekir; geliştirme için ücretsiz deneme sürümü çalışır.  
- **Kodu PDF veya SVG için yeniden kullanabilir miyim?** Evet—Aspose.Page, minimal değişikliklerle birden fazla çıktı formatını destekler.

## PostScript'te Şekli Gradyan ile Doldurma
Kodun içine dalmadan önce, “fill shape with gradient” neden önemli açıklayalım. Gradyanlar, raster görüntülere ihtiyaç duymadan grafiklerinize profesyonel, üç‑boyutlu bir his verir. Aspose.Page ile aynı gradyan mantığını herhangi bir vektör şekline—daireler, dikdörtgenler veya özel yollar—tüm desteklenen çıktı formatlarında (PostScript, PDF, SVG) uygulayabilirsiniz.

## Radial Gradyan Nedir?
Radial gradyan, renkleri merkezi bir noktadan dışa doğru geçiş yaparak pürüzsüz, dairesel bir karışım oluşturur. Vurgulamalar, düğme arka planları veya doğal bir “parıltı” etkisi gerektiren görseller için idealdir.

## Neden Aspose.Page'i Radial Gradyanlar İçin Kullanmalısınız?
- **Cihaz‑bağımsız renderleme** – PostScript, PDF, SVG ve daha fazlasında aynı şekilde çalışır.  
- **Tam Java entegrasyonu** – yerel kod yok, sadece saf Java API'leri.  
- **Yüksek‑kaliteli çıktı** – anti-aliasing ve renk uzayı kontrolünü destekler.

## Ön Koşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:

- Java programlamaya temel aşinalık.  
- Makinenizde JDK 8 veya daha yeni bir sürüm yüklü.  
- Aspose.Page for Java kütüphanesi ([Aspose.Page Java documentation](https://reference.aspose.com/page/java/) adresinden indirin).  

## Paketleri İçe Aktarma
İhtiyacımız olan sınıfları içe aktaralım. Bunlar standart AWT grafik tiplerini ve Aspose.Page API'sini içerir.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım 1: Belge Dizini Ayarlama
Oluşturulan PostScript dosyasının kaydedileceği klasörü tanımlayın. Yer tutucuyu sisteminizdeki gerçek bir yol ile değiştirin.

```java
String dataDir = "Your Document Directory";
```

## Adım 2: Çıktı Akışı Oluşturma
Hedef `.ps` dosyasına işaret eden bir `FileOutputStream` açın. Bu akış, Aspose.Page tarafından üretilen ikili verileri besler.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Adım 3: Kaydetme Seçeneklerini Oluşturma
`PsSaveOptions` nesnesini örnekleyin. Sayfa boyutu, sıkıştırma vb. özelleştirilebilir, ancak bu örnek için varsayılanlar yeterlidir.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Adım 4: PS Belgesi Oluşturma
Çıktı akışı ve kaydetme seçeneklerini geçirerek `PsDocument` nesnesini oluşturun. `false` bayrağı, Aspose.Page'in otomatik olarak bir sayfa açmasını engeller (biz manuel olarak açacağız).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 5: Bir Daire Oluşturma
`Ellipse2D.Float` kullanarak bir daire çizeceğiz. Parametreler `(x, y, width, height)` şeklindedir. Genişlik = yükseklik ayarı mükemmel bir daire oluşturur.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Daireyi Gradyan ile Çizme
Şimdi bir şeklimiz var, bir sonraki adım **draw circle with gradient**. Daireye bir `RadialGradientPaint` uygulayarak, doldurma işlemi tanımladığımız gradyanı otomatik olarak kullanır.

## Adım 6: Gradyan Renklerini Tanımlama
İki dizi hazırlayın: gradyanda görünecek renkler ve karşılık gelen kesirli konumlar (0 = merkez, 1 = kenar).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Adım 7: AffineTransform Oluşturma
`AffineTransform`, gradyanı dairemize sığacak şekilde ölçeklendirir ve çevirir. Matris `(scaleX, 0, 0, scaleY, translateX, translateY)` işi görür.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Adım 8: Radial Gradient Paint Oluşturma
Şimdi `RadialGradientPaint` nesnesini oluşturuyoruz. Merkez noktası, yarıçap, odak noktası, renk kesirleri, renk dizisi, döngü yöntemi, renk uzayı ve az önce tanımladığımız dönüşüm bu nesneye geçirilir.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Adım 9: Boyayı Ayarla ve Daireyi Doldur
Gradyan boyasını belgeye uygulayın ve önceden tanımlanan daireyi doldurun. Bu, **radial gradient example**'ımızın çekirdeğidir ve **fill shape with gradient** nasıl yapılır gösterir.

```java
document.setPaint(paint);
document.fill(circle);
```

## Adım 10: Sayfayı Kapat ve Belgeyi Kaydet
Sayfayı sonlandırın, içeriği diske yazın ve akışı kapatın. PostScript dosyanız artık herhangi bir PS görüntüleyici ile görüntülenebilir.

```java
document.closePage();
document.save();
```

Tebrikler! Aspose.Page kullanarak Java PostScript'te bir radial gradyan örneği başarıyla oluşturdunuz. Artık **fill shape with gradient** için yeniden kullanılabilir bir deseniniz var; bu desen diğer şekillere ve çıktı formatlarına kolayca uyarlanabilir.

## Yaygın Sorunlar ve Çözümler
| Problem | Çözüm |
|---------|----------|
| **FileNotFoundException** çıktı akışı açılırken | `dataDir`'in mevcut bir klasöre işaret ettiğini ve yazma izniniz olduğunu doğrulayın. |
| Gradyan düz veya eksik görünüyor | `fractions` dizisinin `colors` dizisi uzunluğuyla eşleştiğinden ve `AffineTransform`'un doğru ölçeklediğinden emin olun. |
| Renkler ters görünüyor | `colors` dizisindeki renk sırasını değiştirin veya `focus` noktasının koordinatlarını ayarlayın. |

## Sık Sorulan Sorular

**S: Aspose.Page for Java dokümantasyonunu nereden bulabilirim?**  
C: Tam API referansı [burada](https://reference.aspose.com/page/java/) mevcuttur.

**S: Aspose.Page for Java'ı nasıl indirebilirim?**  
C: En son JAR dosyasını [releases page](https://releases.aspose.com/page/java/) üzerinden alın.

**S: Ücretsiz bir deneme sürümü mevcut mu?**  
C: Evet—deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Test için geçici bir lisans alabilir miyim?**  
C: Kesinlikle, bir tane için [temporary license page](https://purchase.aspose.com/temporary-license/) adresinden talepte bulunun.

**S: Topluluk desteği nereden alınır?**  
C: [Aspose.Page forum](https://forum.aspose.com/c/page/39) üzerinden tartışmaya katılabilirsiniz.

## Sonuç
Bu rehberde Aspose.Page for Java kullanarak bir PostScript belgesi için tam bir **radial gradient example** oluşturduk. Adımları izleyerek artık **fill shape with gradient** için yeniden kullanılabilir bir deseniniz var; bu deseni PDF, SVG veya Aspose.Page'in desteklediği diğer formatlara uyarlayabilirsiniz. Farklı renkler, yarıçaplar ve şekiller deneyerek Java grafik projelerinizi zenginleştirin.

---

**Son Güncelleme:** 2026-02-13  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}