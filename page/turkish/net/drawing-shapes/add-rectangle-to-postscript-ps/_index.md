---
date: 2026-01-18
description: Aspose.Page for .NET kullanarak PostScript belgesi .NET oluşturmayı ve
  dikdörtgenler eklemeyi öğrenin. Kod örnekleriyle adım adım rehber.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Postscript belgesi oluştur .net – Aspose.Page ile Dikdörtgen Ekle
url: /tr/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile PostScript (PS) Belgesine Dikdörtgen Ekleme

## Giriş

Postscript belge .net **oluşturmak** istiyorsanız, Aspose.Page PostScript dosyalarını işlemek için güçlü bir çözüm sunar. Bu öğreticide, Aspose.Page for .NET kullanarak bir PostScript belgesine dikdörtgen eklemeyi adım adım gösterecek ve daha zengin grafikler üretmek için sağlam bir temel sağlayacağız.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET.
- **Sıfırdan bir PostScript belgesi oluşturabilir miyim?** Evet – API, PS dosyalarını programlı olarak oluşturmanıza izin verir.
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü çalışır; üretim için lisans gereklidir.
- **Uygulama ne kadar sürer?** Temel şekiller için genellikle 10 dakikadan az.

## postscript belge .net oluşturmak nedir?
.NET içinde bir PostScript belgesi oluşturmak, Aspose.Page API’si kullanarak sayfa içeriğini—metin, grafik veya şekiller—tanımlayan bir .ps dosyasını programlı olarak üretmek anlamına gelir. Bu yaklaşım, sunucu tarafı grafik üretimi, otomatik rapor oluşturma veya çıktının formatı üzerinde hassas kontrol gerektiği her senaryo için idealdir.

## Neden Aspose.Page for .NET?
- **Grafikler üzerinde tam kontrol** – düşük seviyeli PS sözdizimiyle uğraşmadan şekiller çizin, renkleri ayarlayın ve çizgi stilleri uygulayın.
- **Çapraz platform** – Windows, Linux ve macOS çalışma ortamlarında çalışır.
- **Harici bağımlılık yok** – kütüphane tüm PS üretimini dahili olarak yönetir.
- **Zengin dokümantasyon & örnekler** – hızlı bir şekilde başlayabilirsiniz.

## Önkoşullar

- **Aspose.Page for .NET Kütüphanesi** – [buradan](https://releases.aspose.com/page/net/) indirin ve kurun.
- **Geliştirme Ortamı** – Visual Studio, VS Code veya herhangi bir .NET‑uyumlu IDE.

## Ad Alanlarını İçe Aktarma

Kodlamaya başlamadan önce gerekli sınıfları ortaya çıkaran ad alanlarını içe aktarın:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Şimdi örneği net, numaralı adımlara ayıralım.

## Adım 1: Belge Dizinini Ayarlama

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` ifadesini, oluşturulan PS dosyasının kaydedileceği klasörle değiştirin.

## Adım 2: PostScript Belgesi İçin Çıktı Akışı Oluşturma

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Bu akış **AddRectangle_outPS.ps** dosyasına işaret eder. Dosya adını veya konumunu ihtiyacınıza göre değiştirebilirsiniz.

## Adım 3: Kaydetme Seçeneklerini Ayarlama ve PS Belgesini Oluşturma

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Burada Aspose.Page’e A4 sayfa boyutu kullanmasını ve tek sayfalık bir belge oluşturmasını söylüyoruz.

## Adım 4: Dolu Bir Dikdörtgen Ekleme

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

(250, 100) konumunda, 150 genişlik ve 100 yükseklikte bir dikdörtgen tanımlıyoruz, turuncu bir fırça ayarlıyoruz ve şekli dolduruyoruz.

## Adım 5: Çerçeveli Bir Dikdörtgen Ekleme

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

İkinci dikdörtgen sayfanın daha alt kısmına oluşturuluyor; bu sefer kırmızı 3‑nokta kalınlığında bir çizgi (stroke) kullanılıyor.

## Adım 6: Sayfayı Kapatma ve Belgeyi Kaydetme

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Sayfayı kapatmak çizimi sonlandırır ve `Save()` PS dosyasını diske yazar.

## Yaygın Sorunlar & İpuçları

- **Yanlış dosya yolu** – `dataDir` sonunun bir yol ayırıcı (`\\` veya `/`) ile bittiğinden emin olun veya `Path.Combine` kullanın.
- **Lisans eksik** – Üretim ortamında belgeyi oluşturmadan önce Aspose lisansınızı uygulayın; aksi takdirde değerlendirme filigranı görünür.
- **Renk görünürlüğü** – Dikdörtgen boş görünüyor ise, fırça veya kalem renklerinin sayfa arka planıyla kontrast oluşturduğunu kontrol edin.

## Sık Sorulan Sorular

**S:** Dikdörtgenlerin renklerini özelleştirebilir miyim?  
**C:** Kesinlikle. `SolidBrush` ve `Pen` yapıcılarındaki `Color.Orange` veya `Color.Red` değerlerini istediğiniz `System.Drawing.Color` ile değiştirin.

**S:** Aspose.Page diğer belge formatlarıyla uyumlu mu?  
**C:** Evet. PostScript’in yanı sıra Aspose.Page XPS ve EPS üretimini de destekler.

**S:** Aynı belgeye metin ekleyebilir miyim?  
**C:** `TextFragment` sınıfını kullanarak istediğiniz koordinatlara metin yerleştirin, ardından `document.Draw(textFragment)` çağrısını yapın.

**S:** Ek örnekler ve tam API referansını nereden bulabilirim?  
**C:** Dokümantasyonu [buradan](https://reference.aspose.com/page/net/) inceleyin ve [Aspose.Page forumunda](https://forum.aspose.com/c/page/39) topluluğa katılın.

**S:** Aspose.Page’i satın almadan denemek mümkün mü?  
**C:** Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz. Uzun vadeli değerlendirme için bir [geçici lisans](https://purchase.aspose.com/temporary-license/) düşünebilirsiniz.

---

**Son Güncelleme:** 2026-01-18  
**Test Edilen Versiyon:** Aspose.Page 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}