---
date: 2026-02-28
description: Aspose.Page for .NET kullanarak bir PostScript belgesine nasıl resim
  ekleyeceğinizi öğrenin. Bu kılavuz ayrıca bitmap'i PS'ye nasıl ekleyeceğinizi ve
  gerektiğinde PS'den görüntüleri nasıl çıkaracağınızı da kapsar.
linktitle: Add Image to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page ile PostScript (PS) Belgesine Görüntü Ekleme
url: /tr/net/image-management/add-image-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile PostScript (PS) Belgesine Görüntü Ekleme

## PostScript (PS) Belgesine Görüntü Ekleme

Bu öğreticide, güçlü Aspose.Page for .NET kütüphanesini kullanarak bir PostScript (PS) belgesine **görsel ekleme** yöntemini öğreneceksiniz. Yazdırılabilir broşürler, teknik çizimler veya özel raporlar hazırlıyor olun, grafiklerin doğrudan PS dosyalarına gömülmesi görsel kalitenin önemli ölçüde artmasını sağlar. Her adımı adım adım inceleyecek, her satırın neden önemli olduğunu açıklayacak ve gelecekteki projelerde yeniden kullanabileceğiniz ipuçları vereceğiz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET (latest version)
- **Bitmap'i ps'ye ekleyebilir miyim?** Yes – use `DrawImage` with a `Bitmap` object
- **Uygulama ne kadar sürer?** Typically under 10 minutes for a basic image
- **Lisans gerekiyor mu?** A trial works for evaluation; a commercial license is required for production
- **Daha sonra ps'den görüntüleri çıkarabilir miyim?** Absolutely – Aspose.Page also provides extraction APIs

## Önkoşullar

Koda başlamadan önce, aşağıdaki önkoşulların karşılandığından emin olun:

- Aspose.Page for .NET Kütüphanesi: Aspose.Page for .NET kütüphanesini [buradan](https://releases.aspose.com/page/net/) indirip kurun.
- Belge Dizini: Belgeleri ve görüntü dosyalarını saklamak için sisteminizde bir dizin oluşturun.

## Ad Alanlarını İçe Aktarma

Projeye gerekli ad alanlarını içe aktararak başlayın. Bu ad alanları, .NET uygulamanızda Aspose.Page işlevselliğini kullanmanızı sağlar:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Adım 1: Belge Dizini Oluşturma

Belgeleriniz için ayrılmış bir dizininiz olduğundan emin olun. Aşağıdaki kod parçacığındaki `"Your Document Directory"` ifadesini belge dizininizin yolu ile değiştirin.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: PS Belgesi İçin Çıktı Akışı Oluşturma

PostScript belgesi için bir çıktı akışı ayarlayın. Bu akış, değiştirilmiş belgeyi kaydetmek için kullanılacak.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## Adım 3: Kaydetme Seçeneklerini Oluşturma

PS belgesi için kaydetme seçeneklerini oluşturun, sayfa boyutu gibi istenen ayarları belirterek.

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## Adım 4: PS Belgesi Oluşturma

Yeni bir sayfalı PS belgesi başlatın ve grafik işlemlerine hazırlanın.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## Adım 5: Bitmap'i PS Belgesine Ekleme

`Bitmap` nesnesini bir görüntü dosyasından yükleyin ve dönüşümler uygulayın. Bu, **görsel ekleme** işleminin çekirdeğidir – bitmap'i PS tuvaline çizeriz.

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

> **Pro tip:** `Translate`, `Scale` ve `Rotate` değerlerini, görüntüyü tam olarak istediğiniz konuma ve boyuta getirecek şekilde ayarlayın.

## Adım 6: Grafik İşlemlerini Tamamlama

Grafik işlemlerini sonlandırın ve mevcut sayfayı kapatın.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Adım 7: Belgeyi Kaydetme

Değiştirilmiş PS belgesini kaydedin.

```csharp
document.Save();
```

## PS Belgelerinden Görüntü Çıkarma

Daha sonra grafikleri geri almanız gerekirse, Aspose.Page `PsDocument.ExtractImages` gibi çıkarma yöntemleri sunar. Bu öğretici eklemeye odaklansa da, aynı kütüphane **ps dosyalarından görüntü çıkarma** işlemini yeniden kullanım veya analiz için sağlar.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|------|
| Görüntü bozulmuş görünüyor | Yanlış ölçekleme matrisi | `Scale` değerlerini çift kontrol edin; orijinal boyut için tek tip ölçekleme kullanın (ör. `Scale(1,1)`) |
| Çıktı dosyası boş | Akış temizlenmemiş | `document.Save()` çağrısının `using` bloğu içinde yapıldığından emin olun |
| Desteklenmeyen görüntü formatı | Bitmap dosyayı yükleyemiyor | Görüntüyü JPEG, PNG, BMP veya GIF gibi desteklenen bir formata dönüştürün |

## Sonuç

Tebrikler! Aspose.Page for .NET kullanarak bir PostScript belgesine **görsel ekleme** yöntemini başarıyla öğrendiniz. Artık grafik ekleme konusunda sağlam bir temele sahipsiniz ve **ps dosyalarından görüntü çıkarma** ve **ps'ye bitmap ekleme** gerektiğinde nasıl yapacağınızı da biliyorsunuz. Birden fazla görüntü, farklı dönüşümler veya hatta özel çizim komutlarıyla zengin, yazdırılabilir içerikler oluşturmak için denemeler yapmaktan çekinmeyin.

## SSS

### Q1: Tek bir PS belgesine birden fazla görüntü ekleyebilir miyim Aspose.Page kullanarak?

A1: Evet, ekleme adımlarını belge içinde tekrarlayarak birden fazla görüntü ekleyebilirsiniz.

### Q2: Aspose.Page for .NET hangi görüntü formatlarını destekliyor?

A2: Aspose.Page for .NET JPEG, PNG, BMP ve GIF dahil çeşitli görüntü formatlarını destekler.

### Q3: Eklenebilecek görüntüler için bir boyut sınırlaması var mı?

A3: Boyut limiti, PS belgesinin özelliklerine ve sistem kaynaklarına bağlıdır. Aspose.Page geniş bir görüntü boyutu aralığını yönetir.

### Q4: Görüntülere filtreler veya bindirmeler gibi ek efektler uygulayabilir miyim?

A4: Evet, Aspose.Page görüntülere ek dönüşümler ve efektler uygulamanıza izin verir.

### Q5: PS belgesinden görüntüleri nasıl çıkarabilirim?

A5: Aspose.Page for .NET PS belgelerinden görüntü çıkarmak için yöntemler sunar. Ayrıntılı bilgi için dokümantasyona bakın.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}