---
title: Aspose.Page ile PostScript'e (PS) Doku Döşeme Deseni Uygulama
linktitle: PostScript'e (PS) Doku Döşeme Desenini Uygula
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak PostScript (PS) belgelerinizi doku döşeme desenleriyle geliştirin. Yaratıcı bir dokunuş için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## giriiş

Aspose.Page for .NET kullanarak bir PostScript (PS) belgesine doku döşeme deseninin nasıl uygulanacağını anlatan bu adım adım eğitime hoş geldiniz. Aspose.Page, çeşitli belge formatlarıyla çalışmanıza olanak tanıyan güçlü bir kütüphanedir ve bu eğitimde, doku döşeme desenleri ekleyerek PS belgelerinizi nasıl geliştirebileceğinizi keşfedeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- [Görsel stüdyo](https://visualstudio.microsoft.com/) makinenize kurulu.
- Temel C# programlama bilgisi.
-  İndirip yükleyin[.NET kütüphanesi için Aspose.Page](https://releases.aspose.com/page/net/).
- Doku deseni için bir görüntü dosyası (örneğin, "TestTexture.bmp").

## Ad Alanlarını İçe Aktar

C# kodunuzda gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Süreç boyunca size rehberlik etmesi için verilen örneği birden fazla adıma ayıralım.

## 1. Adım: Belge Dizinini Ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
```

"Belge Dizininiz"i, PS belgenizi kaydetmek istediğiniz yolla değiştirdiğinizden emin olun.

## 2. Adım: PS Belgesi için Çıktı Akışı Oluşturun

```csharp
// PostScript belgesi için çıktı akışı oluşturun
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // A4 boyutunda kaydetme seçenekleri oluşturun
    PsSaveOptions options = new PsSaveOptions();

    // Yeni 1 sayfalık PS Belgesi oluştur
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Bu adım, belge boyutunun tanımlanması da dahil olmak üzere PS belgesinin çıktı akışını ayarlar.

## Adım 3: Doku Döşeme Desenini Uygulayın

```csharp
// Görüntü dosyasından bir Bitmap nesnesi oluşturun
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Görüntüden doku fırçası oluşturun
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Desene X yönünde ölçeklendirme ekleyin
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Bu doku fırçasını geçerli boya olarak ayarla
    document.SetPaint(brush);
}
```

Bu adım, bir görüntüden doku fırçası oluşturmayı ve bunu belgenin geçerli boyası olarak ayarlamayı içerir.

## Adım 4: Dikdörtgen Yol Oluşturun ve Doldurun

```csharp
// Dikdörtgen yol oluştur
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Dikdörtgeni doldur
document.Fill(path);
```

Burada dikdörtgen bir yol tanımlayıp önceden ayarladığımız doku fırçasıyla dolduruyoruz.

## Adım 5: Kontur ve Çizimi Ayarlayın

```csharp
// Mevcut boyayı al
Brush paint = document.GetPaint();

// Kırmızı konturu ayarla
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Dikdörtgeni konturla
document.Draw(path);
```

Bu adım, kontur özelliklerinin ayarlanmasını ve ana hatları çizilen dikdörtgenin çizilmesini içerir.

## Adım 6: Metni Doku Deseniyle Doldurun ve Ana Hatlarını Belirleyin

```csharp
// Metni doku deseniyle doldurma
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Doku desenli anahat metni
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Son olarak metni doku deseniyle doldurup ana hatlarını çizerek belgenizin görsel çekiciliğini artırıyoruz.

## Adım 7: Belgeyi Kaydedin ve Kapatın

```csharp
// Geçerli sayfayı kapat
document.ClosePage();

// Belgeyi kaydet
document.Save();
```

Değişikliklerin uygulanması için geçerli sayfayı kapattığınızdan ve belgeyi kaydettiğinizden emin olun.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak PostScript belgesine doku döşeme desenini nasıl uygulayacağınızı başarıyla öğrendiniz. PS belgelerinizi daha da özelleştirmek için farklı görüntüler ve desenlerle denemeler yapın.

## SSS'ler

### S1: Doku deseni için başka görüntü formatlarını kullanabilir miyim?

Cevap1: Evet, Aspose.Page çeşitli görüntü formatlarını destekler. Kütüphane belgeleriyle uyumluluğu sağlayın.

### S2: Aspose.Page .NET Core ile uyumlu mu?

C2: Evet, Aspose.Page hem .NET Framework hem de .NET Core ile uyumludur.

### S3: Dokulu dikdörtgenin boyutunu nasıl ayarlayabilirim?

 Cevap 3: Boyutları değiştirin`RectangleF` yol oluşturma sırasında parametreler.

### S4: Tek bir belgeye birden fazla doku deseni ekleyebilir miyim?

Cevap4: Evet, işlemi farklı görseller ve yollarla tekrarlayabilirsiniz.

### S5: Ek kaynakları ve desteği nerede bulabilirim?

 A5: ziyaret edin[Aspose.Page Forumu](https://forum.aspose.com/c/page/39) topluluk desteği için ve keşfetmek için[dokümantasyon](https://reference.aspose.com/page/net/).
