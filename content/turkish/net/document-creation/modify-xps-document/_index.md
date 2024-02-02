---
title: XPS Belgesini Aspose.Page for .NET ile değiştirin
linktitle: XPS Belgesini Değiştir
second_title: Aspose.Page .NET API'si
description: XPS belgelerini zahmetsizce değiştirmek için Aspose.Page for .NET'in gücünü keşfedin. Adım adım kılavuzumuzu takip edin, belge işleme sürecinizi geliştirin ve kişiselleştirilmiş imza metinleri ekleyin.
type: docs
weight: 12
url: /tr/net/document-creation/modify-xps-document/
---
## giriiş

Aspose.Page for .NET kullanarak XPS belgelerini nasıl değiştireceğinizi gösteren adım adım kılavuzumuza hoş geldiniz. Aspose.Page, geliştiricilerin XPS dosyalarıyla zahmetsizce çalışmasını sağlayan güçlü bir kütüphanedir. Bu öğreticide, bir XPS belgesindeki belirli sayfalara "Onaylandı" imza metnini ekleme sürecinde size yol göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Aspose.Page for .NET: Aspose.Page kütüphanesinin kurulu olduğundan emin olun. Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/page/net/).

-  Gerekli Dosyaları İndirin: Giriş XPS belgesi de dahil olmak üzere gerekli dosyaları şuradan indirin:[Aspose sürümler sayfası](https://releases.aspose.com/page/net/).

-  Belge Dizini: Belgeleriniz için bir dizin oluşturun ve`dir` koddaki değişkeni uygun yolla.

Artık her şeyi ayarladığınıza göre, adım adım kılavuza geçelim.

## Ad Alanlarını İçe Aktar

.NET projenizde Aspose.Page için gerekli ad alanlarını içe aktararak başlayın:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## 1. Adım: XPS Belge Akışını açın

```csharp
// ExStart:3
// Belgeler dizininin yolu.
string dir = "Your Document Directory";
// Bir XPS dosyası akışı açın
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Akıştan PS belgesi oluşturun
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Sonraki adıma devam et...
}
// ExEnd:3
```

## 2. Adım: İmza Metni Oluşturun

```csharp
// ExStart:4
// İmza metninin dolgusunu oluşturun
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Sonraki adıma devam et...
// ExBitiş:4
```

## 3. Adım: Sayfaları Tanımlayın ve İmza Ekleyin

```csharp
// ExStart:5
// İmzanın belirleneceği sayfaları tanımlayın
int[] pageNumbers = new int[] {1, 2, 3};

//Tanımlanan her sayfa için imzayı x=650 ve y=950 koordinatlarında "Onaylandı" olarak ayarlayın
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Etkin sayfayı tanımla
    document.SelectActivePage(pageNumbers[i]);

    // Glif nesnesi oluştur
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Glifler için dolguyu tanımlama
    glyphs.Fill = textFill;
}
// Sonraki adıma devam et...
// ExBitiş:5
```

## 4. Adım: Değişiklikleri XPS Belgesine Kaydetme

```csharp
// ExStart:6
// Değiştirilen XPS belgesini kaydet
document.Save(dir + "input1_out.xps");
// ExBitiş:6
```

Tebrikler! Aspose.Page for .NET'i kullanarak bir XPS belgesini başarıyla değiştirdiniz. Belge işleme sürecinizi geliştirmek için Aspose.Page tarafından sunulan ek özellikleri ve işlevleri keşfetmekten çekinmeyin.

## Çözüm

Bu eğitimde, XPS belgelerini Aspose.Page for .NET kullanarak değiştirmek için gerekli adımları ele aldık. Bu adımları izleyerek imza metinlerini belirli sayfalara sorunsuz bir şekilde entegre edebilir ve belgelerinize kişiselleştirilmiş bir dokunuş katabilirsiniz.

## SSS'ler

### S1: Aspose.Page en yeni .NET çerçeveleriyle uyumlu mu?

Cevap1: Evet, Aspose.Page en son .NET çerçevelerini desteklemek için düzenli olarak güncellenmektedir.

### S2: Eklenen metnin yazı tipini ve stilini özelleştirebilir miyim?

A2: Kesinlikle! Gereksinimlerinize göre yazı tipini, stili ve diğer nitelikleri değiştirebilirsiniz.

### S3: Aspose.Page'in işleyebileceği belge boyutunda herhangi bir sınırlama var mı?

Cevap3: Aspose.Page, farklı boyutlardaki belgeleri işlemek için tasarlanmıştır, ancak belirli ayrıntılar için her zaman belgelere göz atılması önerilir.

### S4: Aspose.Page için nasıl geçici lisans alabilirim?

 Cevap4: Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Nereden yardım alabilirim veya Aspose topluluğuyla bağlantı kurabilirim?

 A5: ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) soru sormak ve toplulukla etkileşime geçmek.