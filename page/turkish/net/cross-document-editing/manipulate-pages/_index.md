---
date: 2026-01-10
description: Aspose.Page for .NET ile XPS belgelerini nasıl birleştireceğinizi öğrenin.
  Bu adım adım kılavuz, verimli sonuçlar için sayfa manipülasyonu tekniklerini gösterir.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile XPS Belgelerini Birleştirin
url: /tr/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Belgelerini Aspose.Page for .NET ile Birleştirme

## Giriş

Bu öğreticide **XPS belgelerini birleştirme** ve .NET ortamında Aspose.Page kütüphanesini kullanarak sayfalarını nasıl manipüle edeceğinizi keşfedeceksiniz. Birden fazla raporu tek bir XPS dosyasında birleştirmeniz ya da şık bir çıktı için sayfaları yeniden düzenlemeniz gerekse, bu rehber adım adım süreci, net açıklamalar ve çalıştırmaya hazır kodlarla size gösterir.

## Hızlı Yanıtlar
- **Aspose.Page ile ne yapabilirim?** XPS belgelerini birleştirme, sayfa ekleme, ekleme veya kaldırma ve sonucu kaydetme.  
- **Test için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans mevcuttur.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Visual Studio gerekli mi?** Hayır, C# destekleyen herhangi bir IDE çalışır, ancak Visual Studio önerilir.  
- **Birleştirme ne kadar sürer?** Standart‑boyutlu XPS dosyaları için genellikle birkaç saniye.

## XPS Belgelerini Birleştirme Nedir?

XPS belgelerini birleştirmek, iki veya daha fazla mevcut XPS dosyasından sayfaları alıp tek bir XPS belgesinde birleştirmek anlamına gelir. Bu, birleştirilmiş raporlar oluşturmak, çok sayfalı kılavuzları derlemek veya başka bir formata dönüştürmeden baskıya hazır paketler hazırlamak için faydalıdır.

## Neden .NET için Aspose.Page Kullanmalı?

Aspose.Page, XPS dosyalarıyla doğrudan çalışan **saf .NET API** sunar—harici araçlara veya üçüncü‑taraf bileşenlere ihtiyaç yoktur. Sayfa sırası, ekleme noktaları ve içerik korunumu üzerinde ince kontrol sağlar, böylece birleştirme sürecini güvenilir ve hızlı kılar.

## Önkoşullar

- **Aspose.Page for .NET** – [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) adresinden indirin.  
- **Development Environment** – Visual Studio, Rider veya C# destekleyen herhangi bir IDE.  
- **Input XPS Files** – bilinen bir klasöre yerleştirilmiş üç örnek dosya (`input1.xps`, `input2.xps`, `input3.xps`).

## Ad Alanlarını İçe Aktarma

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Bu ad alanları, temel XPS belge sınıflarına, sayfa modellerine ve temel çizim yardımcı programlarına erişim sağlar.

## Adım 1: Belge Dizinini Ayarlama

```csharp
string dataDir = "Your Document Directory";
```

**Your Document Directory** ifadesini XPS dosyalarınızın bulunduğu tam yol ile değiştirin, ör. `C:\\Docs\\XpsFiles\\`.

## Adım 2: XPS Belge Örneklerini Oluşturma

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` ve `doc3` birleştirmek istediğiniz kaynak belgeleri temsil eder.  
- `doc4` birleştirilmiş sonucu tutacak boş bir XPS belgesidir.

## Adım 3: Sayfaları Ekleme, Eklememe ve Kaldırma

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Her satırın yaptığı işlev şu şekildedir:

1. **InsertPage(1, doc2.Page, false)** – `doc2`'nin ilk sayfasını `doc4` içinde 1. konuma yerleştirir.  
2. **AddPage(doc3.Page, false)** – `doc3`'ün ilk sayfasını `doc4`'ün sonuna ekler.  
3. **RemovePageAt(2)** – şu anda 2. indekste bulunan sayfayı kaldırır (istenmeyen sayfaları silmek için faydalıdır).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – `doc1`'in üçüncü sayfasını 2. konuma ekler, birleştirmeyi tamamlar.

Bu işlemler, gerektiğinde sayfaları yeniden sıralayarak veya atarak **XPS belgelerini birleştirebileceğinizi** gösterir.

## Adım 4: Birleştirilmiş Belgeyi Kaydetme

```csharp
doc4.Save(dataDir + "out.xps");
```

Son birleştirilmiş XPS dosyası (`out.xps`) aynı dizine yazılır. Artık herhangi bir XPS görüntüleyicide açabilir veya Aspose.Page ile daha fazla işleyebilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **File not found** – `dataDir` yolunu iki kez kontrol edin ve giriş dosyalarının mevcut olduğundan emin olun.  
- **Invalid page index** – sayfa indeksleri 1‑tabanlıdır; var olmayan bir sayfayı eklemeye çalışmak istisna fırlatır.  
- **License errors** – üretime dağıtmadan önce geçici veya tam lisans kullanın.

## SSS'ler

### Q1: Farklı XPS belgelerinden sayfaları manipüle edebilir miyim?
A1: Evet, öğreticide gösterildiği gibi, birden fazla XPS belgesinden sayfaları yeni bir belgeye ekleyebilirsiniz.

### Q2: Belgeden belirli bir sayfayı nasıl kaldırabilirim?
A2: Kaldırmak istediğiniz sayfanın indeksini belirterek `RemovePageAt` metodunu kullanın.

### Q3: Aspose.Page Visual Studio ile uyumlu mu?
A3: Evet, Aspose.Page Visual Studio ile tamamen uyumludur, .NET projelerinize entegre etmeyi kolaylaştırır.

### Q4: Kullanılabilir lisans seçenekleri var mı?
A4: Evet, lisans seçeneklerini inceleyebilir ve geçici bir lisans alabilirsiniz [buradan](https://purchase.aspose.com/temporary-license/).

### Q5: Destek alabileceğim veya soru sorabileceğim yer neresi?
A5: Destek almak ve toplulukla etkileşimde bulunmak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

## Sık Sorulan Sorular

**S: Üçten fazla XPS dosyasını birleştirebilir miyim?**  
C: Kesinlikle. Ek `XpsDocument` örnekleri oluşturup `InsertPage` veya `AddPage` metodlarını tekrarlayarak daha büyük bir birleştirilmiş belge oluşturabilirsiniz.

**S: Birleştirme orijinal biçimlendirme ve grafikleri korur mu?**  
C: Evet. Aspose.Page sayfa içeriğini bayt‑bayt kopyalar, böylece metin, resimler ve vektör grafikleri değişmeden kalır.

**S: Bir sayfayı indeks belirtmeden sona nasıl eklerim?**  
C: `AddPage(sourcePage, false)` kullanın; bu, sayfayı belgenin sonuna ekler.

**S: UI olmadan bir sunucuda XPS belgelerini birleştirmek mümkün mü?**  
C: API tamamen başsızdır; aynı kodu ASP.NET, Azure Functions veya herhangi bir sunucu‑tarafı .NET ortamında çalıştırabilirsiniz.

**S: XPS dosyalarım şifre korumalı olursa ne olur?**  
C: Aspose.Page şu anda şifreli XPS dosyalarını desteklememektedir; birleştirmeden önce dosyaları çözmeniz gerekir.

---

**Son Güncelleme:** 2026-01-10  
**Test Edildi:** Aspose.Page for .NET 24.10  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}