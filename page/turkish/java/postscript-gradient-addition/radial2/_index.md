---
date: 2025-12-08
description: Aspose.Page kullanarak Java PostScript'te bir radyal degrade örneği oluşturmayı
  öğrenin. Tam kod ve sorun giderme ile adım adım rehber.
language: tr
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Radial Gradient Örneği: Aspose.Page ile Java PostScript'
url: /java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radial Gradient Örneği: Aspose.Page ile Java PostScript

## Giriş
Bu öğreticide, Aspose.Page for Java kullanarak bir PostScript belgesi için **radial gradient örneği** oluşturacaksınız. Proje kurulumundan, pürüzsüz bir radial gradient ile doldurulmuş bir daireyi render etmeye kadar her adımı adım adım göstereceğiz; böylece Java uygulamalarınıza anında göz alıcı grafikler ekleyebilirsiniz.

## Hızlı Yanıtlar
- **Bu öğreticinin oluşturduğu şey nedir?** Radial gradient ile doldurulmuş bir daire içeren bir PostScript dosyası (`.ps`).  
- **Hangi kütüphane gereklidir?** Aspose.Page for Java (en son sürüm).  
- **Uygulama ne kadar sürer?** Çalışan bir örnek için yaklaşık 10‑15 dakika.  
- **Lisans gerekli mi?** Üretim kullanımı için geçici ya da tam lisans gerekir; geliştirme için ücretsiz deneme sürümü çalışır.  
- **Kodu PDF veya SVG için yeniden kullanabilir miyim?** Evet—Aspose.Page, minimal değişikliklerle birden fazla çıktı formatını destekler.

## Radial Gradient Nedir?
Radial gradient, renkleri merkez noktasından dışa doğru geçiş yaparak pürüzsüz, dairesel bir karışım oluşturur. Vurgular, düğme arka planları veya doğal bir “parıltı” etkisi gerektiren herhangi bir görsel için idealdir.

## Aspose.Page'i Radial Gradient'ler İçin Neden Kullanmalı?
- **Cihaz bağımsız render** – PostScript, PDF, SVG ve daha fazlasında aynı şekilde çalışır.  
- **Tam Java entegrasyonu** – yerel kod yok, sadece saf Java API'leri.  
- **Yüksek kaliteli çıktı** – anti-aliasing ve renk uzayı kontrolünü destekler.

## Ön Koşullar
Başlamadan önce, şunların olduğundan emin olun:

- Java programlamaya temel aşinalık.  
- Makinenizde JDK 8 veya daha yeni bir sürüm yüklü.  
- Aspose.Page for Java kütüphanesi ([Aspose.Page Java belgelerinden](https://reference.aspose.com/page/java/) indirilebilir).

## Paketleri İçe Aktar
İlk olarak, ihtiyacımız olan sınıfları içe aktarın. Bunlar standart AWT grafik türlerini ve Aspose.Page API'sini içerir.

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

## Adım 1: Belge Dizinini Ayarla
Oluşturulan PostScript dosyasının kaydedileceği klasörü tanımlayın. Yer tutucuyu sisteminizdeki gerçek bir yol ile değiştirin.

```java
String dataDir = "Your Document Directory";
```

## Adım 2: Çıktı Akışı Oluştur
Hedef `.ps` dosyasına işaret eden bir `FileOutputStream` açın. Bu akış, Aspose.Page tarafından oluşturulan ikili veriyi besler.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Adım 3: Kaydetme Seçeneklerini Oluştur
`PsSaveOptions` nesnesini oluşturun. Sayfa boyutu, sıkıştırma vb. özelleştirebilirsiniz, ancak bu örnek için varsayılanlar yeterlidir.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Adım 4: PS Belgesi Oluştur
`PsDocument` nesnesini oluşturun, çıktı akışını ve kaydetme seçeneklerini geçirin. `false` bayrağı, Aspose.Page'in otomatik olarak bir sayfa açmasını engeller (biz manuel olarak açacağız).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 5: Bir Daire Oluştur
`Ellipse2D.Float` kullanarak bir daire çizeceğiz. Parametreler `(x, y, width, height)` şeklindedir. Genişlik = yükseklik ayarı mükemmel bir daire oluşturur.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Adım 6: Gradient Renklerini Tanımla
İki dizi hazırlayın: gradient içinde görünecek renkler için bir dizi ve karşılık gelen kesirli konumlar (0 = merkez, 1 = kenar) için bir dizi.

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Adım 7: AffineTransform Oluştur
`AffineTransform`, gradient'i dairemize sığdırmak için ölçeklendirir ve çevirir. `(scaleX, 0, 0, scaleY, translateX, translateY)` matrisi bu işi yapar.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Adım 8: Radial Gradient Paint Oluştur
Şimdi `RadialGradientPaint` nesnesini oluşturuyoruz. Merkez nokta, yarıçap, odak noktası, renk kesirleri, renk dizisi, döngü yöntemi, renk uzayı ve az önce tanımladığımız dönüşüm bu nesneye parametre olarak verilir.

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

## Adım 9: Paint'i Ayarla ve Daireyi Doldur
Gradient paint'i belgeye uygulayın ve önceden tanımlanan daireyi doldurun. Bu, **radial gradient örneğimizin** çekirdeğidir.

```java
document.setPaint(paint);
document.fill(circle);
```

## Adım 10: Sayfayı Kapat ve Belgeyi Kaydet
Sayfayı tamamlayın, içeriği diske yazın ve akışı kapatın. PostScript dosyanız artık herhangi bir PS görüntüleyiciyle görüntülenmeye hazır.

```java
document.closePage();
document.save();
```

Tebrikler! Aspose.Page kullanarak Java PostScript'te başarılı bir şekilde radial gradient örneği oluşturdunuz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|-------|
| **FileNotFoundException** çıktıyı akışı açarken | `dataDir`'in mevcut bir klasöre işaret ettiğini ve yazma izniniz olduğunu doğrulayın. |
| Gradient düz veya eksik görünüyor | `fractions` dizisinin `colors` dizisi uzunluğuyla eşleştiğinden ve `AffineTransform`'un doğru ölçeklendirdiğinden emin olun. |
| Renkler ters görünüyor | `colors` dizisindeki renk sırasını değiştirin veya `focus` nokta koordinatlarını ayarlayın. |

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java belgelerini nerede bulabilirim?**  
C: Tam API referansı [burada](https://reference.aspose.com/page/java/) mevcuttur.

**S: Aspose.Page for Java'ı nasıl indirebilirim?**  
C: En son JAR dosyasını [sürümler sayfasından](https://releases.aspose.com/page/java/) alın.

**S: Ücretsiz deneme sürümü var mı?**  
C: Evet—deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Test için geçici bir lisans alabilir miyim?**  
C: Kesinlikle, [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) bir tane talep edebilirsiniz.

**S: Topluluk desteğini nereden alabilirim?**  
C: [Aspose.Page forumunda](https://forum.aspose.com/c/page/39) tartışmaya katılabilirsiniz.

## Sonuç
Bu rehberde, Aspose.Page for Java kullanarak bir PostScript belgesi için tam bir **radial gradient örneği** oluşturduk. Adımları izleyerek artık karmaşık gradientler oluşturmak için yeniden kullanılabilir bir deseniniz var; bunu PDF, SVG veya diğer desteklenen formatlara uyarlayabilirsiniz. Java grafik projelerinizi zenginleştirmek için farklı renkler, yarıçaplar ve şekillerle deneyler yapın.

---

**Son Güncelleme:** 2025-12-08  
**Test Edilen:** Aspose.Page for Java 24.11 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}