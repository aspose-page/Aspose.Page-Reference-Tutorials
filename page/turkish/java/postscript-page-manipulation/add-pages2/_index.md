---
date: 2026-02-18
description: Aspose.Page kullanarak Java PostScript belgelerinde özel sayfa boyutu
  ayarlamayı ve sayfa eklemeyi öğrenin. Sorunsuz belge manipülasyonu için adım adım
  rehberimizi izleyin.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java Öğreticisi – PostScript'te Sayfa Eklerken Özel Sayfa Boyutu
  Ayarlama
url: /tr/java/postscript-page-manipulation/add-pages2/
weight: 11
---

 final markdown.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Öğreticisi – PostScript'te Sayfa Eklerken Özel Sayfa Boyutu Ayarlama

## Giriş
Modern Java uygulamalarında **özel bir sayfa boyutu** ayarlamak, fatura, bilet veya özel grafikler oluştururken sıkça gereklidir. Bu öğreticide **özel sayfa boyutu** nasıl ayarlanır, birden çok sayfa nasıl eklenir ve sonunda **tam olarak istediğiniz düzeni karşılayan bir PostScript dosyası** nasıl oluşturulur öğreneceksiniz. Kodu adım adım inceleyecek ve tekniği kendi projelerinizde hızlıca uygulayabileceksiniz.

## Hızlı Yanıtlar
- **Her sayfa için farklı sayfa boyutları ayarlayabilir miyim?** Evet, `document.openPage(width, height)` kullanarak özel boyutlu sayfalar açabilirsiniz.  
- **Üretim ortamında lisansa ihtiyacım var mı?** Değerlendirme dışı dağıtımlar için geçerli bir Aspose.Page lisansı gereklidir.  
- **Hangi Java sürümleri destekleniyor?** Kütüphane Java 8 ve üzeri sürümlerle çalışır.  
- **API iş parçacığı güvenli mi?** Document örnekleri iş parçacığı güvenli değildir; her iş parçacığı için ayrı bir `PsDocument` oluşturun.  
- **PostScript dosyası ne kadar büyük olabilir?** Aspose.Page çok megabaytlık dosyaları verimli bir şekilde işler; bellek kullanımı içerikle orantılıdır, sayfa sayısıyla değil.  
- **openPage genişlik/yükseklik aşırı yüklemesini kullanabilir miyim?** Kesinlikle—`openPage(double width, double height)` istediğiniz herhangi bir boyutu puan cinsinden belirlemenizi sağlar.  

## Ön Koşullar
Başlamadan önce şunların olduğundan emin olun:

- Java programlamaya temel bir anlayış.  
- Projenize eklenmiş Aspose.Page for Java (Maven/Gradle ya da manuel JAR).  
- Bir Java geliştirme ortamı (IDE, JDK 8+).  

## Paketleri İçe Aktarma
Başlamak için Aspose.Page kütüphanesinden gerekli sınıfları içe aktarın.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım 1: Çok Sayfalı bir PostScript Belgesi Oluşturma
İlk olarak, çok sayfalı bir dosya oluşturmak için yeni bir `PsDocument` oluşturun. Bu, çıktı akışını ayarlar ve kütüphaneye çok sayfalı bir dosyayla çalışacağımızı bildirir.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Adım 2: İlk Sayfaya İçerik Ekleme
Belge hazır olduğunda, ilk sayfaya ihtiyacınız olan içeriği ekleyebilirsiniz. İşiniz bittiğinde, sayfayı kapatarak içeriğini kilitleyin.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Özel sayfa boyutu nasıl ayarlanır
Varsayılan sayfa boyutu ihtiyacınızı karşılamıyorsa, yeni bir sayfa açarken **özel bir sayfa boyutu** belirleyebilirsiniz. Bu, fişler, etiketler veya herhangi bir standart dışı düzen için kullanışlıdır.

## Adım 3: Farklı Boyutta İkinci Sayfa Ekleme
Aşağıda ikinci bir sayfa açıyor ve özel bir genişlik ve yükseklik (puan cinsinden) sağlıyoruz. Bu, aynı belge içinde **farklı sayfa boyutları** kullanabilmenizi gösterir.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Adım 4: Belgeyi Kaydetme
Son olarak, değişiklikleri belgeyi kaydederek kalıcı hale getirin. Özel boyutlu sayfalar dahil tüm sayfalar çıktı dosyasına yazılır.

```java
// Save the document
document.save();
```

Bu adımları izleyerek, Aspose.Page kullanarak Java PostScript belgesinde sorunsuz bir şekilde sayfa ekleyebilir ve **özel sayfa boyutu** ayarlayabilirsiniz; böylece her sayfanın düzeni üzerinde tam kontrol sahibi olursunuz.

## Aspose.Page ile özel sayfa boyutu kullanmanın avantajları
- **Kesinlik:** Boyutlar puan cinsinden tanımlandığı için sayfa genişliği ve yüksekliği üzerinde tam kontrol sağlarsınız.  
- **Esneklik:** Tek bir PostScript dosyasında **farklı sayfa boyutlarını** karıştırıp eşleştirebilirsiniz.  
- **Performans:** Kütüphane içeriği doğrudan çıktı dosyasına akıtarak büyük ölçekli **PostScript dosyası oluşturma** senaryoları için uygundur.  
- **Zengin API:** Grafik çizme, resim gömme ve metin ekleme gibi işlemleri, ayarladığınız özel boyutlara saygı göstererek destekler.  

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Sayfa boyutları ters görünüyor** | `openPage(width, height)` metodunun önce genişlik, sonra yükseklik (her ikisi de puan) beklediğini unutmayın. |
| **İçerik sayfayı aşıyor** | `PsGraphics` koordinat sistemini kullanarak öğeleri özel sınırlar içinde konumlandırın veya çiziminizi ölçeklendirin. |
| **Büyük belgelerde bellek hataları** | Gösterildiği gibi doğrudan bir `FileOutputStream`e yazarak akış modunu etkinleştirin ve büyük resimleri bir kerede belleğe yüklemekten kaçının. |

## Sık Sorulan Sorular
### Tek bir PostScript belgesinde farklı boyutlarda sayfalar ekleyebilir miyim?
Evet, bu öğreticide gösterildiği gibi çok sayfalı bir PostScript belgesinde farklı boyutlarda sayfalar ekleyebilirsiniz.  

### Ekleyebileceğim sayfa sayısında bir sınırlama var mı?
Aspose.Page, belgeye teorik olarak sınırsız sayıda sayfa eklemeyi destekler.  

### Sayfalara özel içerik, örneğin resim veya grafik ekleyebilir miyim?
Kesinlikle! Aspose.Page, metin, resim ve diğer grafik öğeler dahil geniş bir içerik yelpazesini eklemenize olanak tanır.  

### Aspose.Page büyük belgeleri işleyebilir mi?
Evet, Aspose.Page hem küçük hem de büyük belgeleri sorunsuz bir şekilde yönetebilecek şekilde tasarlanmıştır.  

### Aspose.Page için ek kaynaklar ve destek nereden bulunur?
[Aspose.Page belgeleri](https://reference.aspose.com/page/java/) inceleyebilir veya topluluk desteği için [Aspose.Page forumu](https://forum.aspose.com/c/page/39) ziyaret edebilirsiniz.  

**Ek Soru‑Cevap**

**S:** *PostScript sayfasına çizim yaparken hangi resim formatları desteklenir?*  
**C:** PNG, JPEG, BMP ve GIF formatındaki resimleri çizim API'si aracılığıyla doğrudan gömebilirsiniz.  

**S:** *Belgenin varsayılan DPI değerini nasıl değiştiririm?*  
**C:** `PsDocument` oluşturmadan önce `PsSaveOptions.setResolution(int dpi)` metodunu kullanın.  

**S:** *PostScript dosyasını bir şifreyle şifreleyebilir miyim?*  
**C:** PostScript kendisi şifrelemeyi desteklemez, ancak çıktıyı bir PDF'e dönüştürüp gerekli güvenlik ayarlarını uygulayabilirsiniz.

---

**Son Güncelleme:** 2026-02-18  
**Test Edilen Versiyon:** Aspose.Page for Java 24.10  
**Yazar:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}