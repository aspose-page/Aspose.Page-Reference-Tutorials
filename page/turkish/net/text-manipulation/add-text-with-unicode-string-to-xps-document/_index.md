---
date: 2026-03-21
description: Aspose.Page for .NET kullanarak bir XPS belgesine Unicode metin eklemeyi
  öğrenin. Bu rehber, C# ile XPS belgesi oluşturmayı ve Aspose.Page ile Unicode dizgileri
  kullanarak metin eklemeyi gösterir.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page ile XPS Belgesine Unicode Metin Nasıl Eklenir
url: /tr/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile XPS Belgesine Unicode Metin Ekleme

## Giriş

Eğer bir XPS dosyasına **unicode ekleme** karakterleri eklemeniz gerekiyorsa, doğru yerdesiniz. Bu öğreticide, Aspose.Page for .NET kullanarak **C# tarzı XPS belgesi oluşturma** adımlarını ayrıntılı olarak gösterecek ve Unicode bir dizeyle **aspose page add text** yeteneğini sergileyeceğiz. Sonunda, sağ‑dan‑sol (RTL) Unicode metni doğru şekilde görüntüleyen tam işlevsel bir XPS belgeniz olacak.

## Hızlı Yanıtlar
- **Bu öğreticide ne anlatılıyor?** Aspose.Page for .NET ile bir XPS belgesine Unicode metin ekleme.  
- **Hangi dil kullanılıyor?** C# (.NET Framework ve .NET Core ile uyumlu).  
- **Lisans gereklimi?** Geliştirme için ücretsiz deneme sürümü yeterli; üretim için ticari lisans gerekir.  
- **Yazı tipi veya boyut değiştirilebilir mi?** Evet – örnekte Arial 20 pt kullanıldı, ancak yüklü herhangi bir yazı tipi çalışır.  
- **RTL desteği var mı?** `BidiLevel = 1` ayarı, Unicode dizgileri için sağ‑dan‑sol renderlamayı etkinleştirir.

## XPS’te “unicode ekleme” nedir?

Unicode metin eklemek, bir XPS belgesine Arapça, İbranice, Çince vb. herhangi bir dilden karakterler yerleştirmek anlamına gelir. Aspose.Page’in `XpsGlyphs` sınıfı düşük seviyeli glif yerleştirmesini yönetirken, `BidiLevel` özelliği RTL betikler için metin yönünü kontrol eder.

## Metin eklemek için neden Aspose.Page kullanmalı?

- **Tam .NET entegrasyonu** – .NET Framework, .NET Core, .NET 5/6+ ile çalışır.  
- **Harici bağımlılık yok** – saf yönetilen kod, COM interop gerektirmez.  
- **Zengin tipografi desteği** – yazı tipleri, stiller, renkler ve çift yönlü metin.  
- **Yüksek performans** – XPS dosyalarını hızlı bir şekilde oluşturur ve kaydeder, sunucu tarafı üretim için idealdir.

## Önkoşullar

- C# ve .NET geliştirme konusunda temel bilgi.  
- Visual Studio (herhangi bir yeni sürüm).  
- Aspose.Page for .NET kütüphanesi – indirmek için [buraya](https://releases.aspose.com/page/net/) tıklayın.

## Ad Alanlarını İçe Aktarma

XPS modeli ve çizim yardımcılarına erişim sağlayan ad alanlarını içe aktarın.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Adım 1: Belgeyi Oluştur – create XPS document C#

Unicode metni barındıracak yeni bir XPS belgesi oluşturun.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Adım 2: Unicode Metin Ekle – aspose page add text

Şimdi gerçek Unicode dizesini ekleyelim. Bu örnekte Arial yazı tipini, 20 boyutunu kullanıyor ve metni (400 f, 200 f) konumuna yerleştiriyoruz. `BidiLevel` değeri 1, renderlayıcıya dizeyi sağ‑dan‑sol olarak işlemesini söyler.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Adım 3: Belgeyi Kaydet

Son olarak XPS dosyasını diske kaydedin.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Tebrikler! Aspose.Page for .NET kullanarak **unicode ekleme** metnini bir XPS belgesine başarıyla eklediniz.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| Metin bozuk görünüyor | Yazı tipi Unicode aralığını desteklemiyor | Gerekli glifleri içeren bir yazı tipi kullanın (ör. Arial Unicode MS). |
| RTL metin hâlâ soldan sağa | `BidiLevel` ayarlanmamış veya 0 | RTL betikler için `glyphs.BidiLevel = 1;` olduğundan emin olun. |
| Dosya kaydedilmiyor | Geçersiz `dataDir` yolu | Dizin mevcut mu ve uygulamanın yazma izni var mı kontrol edin. |

## Sık Sorulan Sorular

**S: Aspose.Page en yeni .NET framework’leriyle uyumlu mu?**  
C: Evet, Aspose.Page düzenli olarak .NET Framework, .NET Core ve .NET 5/6+ destekleyecek şekilde güncellenir.

**S: Metin eklerken yazı tipi stili ve boyutunu özelleştirebilir miyim?**  
C: Kesinlikle! `AddGlyphs` metodu, istediğiniz yazı tipi ailesi, boyutu ve `FontStyle` değerini belirtmenize olanak tanır.

**S: Aspose.Page için ek belgeler nerede bulunabilir?**  
C: Kapsamlı API detayları için belgeleri [buradan](https://reference.aspose.com/page/net/) inceleyebilirsiniz.

**S: Aspose.Page ile başlamam için ücretsiz kaynaklar var mı?**  
C: Evet, ipuçları, örnekler ve topluluk desteği için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresindeki topluluk forumunu keşfedin.

**S: Satın almadan önce deneme sürümü mevcut mu?**  
C: Tabii ki! Kütüphaneyi değerlendirmek için ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

---

**Son Güncelleme:** 2026-03-21  
**Test Edilen Sürüm:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}