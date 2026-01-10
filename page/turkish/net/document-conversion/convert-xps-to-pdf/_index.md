---
date: 2026-01-10
description: Aspose.Page ile .NET’te XPS’yi PDF’ye zahmetsizce dönüştürün. Kütüphaneyi
  indirin, belgeleri inceleyin ve ücretsiz deneme sürümünü alın.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile XPS'yi PDF'ye Dönüştür
url: /tr/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS'yi PDF'ye Dönüştür

## Giriş

Bu öğreticide Aspose.Page for .NET kütüphanesini kullanarak **XPS'yi PDF'ye nasıl dönüştüreceğinizi** öğreneceksiniz. XPS'yi PDF'ye dönüştürmek, XPS belgelerini yalnızca PDF okuyucuya sahip kullanıcılarla paylaşmanız gerektiğinde veya XPS içeriğini daha büyük PDF iş akışlarına yerleştirmek istediğinizde yaygın bir gereksinimdir. Her adımı adım adım inceleyecek, her ayarın neden önemli olduğunu açıklayacak ve çıktıyı ince ayar yapmayı—örneğin JPEG kalitesini ayarlamayı ve PDF görüntü sıkıştırmasını uygulamayı—göstereceğiz.

## Hızlı Yanıtlar
- **XPS'den PDF'ye dönüşüm için en iyi kütüphane hangisidir?** Aspose.Page for .NET
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur.
- **Görüntü kalitesini kontrol edebilir miyim?** Kesinlikle—`JpegQualityLevel` ve `PdfImageCompression` kullanın.
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Birden fazla XPS dosyasını tek bir PDF'ye dönüştürmek mümkün mü?** Evet, dosyalar üzerinde döngü yaparak ve sonuçları birleştirerek.

## Önkoşullar

Bu dönüşüm yolculuğuna başlamadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- **Aspose.Page for .NET Kütüphanesi** – Geliştirme ortamınıza Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. [Aspose.Page documentation](https://reference.aspose.com/page/net/) adresinden indirebilirsiniz.
- **Geliştirme Ortamı** – Visual Studio veya başka bir uyumlu IDE ile .NET geliştirme ortamı kurun.
- **XPS Belgesi** – PDF'ye dönüştürmek istediğiniz XPS belgesini hazırlayın. Bu, belirli bir dizinde saklanan örnek XPS dosyanız olabilir.

## Ad Alanlarını İçe Aktarın

Koda dalmadan önce, Aspose.Page for .NET işlevselliğini projemizde kullanılabilir hâle getirmek için gerekli ad alanını içe aktaralım:

```csharp
using Aspose.Page.XPS;
```

## Adım Adım Kılavuz

### Adım 1: Belge Dizinini Başlat

Kaynak XPS dosyanızın bulunduğu ve oluşturulan PDF'nin kaydedileceği klasörü tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` ifadesini XPS belgenizin bulunduğu klasörün mutlak ya da göreli yolu ile değiştirin.

### Adım 2: PDF Çıktısı ve XPS Girişi İçin Akışları Aç

İki dosya akışı kullanıyoruz—biri XPS dosyasını okumak, diğeri oluşturulan PDF'yi yazmak için.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Pro ipucu:** Yolların doğru olduğundan ve uygulamanın hedef klasörde okuma/yazma izinlerine sahip olduğundan emin olun.

### Adım 3: XPS Belgesini Yükle

`XpsDocument` örneğini XPS akışından oluşturun. `XpsLoadOptions` nesnesi yükleme tercihlerinizi belirlemenizi sağlar, ancak varsayılan çoğu senaryo için çalışır.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Adım 4: PDF Kaydetme Seçeneklerini Yapılandır

Burada PDF çıktı tercihlerini ayarlıyoruz. **PDF görüntü sıkıştırması** (`PdfImageCompression.Jpeg`) ve **JPEG kalitesi** (`JpegQualityLevel = 100`) kullanımına dikkat edin. Bu ayarlar dosya boyutunu ve görsel doğruluğu doğrudan etkiler.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – PDF'ye gömülen JPEG görüntülerinin kalitesini kontrol eder (daha yüksek = daha iyi kalite, daha büyük dosya).
- **`ImageCompression`** – Sıkıştırma algoritmasını seçer; JPEG fotoğraf görüntüleri için idealdir.
- **`TextCompression`** – Flate sıkıştırması, metin kalitesini kaybetmeden PDF boyutunu azaltır.
- **`PageNumbers`** – Yalnızca seçili sayfalar için **XPS'yi PDF olarak kaydetmenizi** sağlar.

### Adım 5: PDF Render Cihazı Oluştur

`PdfDevice`, daha önce açtığımız akışa PDF verisini yazan render hedefi olarak görev yapar.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Adım 6: Belgeyi PDF'ye Kaydet

Son olarak, render cihazını ve yapılandırılmış seçenekleri geçirerek `Save` metodunu çağırın.

```csharp
document.Save(device, options);
```

Kod çalışmasını tamamladığında, `XPStoPDF_out.pdf` belirtilen dizininizde görünecek ve tanımladığınız sıkıştırma ve kalite ayarlarıyla dönüştürülmüş sayfaları içerecektir.

## XPS'yi PDF'ye Neden Dönüştürmeliyiz?

- **Evrensel erişilebilirlik** – PDF görüntüleyicileri neredeyse tüm cihazlarda yüklüdür, XPS okuyucuları ise nadirdir.
- **Düzeni koruma** – PDF, orijinal XPS'nin tam görsel düzenini, yazı tiplerini ve grafikleri korur.
- **İleri işleme** – PDF'ye dönüştürüldükten sonra, diğer Aspose kütüphanelerini kullanarak belgeyi birleştirebilir, açıklama ekleyebilir veya dijital olarak imzalayabilirsiniz.

## Yaygın Kullanım Senaryoları

- **Kurumsal raporlama** – Eski sistemlerden XPS raporları oluşturun ve dağıtım için PDF'ye dönüştürün.
- **Arşivleme** – Belgeleri uzun vadeli koruma için PDF olarak saklayın, aynı zamanda XPS kaynaklarından oluşturabilmeye devam edin.
- **Web servisleri** – XPS yüklemelerini kabul eden ve anında PDF dosyaları döndüren bir API uç noktası sunun.

## Sorun Giderme ve İpuçları

- **Dosya bulunamadı** – `dataDir` yolunu iki kez kontrol edin ve XPS dosya adının tam olarak eşleştiğinden emin olun.
- **İzin hataları** – Visual Studio'yu Yönetici olarak çalıştırın veya çıktı klasörüne yazma izni verin.
- **Büyük PDF'ler** – Oluşan PDF çok büyükse, `JpegQualityLevel` değerini düşürün veya `ImageCompression`'ı `PdfImageCompression.Zip` olarak değiştirin.

## SSS'ler

### S1: Aspose.Page for .NET kullanarak birden fazla XPS dosyasını tek bir PDF'ye dönüştürebilir miyim?

A1: Evet, birden fazla XPS dosyası üzerinde döngü yapabilir ve aynı adımları izleyerek tek bir PDF'ye birleştirebilirsiniz.

### S2: Aspose.Page for .NET başka hangi çıktı formatlarını destekliyor?

A2: Evet, Aspose.Page for .NET TIFF, JPEG, PNG ve daha fazlası dahil olmak üzere çeşitli çıktı formatlarını destekler.

### S3: Dönüştürülen PDF belgesinin görünümünü nasıl özelleştirebilirim?

A3: İstenilen görünümü elde etmek için görüntü sıkıştırması ve metin sıkıştırması gibi seçenek nesnesi parametrelerini ayarlayabilirsiniz.

### S4: Aspose.Page for .NET için bir deneme sürümü mevcut mu?

A4: Evet, [buradan](https://releases.aspose.com/) ücretsiz bir deneme sürümü alarak Aspose.Page for .NET'in yeteneklerini keşfedebilirsiniz.

### S5: Aspose.Page for .NET için topluluk desteğini nereden alabilirim?

A5: Topluluk tartışmaları ve destek için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

## Sıkça Sorulan Sorular (AI‑Dostu)

**S: XPS'yi PDF'ye dönüştürürken JPEG kalitesini nasıl ayarlarım?**  
A: `PdfSaveOptions` içinde `JpegQualityLevel` özelliğini kullanın. 100 olarak ayarlamak en yüksek kaliteyi verir.

**S: Bu bağlamda “pdf image compression” ne anlama geliyor?**  
A: PDF içindeki görüntülerin nasıl sıkıştırılacağını belirleyen `ImageCompression` seçeneğine atıfta bulunur (ör. JPEG, Zip).

**S: XPS kaynağı olmadan programlı olarak PDF oluşturabilir miyim?**  
A: Evet, Aspose.Page doğrudan çizim komutlarından **c# generate pdf**'yi destekler, ancak bu öğreticinin kapsamı dışındadır.

**S: Vektör grafikleri kaybetmeden XPS'yi PDF'ye dönüştürmenin bir yolu var mı?**  
A: Dönüşüm vektör verilerini korur; gerektiğinde `ImageCompression`'ı JPEG veya Zip olarak tutarak görüntüleri rasterleştirmekten kaçının.

**S: Kütüphane .NET Core'u destekliyor mu?**  
A: Kesinlikle – Aspose.Page for .NET .NET Core, .NET 5, .NET 6 ve sonraki sürümlerle çalışır.

---

**Son Güncelleme:** 2026-01-10  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}