---
date: 2026-01-12
description: Aspose.Page for .NET ile XPS belgesi oluşturmayı öğrenin – yüksek kaliteli
  elektronik belgeler üretmek için adım adım bir rehber.
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile XPS Belgesi Oluşturma
url: /tr/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Belgesi Oluşturma

## Giriş

Adım adım **XPS belgesi nasıl oluşturulur** rehberimize hoş geldiniz. Bu öğreticide, elektronik belgeler için yaygın olarak kullanılan XPS dosyalarının oluşturulma sürecini inceleyeceğiz. İster deneyimli bir geliştirici olun, ister Aspose.Page ile yeni başlıyor olun, bu kılavuz XPS belgelerini sorunsuz bir şekilde oluşturmanız için net örnekler ve ayrıntılı açıklamalar sunar.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET  
- **Bunu .NET Core üzerinde çalıştırabilir miyim?** Evet, kütüphane .NET Core ve .NET 5/6'yı tam olarak destekler  
- **Kaç satır kod gerekiyor?** Temel bir XPS dosyası üretmek için 20 satırdan az  
- **Test için lisansa ihtiyacım var mı?** Ücretsiz deneme mevcuttur; üretim için lisans gereklidir  
- **Çıktı hangi formatta?** XPS (XML Paper Specification)  

## Aspose.Page for .NET kullanarak XPS belgesi oluşturma

Aşağıda kodlamaya başlamadan önce ihtiyacınız olan her şeyi bulacaksınız, ardından kısa ve numaralı bir adım‑adım rehber izlenecek.

## Önkoşullar

Öğreticiye başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1. **Aspose.Page for .NET Kütüphanesi:** Aspose.Page kütüphanesini [indirme bağlantısından](https://releases.aspose.com/page/net/) indirip kurun.  
2. **Belge Dizininiz:** Çıktı XPS dosyalarını kaydetmek istediğiniz dizini sisteminizde seçin veya oluşturun.  

Şimdi öğreticiye geçelim!

## Ad Alanlarını İçe Aktarma

Aspose.Page for .NET'i kullanabilmek için projenize gerekli ad alanlarını (namespaces) eklemeniz gerekir. Aşağıdaki adımları izleyin:

### Adım 1: Aspose.Page'e Referans Ekle

Projenizde Aspose.Page for .NET kütüphanesine bir referans ekleyin. Gerekli DLL'i indirdiğiniz pakette bulabilirsiniz.

### Adım 2: Ad Alanlarını İçe Aktar

Kod dosyanıza aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Şimdi önkoşulları kurduk ve gerekli ad alanlarını içe aktardık; XPS belgesi oluşturma sürecini birden fazla adıma ayıralım.

## Adım 1: Belge Dizinini Ayarla

```csharp
string dir = "Your Document Directory";
```

`"Your Document Directory"` ifadesini çıktıyı kaydetmek istediğiniz gerçek yol ile değiştirin.

## Adım 2: XPS Belgesi Oluştur

```csharp
XpsDocument xDocs = new XpsDocument();
```

`XpsDocument` sınıfını kullanarak yeni bir XPS belgesi başlatın.

## Adım 3: Belgeye Glyph (Metin) Ekle

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

`AddGlyphs` metodunu kullanarak belgeye glyph (metin) ekleyin. İhtiyacınıza göre yazı tipi, boyut, stil ve konumu özelleştirin.

## Adım 4: Glyph Dolgu Rengini Ayarla

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Eklenen glyph'lerin dolgu rengini belirleyin. Bu örnekte siyah renk kullanılmıştır, ancak istediğiniz herhangi bir rengi seçebilirsiniz.

## Adım 5: Sonucu Kaydet

```csharp
xDocs.Save(dir + "output.xps");
```

Son olarak, XPS belgesini belirtilen dizine istediğiniz dosya adıyla kaydedin. Oluşan XPS dosyası "Hello World!" metnini içerecektir.

Tebrikler! Aspose.Page for .NET kullanarak başarıyla bir XPS belgesi oluşturdunuz.

## Yaygın İpuçları ve Dikkat Edilmesi Gerekenler

- **Dizin Yolu** – Farklı işletim sistemlerinde eksik yol ayırıcılarından kaçınmak için `Path.Combine(dir, "output.xps")` kullanın.  
- **Yazı Tipi Mevcudiyeti** – Belirttiğiniz yazı tipi, kodun çalıştığı makinede yüklü olmalıdır; aksi takdirde Aspose varsayılan bir yazı tipi ile değiştirecektir.  
- **Birden Çok Sayfa** – Çok sayfalı XPS dosyaları oluşturmak için ek `XpsPage` nesneleri oluşturun ve kaydetmeden önce her sayfaya içerik ekleyin.

## Sonuç

Bu öğreticide, Aspose.Page for .NET kullanarak XPS belgeleri oluşturma sürecini adım adım inceledik. Bu güçlü kütüphane, elektronik belgeleri zahmetsizce üretmenizi sağlar. Farklı yazı tipleri, stiller ve içeriklerle deneyler yaparak XPS dosyalarınızı ihtiyaçlarınıza göre özelleştirin.

## SSS

### Q1: XPS belgemde özel yazı tipleri kullanabilir miyim?

A1: Evet, XPS belgenize glyph eklerken yazı tipi ailesini ve boyutunu belirtebilirsiniz.

### Q2: Aspose.Page .NET Core ile uyumlu mu?

A2: Evet, Aspose.Page .NET Core'u destekler, böylece çapraz platform uygulamalarında kullanabilirsiniz.

### Q3: Bir XPS belgesine nasıl resim ekleyebilirim?

A3: Aspose.Page, XPS belgenize resim eklemek için yöntemler sunar. Ayrıntılı örnekler için dokümantasyona bakın.

### Q4: Çok sayfalı XPS belgeleri oluşturabilir miyim?

A4: Kesinlikle! Aspose.Page kütüphanesini kullanarak bir XPS belgesine birden fazla sayfa ekleyebilirsiniz.

### Q5: Deneme sürümü mevcut mu?

A5: Evet, [ücretsiz deneme](https://releases.aspose.com/) sürümünü indirerek Aspose.Page'in özelliklerini keşfedebilirsiniz.

---

**Son Güncelleme:** 2026-01-12  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}