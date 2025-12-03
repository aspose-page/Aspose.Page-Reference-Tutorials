---
date: 2025-12-03
description: Aspose.Page for Java kullanarak PostScript olarak kaydetmeyi ve şekilleri
  kırpmayı keşfedin. Java grafik kırpma işleminde çizgi stilini ayarlamayı ve kırpma
  bölgesini uygulamayı öğrenin.
language: tr
linktitle: Save as PostScript – Clipping in Java Page Manipulation
second_title: Aspose.Page Java API
title: PostScript olarak Kaydet – Java Sayfa Manipülasyonunda Kırpma
url: /java/page-manipulation/clipping/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript Olarak Kaydet – Java Sayfa Manipülasyonunda Kırpma

## Giriş
Karmaşık grafikler oluştururken **PostScript olarak kaydet** ihtiyacınız olduğunda, kırpma en güçlü yardımcınız olur. Aspose.Page for Java ile Java Sayfa Manipülasyonunda kırpma, çizim işlemlerinin görünür olduğu kesin bölgeleri tanımlamanızı sağlar ve nihai çıktınız üzerinde ince ayar kontrolü sunar. Bu öğreticide **şekilleri nasıl kırpacağınızı**, **çizgi stilini nasıl ayarlayacağınızı** ve **kırpma bölgesini nasıl uygulayacağınızı** Aspose.Page for Java kütüphanesini kullanarak adım adım gösteriyoruz, böylece güvenle profesyonel PostScript dosyaları üretebilirsiniz.

## Hızlı Yanıtlar
- **“PostScript olarak kaydet” ne anlama geliyor?**  
  Vektör grafikleri PostScript dilinde saklayan bir .ps dosyası oluşturur; bu dosya baskı ve yüksek çözünürlüklü render için idealdir.  
- **Java’da kırpmayı hangi kütüphane yönetiyor?**  
  Aspose.Page for Java, `java graphics clipping` için basit bir API sağlar.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?**  
  Test için geçici bir lisans yeterlidir; üretim ortamı için ticari lisans gereklidir.  
- **Çizgi görünümünü değiştirebilir miyim?**  
  Evet—`set stroke style` ile `BasicStroke` kullanarak genişlik, kesik desen ve uçları özelleştirebilirsiniz.  
- **Kod Java 8+ ile uyumlu mu?**  
  Kesinlikle, örnek herhangi bir Java 8 veya daha yeni çalışma zamanı üzerinde çalışır.

## Aspose.Page’de “PostScript olarak kaydet” nedir?
Bir belgeyi PostScript olarak kaydetmek, çizim komutlarınızı PostScript sayfa tanım dili haline dönüştürür. Oluşan `.ps` dosyası yazıcılar, görüntüleyiciler tarafından açılabilir veya kalite kaybı olmadan PDF’ye dönüştürülebilir.

## Java grafiklerinde kırpma neden kullanılır?
Kırpma, **kırpma bölgesi** uygulayarak çizimi belirli şekillerle sınırlamanızı sağlar—maskeler, karmaşık düzenler oluşturmak veya sayfanın belirli bir alanına odaklanmak için mükemmeldir. Ayrıca görünür bölge dışındaki gereksiz çizim komutlarını ortadan kaldırarak dosya boyutunu azaltmaya yardımcı olur.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

- **Aspose.Page for Java** – [Aspose.Page documentation](https://reference.aspose.com/page/java/) adresinden indirin.  
- **Java Geliştirme Ortamı** – JDK 8 veya üzeri, tercih ettiğiniz IDE (IntelliJ, Eclipse vb.).

## Paketleri İçe Aktarma
Java projenizde gerekli sınıfları şu şekilde içe aktarın:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Bu içe aktarmalar, şekil tanımları, renk işleme, çizgi yapılandırması ve bir PostScript belgesi oluşturmak için Aspose.Page API’sine erişim sağlar.

## Adım‑Adım Kılavuz

### Adım 1: Belgeyi ve Çıktı Akışını Ayarlama
İlk olarak bir `PsDocument` oluşturun ve **PostScript** dosyasının yazılacağı çıktı akışını belirtin.

```java
String dataDir = "Your Document Directory";
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Clipping_outPS.ps");
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

> **İpucu:** `dataDir` yolunu mutlak tutun veya platform bağımsız yollar için `Paths.get(...)` kullanın.

### Adım 2: Şekilleri Oluşturma ve **şekilleri nasıl kırpacağınız**
Şimdi çalışacağımız geometrileri—bir dikdörtgen ve bir daire—tanımlıyoruz. Ardından daireyi kullanarak **kırpma bölgesi** uyguluyoruz; böylece sadece dairenin içindeki dikdörtgen kısmı render ediliyor.

```java
Shape rectangle = new Rectangle2D.Float(0, 0, 300, 200);
document.setPaint(Color.BLUE);
// Clipping by shape
document.writeGraphicsSave();
document.translate(100, 100);
Shape circle = new Ellipse2D.Float(50, 0, 200, 200);
document.clip(circle);
document.fill(rectangle);
document.writeGraphicsRestore();
```

`writeGraphicsSave()` / `writeGraphicsRestore()` çifti, grafik durumunu korur ve kırpmanın yalnızca amaçlanan çizim komutlarını etkilemesini sağlar.

### Adım 3: **Çizgi stilini ayarlama** ve konturu çizme
Kırpılmış dikdörtgeni doldurduktan sonra, özel bir kesik desenle dikdörtgenin kenarını çizerek **java graphics clipping** örneğini gösteriyoruz.

```java
document.translate(100, 100);
BasicStroke stroke = new BasicStroke(2, BasicStroke.CAP_BUTT, BasicStroke.JOIN_MITER, 10.0f, new float[]{5.0f}, 0.0f);
document.setStroke(stroke);
document.draw(rectangle);
```

Burada `BasicStroke`, 2 piksel genişliğinde ve 5 piksel kesik bir çizgi tanımlar; bu da **çizgi stilini ayarlama** sayesinde daha zengin görsel efektler elde etmenizi sağlar.

### Adım 4: Sayfayı kapatma ve **PostScript olarak kaydetme**
Son olarak sayfayı sonlandırın ve çıktı dosyasını yazın.

```java
document.closePage();
document.save();
```

`Clipping_outPS.ps` dosyanız artık dairesel bir bölgeyle kırpılmış mavi bir dikdörtgen ve kesikli bir kontur içeriyor—baskı veya daha ileri dönüşüm için hazır.

## Yaygın Sorunlar & Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|------|
| **Dosya bulunamadı** | `dataDir` yolu hatalı | Mutlak yol kullanın veya akışı oluştururken `new File(dataDir).mkdirs()` çağırın. |
| **Kırpma uygulanmadı** | `writeGraphicsSave()` / `writeGraphicsRestore()` eksik | Kırpma kodunu bu çağrılarla sarmaladığınızdan emin olun. |
| **Çizgi düz görünüyor** | `BasicStroke` kesik dizisi ayarlanmamış | Kesik desen dizisini (`new float[]{5.0f}`) doğru şekilde geçtiğinizi kontrol edin. |

## Sık Sorulan Sorular

### Aspose.Page farklı belge formatlarıyla uyumlu mu?
Evet, Aspose.Page çeşitli belge formatlarını destekler ve belge işleme görevlerinde çok yönlülük sağlar.

### Aspose.Page for Java’yı ticari projelerimde kullanabilir miyim?
Kesinlikle! Aspose.Page, kişisel ve ticari projelerde kullanılabilecek bir ticari lisans sunar.

### Test amaçlı geçici bir lisans nasıl alabilirim?
Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### Daha fazla örnek ve dokümantasyon nerede bulunur?
Zengin kaynaklar için [documentation](https://reference.aspose.com/page/java/) ve [Aspose.Page forum](https://forum.aspose.com/c/page/39) sayfalarını keşfedin.

### Ücretsiz deneme mevcut mu?
Evet, Aspose.Page’in ücretsiz denemesine [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**Ek Soru‑Cevap**

**S:** *“apply clipping region” aslında render pipeline’ına ne yapar?*  
**C:** Grafik motoruna tanımlı şeklin dışındaki tüm çizim komutlarını yok saymasını söyler; böylece çıktıyı maskeleyerek sadece istenen bölgeyi gösterir.

**S:** *Birden fazla kırpma şekli birleştirilebilir mi?*  
**C:** Evet—`document.clip()` metodunu birden çok kez çağırın; her çağrı mevcut kırpma bölgesiyle yeni şeklin kesişimini alır.

**S:** *Çizimden sonra kırpma şekli değiştirilebilir mi?*  
**C:** Yalnızca kaydedilmiş bir grafik durumu içinde mümkündür. Kırpmadan önce `writeGraphicsSave()` kullanın ve geri dönmek için `writeGraphicsRestore()` çağırın.

## Sonuç
**PostScript olarak kaydet**, **şekilleri nasıl kırpacağınız**, **çizgi stilini ayarlama** ve **kırpma bölgesi uygulama** konularında uzmanlaşarak Aspose.Page ile Java grafik render’ını tam kontrol edebilirsiniz. Farklı geometriler, kesik desenler ve renklerle deneyler yaparak vektör tabanlı belge oluşturmanın tam potansiyelini ortaya çıkarın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-03  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11  
**Yazar:** Aspose