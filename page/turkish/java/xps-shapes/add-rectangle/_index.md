---
date: 2026-04-24
description: Aspose.Page kullanarak Java XPS'te dikdörtgen rengini ayarlamayı ve dikdörtgen
  eklemeyi öğrenin. Bu kılavuz, Java’da dikdörtgen ekleme ve dikdörtgen çizgi kalınlığını
  değiştirmeyi kapsar.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Java XPS'te Dikdörtgen Ekle
second_title: Aspose.Page Java API
title: Java XPS'te Dikdörtgen Rengini Ayarla ve Dikdörtgen Ekle
url: /tr/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'de Dikdörtgen Rengini Ayarlama ve Dikdörtgen Ekleme

## Giriş
Bu rehberde, Aspose.Page kütüphanesini kullanarak Java XPS'de **set rectangle color** ve **add a rectangle** işlemlerini nasıl yapacağınızı öğreneceksiniz. Rapor için basit şekiller çizin ya da karmaşık vektör grafikleri oluşturun, dikdörtgen stilini ustalaşmak XPS belgeleriniz üzerinde hassas kontrol sağlar.  

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for Java  
- **Dikdörtgen çizgisini değiştirebilir miyim?** Evet, `setStroke` ve `setStrokeThickness` kullanarak  
- **CMYK renk profili destekleniyor mu?** Kesinlikle – gösterildiği gibi ICC profilleri yükleyebilirsiniz  
- **Üretim için lisansa ihtiyacım var mı?** Evet, değerlendirme dışı kullanım için ticari lisans gereklidir  
- **Uygulama ne kadar sürer?** Temel bir dikdörtgen için genellikle 10 dakikadan az  

## **set rectangle color** nedir?
Bir dikdörtgenin rengini ayarlamak, şeklin son XPS belgesinde render edileceği dolgu veya çizgi rengini tanımlamak anlamına gelir. Aspose.Page ile tam renk eşleşmesi sağlamak için RGB, CMYK veya hatta özel ICC renk profillerini kullanabilirsiniz.

## Aspose.Page'i **add rectangle java** ve **change rectangle stroke** için neden kullanmalısınız?
- **Tam özellikli API** – hem katı renkleri hem de degrade renkleri destekler.  
- **Çapraz platform** – yerel bağımlılıklar olmadan herhangi bir Java çalışma zamanında çalışır.  
- **Zengin geometri desteği** – karmaşık yollar oluşturun, dönüşümler uygulayın ve çizgi kalınlığını kolayca yönetin.  

## Önkoşullar
Koda geçmeden önce, şunların olduğundan emin olun:

- Java programlama temelleri.  
- Aspose.Page kütüphanesi yüklü. Değilse, [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) adresinden indirin.  
- Çalışan bir Java geliştirme ortamı (IDE, JDK vb.).  

## Paketleri İçe Aktarma
Başlamak için gerekli paketleri Java projenize içe aktarın. Aspose.Page kütüphanesinin sınıf yolunuza doğru eklendiğinden emin olun. İşte temel bir örnek:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Şimdi, sağlanan örneği birden fazla adıma ayırarak Java XPS'de **add a rectangle** ve **set its color** işlemlerini gerçekleştirelim.

## Adım 1: Belge Dizinini Ayarlama
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
`"Your Document Directory"` ifadesini XPS dosyalarını okuma/yazma istediğiniz mutlak yol ile değiştirin.

## Adım 2: Yeni XPS Belgesi Oluşturma
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Bu satır, şekillerimizi tutacak yeni bir XPS belgesi başlatır.

## Adım 3: CMYK Katı Renkli Çizgili Dikdörtgen Ekleme
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Bu adım, CMYK katı rengiyle bir **stroked rectangle** ekler. `setStroke` yöntemi dikdörtgenin dış çizgi rengini tanımlar, `setStrokeThickness` ise çizgi kalınlığını kontrol eder—**changing rectangle stroke** için mükemmeldir.

### İpucu:
RGB rengi tercih ederseniz, `createColor` çağrısını `doc.createColor(0, 0, 255)` ile değiştirerek katı mavi dolgu elde edebilirsiniz.

## Adım 4: Oluşturulan XPS Belgesini Kaydetme
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Son olarak, XPS belgesini diske kaydedin. `AddRectangle_out.xps` dosyası artık tanımladığınız renk ve çizgiye sahip bir dikdörtgen içeriyor.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|----------|
| **Dikdörtgen görünmüyor** | Yanlış yol geometrisi veya çizgi kalınlığı 0 olarak ayarlandı | Yol dizesini (`"M 20,10 L 220,10 220,100 20,100 Z"`) doğrulayın ve `setStrokeThickness` değerinin 0'dan büyük olduğundan emin olun. |
| **Yanlış renk** | İstenen renk uzayıyla eşleşmeyen bir ICC profili kullanmak | `doc.createColor(r, g, b)` ile RGB kullanın veya ICC dosya yolunu tekrar kontrol edin. |
| **Dosya kaydedilmedi** | `dataDir` mevcut olmayan bir klasöre işaret ediyor veya yazma izni yok | Klasörü önceden oluşturun veya yazılabilir bir konum seçin. |

## Sıkça Sorulan Sorular

**S:** *Tek bir XPS belgesine birden fazla dikdörtgen ekleyebilir miyim?*  
**C:** Evet. İhtiyacınız olan her dikdörtgen için geometri oluşturma ve stil adımlarını tekrarlayın.

**S:** *Dikdörtgenin çizgi rengi yerine dolgu rengini nasıl değiştirebilirim?*  
**C:** `path.setFill(...)` metodunu, `setStroke` gibi bir katı renk fırçası ile kullanın.

**S:** *Aspose.Page karmaşık XPS belge manipülasyonları için uygun mu?*  
**C:** Kesinlikle. Kütüphane degrade renkler, dönüşümler ve gömülü yazı tipleri gibi gelişmiş özellikleri destekler.

**S:** *Ek örnekler ve topluluk desteği nerede bulunabilir?*  
**C:** Daha fazla kod örneği ve topluluk yardımı için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresini inceleyin.

**S:** *Satın almadan önce Aspose.Page'i deneyebilir miyim?*  
**C:** Evet, API yeteneklerini değerlendirmek için bir [free trial](https://releases.aspose.com/) keşfedebilirsiniz.

---

**Son Güncelleme:** 2026-04-24  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12  
**Yazar:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}