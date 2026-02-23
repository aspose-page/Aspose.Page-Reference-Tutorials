---
date: 2026-02-23
description: PostScript dosyalarına degrade eklemeyi, PostScript dosyasını A4 sayfa
  boyutunda kaydetmeyi ve Aspose.Page for .NET kullanarak dikdörtgeni degrade ile
  doldurmayı öğrenin.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aspose.Page .NET ile PostScript (PS) içinde Gradient – Diyagonal Gradient Nasıl
  Eklenir
url: /tr/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript (PS) Belgesine Diyagonal Gradient Nasıl Eklenir: Aspose.Page .NET

## Giriş

PostScript (PS) belgesine diyagonal bir gradient eklemek görsel çekiciliği büyük ölçüde artırabilir, özellikle teknik raporlar, broşürler veya grafik‑ağır uygulamalarda **gradient nasıl eklenir** efektlerine ihtiyaç duyduğunuzda. Bu öğreticide, bir PostScript dosyasına gradient nasıl eklenir, A4 sayfa boyutu nasıl ayarlanır ve bir dikdörtgenin içinde yumuşak bir renk geçişi nasıl doldurulur, Aspose.Page for .NET kullanarak tam olarak göreceksiniz.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for .NET  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Gradient yönünü değiştirebilir miyim?** Evet – kodda gösterildiği gibi fırça dönüşümünü döndürün  
- **Sonucu nasıl kaydederim?** `PsDocument.Save()` kullanın; bu, bir PostScript dosyasını diske yazar  
- **Üretim için lisans gerekli mi?** Evet, ticari bir lisans tam işlevselliği açar  

## PostScript'te diyagonal gradient nedir?

Diyagonal gradient, bir şekil boyunca açıyla (genellikle 45°) gerçekleşen lineer renk geçişidir. PostScript'te bu, istenen dikdörtgene uyacak şekilde gradienti döndüren, ölçeklendiren ve taşıyan özel bir dönüşüm matrisiyle `LinearGradientBrush` uygulanarak elde edilir.

## Gradient doldurmaları için Aspose.Page neden kullanılmalı?

Aspose.Page, düşük seviyeli PostScript komutlarını soyutlayarak tanıdık .NET grafik nesneleriyle çalışmanıza olanak tanır. Karmaşık doldurmalar oluşturabilir, sayfa boyutlarını ayarlayabilir ve ham PS sözdizimiyle uğraşmadan doğrudan bir **save PostScript file** dosyasına dışa aktarabilirsiniz.

## Önkoşullar

- **Aspose.Page for .NET Kütüphanesi** – [buradan](https://releases.aspose.com/page/net/) indirin.  
- **Belge Dizini** – oluşturulan `*.ps` dosyasının yazılacağı klasör.

Artık temelleri ele aldığımıza göre, uygulamayı adım adım inceleyelim.

## Ad Alanlarını İçe Aktarma

İlk olarak, EPS cihazına, çizim yardımcılarına ve I/O sınıflarına erişim sağlayan ad alanlarını içe aktarın.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Adım 1: PostScript Belgesi için Çıktı Akışı Oluşturma (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Adım 2: A4 Sayfa Boyutunu Ayarla (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Adım 3: Yeni 1‑Sayfalı PS Belgesi Oluştur

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 4: Dikdörtgen Parametrelerini Tanımla

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Adım 5: Grafik Yolu Oluştur

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Adım 6: Lineer Gradient Fırçası Oluştur (Dikdörtgen Gradientini Doldur)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Adım 7: Fırça için Dönüşüm Oluştur

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Adım 8: Fırçaya Dönüşümleri Uygula (Döndür, Ölçekle, Taşı)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Adım 9: Dönüşümü Fırçaya Ayarla

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Adım 10: Boyayı Ayarla ve Dikdörtgeni Doldur

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Adım 11: Mevcut Sayfayı Kapat

```csharp
	//Close current page
	document.ClosePage();
```

## Adım 12: Belgeyi Kaydet (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## PostScript Dosyasını Nasıl Kaydedilir

`PsDocument.Save()` çağrısı, **Adım 1**'de açtığınız akışa tam oluşturulmuş PostScript içeriğini yazar. `using` bloğu tamamlandığında, `DiagonaGradient_outPS.ps` dosyası belirttiğiniz dizinde bulunacaktır.

## Yaygın Kullanım Senaryoları

- **Teknik dokümantasyon** için hafif bir arka plan gölgelendirmesi gerekir.  
- **Pazarlama broşürleri** için diyagonal gradient modern bir görünüm katar.  
- **Otomatik rapor oluşturucular** anında yazdırılabilir PS dosyaları üretir.  

## Sorun Giderme ve İpuçları

- **Yanlış renkler** – `LinearGradientBrush`'a geçirilen ARGB değerlerini iki kez kontrol edin.  
- **Gradient görünmüyor** – dönüşüm matrisinin doğru döndürüp ölçeklediğinden emin olun; `Rotate(-45)` çağrısı diyagonal açıyı ayarlar.  
- **Dosya oluşturulmadı** – `dataDir`'in mevcut bir klasöre işaret ettiğini ve uygulamanın yazma iznine sahip olduğunu doğrulayın.  

## Sıkça Sorulan Sorular

**S: Aspose.Page tüm .NET framework'leriyle uyumlu mu?**  
C: Aspose.Page, .NET Framework 4.5+ ile .NET 6+ arasında geniş bir .NET sürüm yelpazesini destekler, bu da geniş uyumluluk sağlar.

**S: Aspose.Page'de gradient renklerini özelleştirebilir miyim?**  
C: Evet, `LinearGradientBrush` oluştururken istediğiniz ARGB renklerini belirtebilirsiniz; bu, başlangıç ve bitiş tonları üzerinde tam kontrol sağlar.

**S: Aspose.Page için bir deneme sürümü mevcut mu?**  
C: Evet, deneme sürümünü [buradan](https://releases.aspose.com/) indirerek Aspose.Page özelliklerini keşfedebilirsiniz.

**S: Aspose.Page için geçici bir lisans nasıl alabilirim?**  
C: Değerlendirme sırasında ek özellikleri açmak için Aspose.Page geçici lisansını [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Aspose.Page için topluluk desteğini nerede bulabilirim?**  
C: Yardım ve tartışmalar için Aspose.Page topluluğuna [forumda](https://forum.aspose.com/c/page/39) katılabilirsiniz.

---

**Son Güncelleme:** 2026-02-23  
**Test Edilen:** Aspose.Page for .NET (en son stabil sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}