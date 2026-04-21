---
date: 2026-01-02
description: Aspose.Page kullanarak Java XPS belgelerine şeffaflık eklemeyi öğrenin.
  Çarpıcı görsel efektlerle şeffaf nesneler eklemek için adım adım rehberimizi izleyin.
linktitle: Add Transparent Object in Java XPS
second_title: Aspose.Page Java API
title: Java XPS Belgelerine Şeffaflık Nasıl Eklenir
url: /tr/java/xps-transparency/add-transparent-object/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS Belgelerine Şeffaflık Nasıl Eklenir

## Giriş
Java XPS belgelerinize **şeffaflık ekleme** ve onlara modern, katmanlı bir görünüm kazandırmak istiyorsanız, Aspose.Page for Java bu süreci oldukça basitleştirir. Bu öğreticide, ortamı kurmaktan şeffaf yollar oluşturma, opaklığı manipüle etme ve sonunda sonucu kaydetmeye kadar ihtiyacınız olan her şeyi adım adım ele alacağız. Sonuna geldiğinizde, herhangi bir XPS nesnesine güvenle şeffaflık ekleyebileceksiniz.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for Java  
- **Şeffaflığı programlı olarak kontrol edebilir miyim?** Evet, bir fırçadaki `setOpacity` yöntemiyle.  
- **Üretim için lisansa ihtiyacım var mı?** Değerlendirme dışı kullanım için ticari lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve sonrası.  
- **Çıktı standart XPS görüntüleyicileriyle uyumlu mu?** Kesinlikle—standart görüntüleyiciler şeffaflığı doğru şekilde işler.

## XPS'de şeffaflık nedir?
Şeffaflık, nesneleri farklı opaklık seviyelerinde render etmenizi sağlar ve arka plan öğelerinin görünmesine izin verir. Bu etki, filigranlar, üst üste gelen grafikler veya katmanlı görsellerin okunabilirliği artırdığı tasarımlar için faydalıdır.

## Şeffaflık eklemek için neden Aspose.Page kullanmalı?
- **Tam kontrol** geometri, fırçalar ve dönüşümler üzerinde.  
- **Harici bağımlılık yok**—her şey API içinde yönetilir.  
- **Çapraz platform** desteği, böylece aynı kod Windows, Linux ve macOS'ta çalışır.  

## Önkoşullar
İlerlemeye başlamadan önce, şunların olduğundan emin olun:

- Java geliştirme ortamı (JDK 8+).  
- Aspose.Page for Java kütüphanesi yüklü. Resmi siteden [buradan](https://releases.aspose.com/page/java/) indirebilirsiniz.  

## Paketleri İçe Aktarma
Java projenizde, şeffaf nesneler eklemeye başlamak için gerekli Aspose.Page paketlerini içe aktarın. Java dosyanızın başına aşağıdaki satırları ekleyin:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.Color;
```

Şimdi örnek kodu birden fazla adıma ayıralım.

## Adım 1: Belgeyi Başlatma
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize document
XpsDocument doc = new XpsDocument();
```
Belgenizi kurarak ve XPS belgenizin kaydedileceği dizini belirleyerek başlayın.

## Adım 2: Şeffaf Nesneler Oluşturma
```java
// Just to demonstrate transparency
doc.addPath(doc.createPathGeometry("M120,0 H400 v1000 H120")).setFill(doc.createSolidColorBrush(Color.GRAY));
doc.addPath(doc.createPathGeometry("M300,120 h600 V420 h-600")).setFill(doc.createSolidColorBrush(Color.GRAY));
```
Burada, daha sonra ekleyeceğimiz şeffaf şekiller için bir arka plan görevi görecek iki gri yol oluşturuyoruz.

## Adım 3: Dolu Yolları Ekleme
```java
// Create path with closed rectangle geometry
XpsPath path1 = doc.createPath(doc.createPathGeometry("M20,20 h200 v200 h-200 z"));
// Set blue solid brush to fill path1
path1.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add it to the current page
XpsPath path2 = doc.add(path1);
```
Bu adımda, sayfaya katı mavi bir dikdörtgen ekliyoruz. Bu dikdörtgen, daha sonra şeffaf şekillerle üst üste gelerek efekti gösterecek.

## Adım 4: Şeffaflığı Manipüle Etme
```java
// path1 and path2 are the same as long as path1 hasn't been placed inside any other element
path2.setFill(doc.createSolidColorBrush(Color.GREEN));
// Now add path2 once again. Now path2 has a parent, so path3 won't be the same as path2.
XpsPath path3 = doc.add(path2);
path3.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 0, 300));
path3.setFill(doc.createSolidColorBrush(Color.RED));
```
Burada, çoğaltılmış yolun dolgu rengini değiştiriyor ve bir çeviri dönüşümü uyguluyoruz. Bu, nesneler aynı ebeveyn öğesini paylaştığında şeffaflığın nasıl etkileşime girdiğini gösterir.

## Adım 5: Yolları Çoğaltma ve Değiştirme
```java
// Create new path4 with path2's geometry
XpsPath path4 = doc.addPath(path2.getData());
path4.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 300, 0));
path4.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add path4 once again.
XpsPath path5 = doc.add(path4);
path5.setRenderTransform(path5.getRenderTransform().deepClone());
path5.getRenderTransform().translate(0, 300);
path5.getFill().setOpacity(0.8f);
```
Mevcut bir yolu klonluyor, taşıyor ve opaklığını 0.8 ( %80 opak) olarak ayarlıyoruz. Bu adım, geometriyi yeniden kullanırken her örnek için şeffaflığı özelleştirmenin nasıl yapılabileceğini gösterir.

## Adım 6: Belgeyi Kaydetme
```java
// Save the modified document
doc.save(dataDir + "WorkingWithTransparency_out.xps");
```
Son olarak XPS dosyasını kalıcı hâle getiriyoruz. Oluşan dosyayı herhangi bir XPS görüntüleyicide açarak katmanlı şeffaflığı gözlemleyin.

## Yaygın Sorunlar ve İpuçları
- **Şeffaflık görünmüyor mu?** Opaklığı destekleyen bir fırça kullandığınızdan emin olun (ör. `createSolidColorBrush`).  
- **Dönüşüm uygulanmadı mı?** `setRenderTransform` metodunu yol belgeye eklemeden **önce** çağırdığınızı doğrulayın.  
- **Performans ipucu:** Benzer şekiller oluştururken geometri nesnelerini yeniden kullanarak bellek yükünü azaltın.

## Sıkça Sorulan Sorular
### Q: Dikdörtgenler dışında diğer şekillere şeffaflık uygulayabilir miyim?
A: Evet, sağlanan geometrileri kullanarak çeşitli şekillere şeffaflık uygulayabilirsiniz.  

### Q: Bir nesnenin şeffaflık seviyesini nasıl kontrol edebilirim?
A: Şeffaflık seviyesini kontrol etmek için dolgunun opaklık özelliğini ayarlayın.  

### Q: Aspose.Page profesyonel belge oluşturma için uygun mu?
A: Kesinlikle! Aspose.Page, profesyonel belge manipülasyonu için güçlü özellikler sunar.  

### Q: Aspose.Page'i diğer Java kütüphaneleriyle entegre edebilir miyim?
A: Evet, Aspose.Page, genişletilmiş işlevsellik için diğer Java kütüphaneleriyle sorunsuz bir şekilde entegre edilebilir.  

### Q: Aspose.Page için ek örnekler ve destek nereden bulunur?
A: Topluluk desteği için [Aspose.Page Java Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin ve belgeleri [buradan](https://reference.aspose.com/page/java/) inceleyin.  

---

**Son Güncelleme:** 2026-01-02  
**Test Edilen Sürüm:** Aspose.Page for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}