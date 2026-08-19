---
date: 2026-03-03
description: Aspose.Page for .NET'i XPS belgelerinde resimleri döşemek için nasıl
  kullanacağınızı öğrenin. Bu adım adım rehber, resmi verimli bir şekilde döşemeyi
  ve görsel çekiciliği artırmayı gösterir.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page'i Kullanarak XPS Belgesine Döşeli Görüntü Ekleme
url: /tr/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile XPS Belgesine Döşeli Görüntü Ekleme

## Giriş

Aspose kullanarak XPS dosyalarınıza daha zengin bir görsel stil kazandırmanın **nasıl yapılacağını** merak ediyorsanız, doğru yerdesiniz. Bu öğreticide, Aspose.Page for .NET ile bir XPS belgesi içinde **görüntüyü döşeme** (tile) adımlarını adım adım inceleyeceğiz. Sonunda, herhangi bir .NET projesine ekleyebileceğiniz, anında döşeli‑görüntü grafikleri oluşturacak yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET  
- **Döşeli fırçayı hangi yöntem oluşturur?** `CreateImageBrush` ve `TileMode = XpsTileMode.Tile`  
- **Şeffaflığı kontrol edebilir miyim?** Evet – `path.Fill.Opacity` değerini ayarlayın (ör. 0.5f)  
- **Test için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Aspose.Page Nedir ve Neden Görüntü Döşenir?

Aspose.Page, geliştiricilerin Microsoft Office’e bağımlı olmadan XPS, PDF ve diğer sayfa‑tabanlı formatları oluşturup düzenlemesini ve render etmesini sağlayan güçlü bir API’dir. Bir görüntüyü döşemek—bitmap’i bir şekil üzerinde tekrar etmek—büyük alanları desen, filigran veya arka plan dokusuyla doldurmanıza olanak tanır ve dosya boyutunu düşük tutar.

## Aspose.Page ile XPS Belgelerinde Görüntü Döşeme Nasıl Yapılır?

Aşağıda, tamamen çalıştırılabilir bir örnek bulacaksınız. Her adım, ilgili kod bloğundan önce sade bir dille açıklanmıştır; böylece **neden** her satırın önemli olduğunu görebilirsiniz.

### Önkoşullar

- **Aspose.Page for .NET** – resmi siteden kütüphaneyi indirin ve [burada](https://reference.aspose.com/page/net/) referans olarak ekleyin.  
- **Geliştirme ortamı** – Visual Studio (herhangi bir sürüm) veya tercih ettiğiniz başka bir .NET IDE.

### Ad Alanlarını İçe Aktarma

İlk olarak, XPS sınıflarının nerede bulunduğunu derleyicinin bilmesi için gerekli ad alanlarını projemize ekleyelim.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Adım 1: Belge Dizinini Tanımlama

Oluşturulacak XPS dosyasının ve kaynak görüntünün nerede saklanacağını belirtin. Yer tutucuyu makinenizdeki gerçek bir klasörle değiştirin.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Adım 2: Yeni bir XPS Belgesi Oluşturma

Döşeli grafiği tutacak boş bir XPS belgesi örnekleyin.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Adım 3: Döşeli Görüntü Ekleme

Burada bir dikdörtgen yol oluşturup, onu bir `ImageBrush` ile dolduruyor ve fırçayı döşeli moda ayarlıyoruz. `TileMode` özelliği motorun görüntüyü hem yatay hem de dikey olarak tekrarlamasını sağlar. Dikdörtgen koordinatlarını veya kaynak görüntüyü senaryonuza göre ayarlayın.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Adım 4: Sonuç XPS Belgesini Kaydetme

Son olarak belgeyi diske yazın. Çıktı dosyası herhangi bir XPS görüntüleyiciyle açılabilir veya Aspose.Page ile daha da işlenebilir.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Yaygın Sorunlar ve İpuçları

- **Yol hataları** – `dataDir` sonundaki eğik çizgiyi unutmayın veya `Path.Combine` kullanarak eksik ayırıcı sorunlarını önleyin.  
- **Görüntü boyutu uyumsuzlukları** – Kaynak görüntü, döşeme alanı için yeterince büyük olmalı; aksi takdirde desen uzatılmış görünebilir.  
- **Şeffaflık görünmüyor** – Bazı görüntüleyiciler XPS’te şeffaflığı yoksayar; tam XPS render desteği sunan bir görüntüleyici (ör. Windows XPS Viewer) ile test edin.

## Sık Sorulan Sorular

### S1: Aspose.Page tüm .NET geliştirme ortamlarıyla uyumlu mu?
C: Evet, Aspose.Page Visual Studio, Rider, VS Code ve .NET’i destekleyen herhangi bir IDE ile çalışır.

### S2: Döşeli görüntünün şeffaflığını ayarlayabilir miyim?
C: Kesinlikle. Örnekte `path.Fill.Opacity = 0.5f;` kullanılmıştır—değeri 0 (tamamen şeffaf) ile 1 (tamamen opak) arasında istediğiniz gibi değiştirebilirsiniz.

### S3: Aspose.Page for .NET’te başka döşeme modları var mı?
C: Evet. `XpsTileMode.Tile` dışında `FlipX`, `FlipY` ve `FlipXY` modlarını kullanarak yansıtılmış desenler oluşturabilirsiniz.

### S4: Aspose.Page için geçici lisansları nasıl yönetirim?
C: Detaylar ve deneme lisansı almak için Aspose sitesindeki [geçici lisans](https://purchase.aspose.com/temporary-license/) sayfasına bakın.

### S5: Yardım almak ya da Aspose.Page topluluğuyla iletişime geçmek için nereden ulaşabilirim?
C: Sorularınızı sorabilir, kod parçacıkları paylaşabilir ve diğer geliştiricilerden öğrenebilirsiniz; bunun için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

### S6: Bu yöntemi filigran efekti oluşturmak için kullanabilir miyim?
C: Evet. Opaklığı düşürüp yarı‑şeffaf bir görüntü seçerek, döşeli fırça tekrar eden bir filigran olarak mükemmel çalışır.

## Sonuç

Artık **Aspose** kullanarak bir XPS belgesine döşeli bir görüntü eklemenin, şeffaflığını kontrol etmenin ve sonucu kaydetmenin yollarını biliyorsunuz. Bu teknik, arka plan desenleri, filigranlar veya dosya boyutunu artırmadan tekrarlayan grafiklerin gerektiği her senaryo için idealdir. Farklı şekiller, görüntüler ve döşeme modlarıyla deneyler yaparak projenizin ihtiyaçlarına en uygun çözümü bulabilirsiniz.

---

**Son Güncelleme:** 2026-03-03  
**Test Edilen Versiyon:** Aspose.Page for .NET (en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}