---
date: 2026-01-15
description: Aspose.Page for .NET kullanarak XPS belgelerini nasıl birleştireceğinizi
  öğrenin – sorunsuz belge birleştirme için adım adım rehber.
linktitle: Merge XPS Documents
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile XPS Belgelerini Birleştirme
url: /tr/net/document-merging/merge-xps-documents/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Belgelerini Aspose.Page for .NET ile Birleştirme

## Giriş

Programlı olarak XPS dosyalarını **nasıl birleştireceğinizi** bulmak için güvenilir bir yol mu arıyorsunuz? Bu öğreticide, Aspose.Page for .NET kullanarak XPS belgelerini birleştirmenin tam adımlarını size göstereceğiz. Raporları, faturaları veya diğer XPS tabanlı varlıkları birleştirmeniz gerekse, süreç basit ve tamamen otomatik. Hadi başlayalım ve sadece birkaç C# satırıyla temiz, birleştirilmiş bir XPS çıktısı elde edebileceğinizi görelim.

## Hızlı Yanıtlar
- **XPS birleştirmeyi hangi kütüphane yönetir?** Aspose.Page for .NET  
- **Uygulama ne kadar sürer?** Genellikle 10 dakikadan az  
- **Lisans gerekli mi?** Üretim kullanımı için bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Şifreli XPS dosyalarını birleştirebilir miyim?** Evet – Aspose.Page şifreli belgeleri işleyebilir  

## XPS Belge Birleştirme Nedir?

XPS (XML Paper Specification), Microsoft tarafından oluşturulan sabit düzenli bir belge formatıdır. XPS dosyalarını birleştirmek, birden fazla XPS belgesini orijinal düzeni, yazı tiplerini ve grafikleri koruyarak tek, sürekli bir dosyada birleştirmek anlamına gelir.

## Neden Aspose.Page for .NET Kullanmalı?

- **Tam kontrol** birleştirme süreci üzerinde, Microsoft XPS Viewer gerektirmeden  
- **Harici bağımlılık yok** – her şey .NET uygulamanız içinde çalışır  
- **Yüksek performans** – büyük belgelerde bile verimli çalışır  
- **Çapraz platform** – .NET Framework, .NET Core ve .NET 5+ ile uyumludur  

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# ve .NET ekosistemi hakkında temel bir anlayış.  
- **Aspose.Page for .NET** yüklü – bunu [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.  
- Birleştirmek istediğiniz bir veya daha fazla XPS dosyası.

## Ad Alanlarını İçe Aktarma

C# projenizde, XPS API'sine erişim sağlayan ad alanını içe aktarın:

```csharp
using Aspose.Page.XPS;
```

## Adım 1: Projenizi Kurun

Visual Studio, Rider veya tercih ettiğiniz IDE'de yeni bir C# konsol veya sınıf kütüphanesi projesi oluşturun. Aspose.Page DLL'ine bir referans ekleyin (veya `Aspose.Page` NuGet paketini kurun). Bu, daha sonra kullanılacak `XpsDocument` sınıfına erişmenizi sağlar.

## Adım 2: Akışları Başlatın

Kaynak XPS dosyalarını giriş akışı olarak açın ve birleştirilmiş belge için bir çıkış akışı oluşturun. `using` ifadeleri, işlem tamamlandıktan sonra tüm akışların doğru şekilde kapatılmasını sağlar.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Initialize XPS output stream
using (System.IO.Stream outStream = System.IO.File.Open(dataDir + "mergedXPSfiles.xps", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream inStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

## Adım 3: XPS Belgesini Yükleyin

`XpsDocument` örneğini birincil giriş akışından oluşturun. `XpsLoadOptions` nesnesi, gerekirse yükleme davranışını özelleştirmenize olanak tanır.

```csharp
XpsDocument document = new XpsDocument(inStream, new XpsLoadOptions());
```

## Adım 4: XPS Dosyalarının Bir Dizisini Oluşturun

Birleştirmek istediğiniz her XPS dosyasını listeleyen bir string dizisi hazırlayın. Dizinin sırası, son belgede dosyaların sırasını belirler.

```csharp
string[] filesToMerge = new string[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

## Adım 5: XPS Dosyalarını Birleştirin

`Merge` metodunu, dosya yolu dizisini ve çıkış akışını parametre olarak vererek çağırın. Aspose.Page tüm ağır işi halleder — sayfaları birleştirir, kaynakları korur ve son XPS dosyasını yazar.

```csharp
document.Merge(filesToMerge, outStream);
```

## Yaygın Sorunlar ve İpuçları

- **Dosya bulunamadı** – `filesToMerge` içindeki yolları iki kez kontrol edin. `Path.Combine` kullanmak, yol ayırıcı hatalarını önlemeye yardımcı olabilir.  
- **Bellek kullanımı** – Çok sayıda dosya birleştirirken, bellek tüketimini düşük tutmak için dosyaları partiler halinde işlemeyi düşünün.  
- **Şifreli belgeler** – Kaynak XPS dosyalarından biri şifre korumalıysa, birleştirmeden önce uygun kimlik bilgileriyle yükleyin.

## Sıkça Sorulan Sorular

**S1: Farklı sayfa boyutlarına sahip XPS dosyalarını birleştirebilir miyim?**  
C: Evet. Aspose.Page birleştirme sırasında sayfa boyutlarını otomatik olarak normalleştirir.

**S2: Kaç XPS dosyasını birleştirebileceğim konusunda bir sınırlama var mı?**  
C: Katı bir sınır yok, ancak çok büyük koleksiyonlar performansı etkileyebilir; bellek kullanımını izleyin.

**S3: Şifreli XPS belgelerini birleştirmek için özel bir lisansa ihtiyacım var mı?**  
C: Şifreli belge işleme dahil olmak üzere üretim seviyesindeki herhangi bir özellik için tam bir Aspose.Page lisansı gereklidir.

**S4: Birleştirmeden sonra her sayfaya özel bir alt bilgi eklemek nasıl yapılır?**  
C: Birleştirme sonrası, oluşan XPS'i `XpsDocument` ile yeniden açabilir ve çizim API'sini kullanarak alt bilgiler ekleyebilirsiniz.

**S5: Aspose.Page .NET Core'u destekliyor mu?**  
C: Kesinlikle. Kütüphane .NET Core 3.1 ve sonrası, ayrıca .NET 5/6/7 ile uyumludur.

## Sonuç

Artık **XPS belgelerini nasıl birleştireceğinizi** verimli bir şekilde Aspose.Page for .NET kullanarak öğrendiniz. Yukarıdaki adımları izleyerek, herhangi bir .NET uygulamasında belge konsolidasyonunu otomatikleştirebilir, zaman kazanabilir ve manuel çabayı azaltabilirsiniz. API'yi daha fazla keşfederek filigran ekleyebilir, son dosyayı şifreleyebilir veya bireysel sayfaları gerektiği gibi manipüle edebilirsiniz.

---

**Son Güncelleme:** 2026-01-15  
**Test Edilen:** Aspose.Page for .NET (latest version)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}