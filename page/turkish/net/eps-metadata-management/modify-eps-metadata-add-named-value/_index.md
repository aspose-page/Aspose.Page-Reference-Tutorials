---
title: Aspose.Page ile Adlandırılmış Değer Ekleyin
linktitle: Adlandırılmış Değer Ekle
second_title: Aspose.Page .NET API'si
description: Aspose.Page'i kullanarak .NET'te EPS dosyalarına nasıl adlandırılmış değerler ekleyeceğinizi öğrenin. Bu kapsamlı eğitim, süreç boyunca size adım adım rehberlik eder.
type: docs
weight: 12
url: /tr/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## giriiş

.NET ile belge işleme alanında Aspose.Page, EPS dosyalarını işlemek için güçlü bir araç olarak öne çıkıyor. Aspose.Page, geliştiricilerin XMP meta verilerini değiştirmesine olanak tanır ve adlandırılmış değerlerin eklenmesi gibi görevleri kolaylaştırır. Bu eğitim size Aspose.Page'i kullanarak bir EPS dosyasına adlandırılmış değerler ekleme sürecinde adım adım rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- Temel C# programlama dili bilgisi.
- Visual Studio gibi entegre bir geliştirme ortamı (IDE) yüklü.
-  .NET kütüphanesi için Aspose.Page. Kurulu değilse adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/page/net/).

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını C# kodunuza aktaralım. Bu ad alanları Aspose.Page tarafından sağlanan işlevlere erişim için hayati öneme sahiptir:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 1. Adım: EPS Dosya Giriş Akışını Başlatın

 İlk adım, EPS dosyası için giriş akışının başlatılmasını içerir. Yer değiştirmek`"Your Document Directory"` belge dizininizin yolu ile:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 2. Adım: XMP Meta Verilerini Alın

EPS dosyasından XMP meta verilerini alın. EPS dosyasında XMP meta verileri yoksa PS meta veri yorumlarındaki değerlerle dolu yeni bir tane oluşturulur:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## 3. Adım: XMP Meta Veri Değerlerini Değiştirin

Şimdi XMP meta verilerinde değişiklik yapalım. Bu örnekte "xmpTPg:MaxPageSize" yapısına adlandırılmış bir değer ekleyeceğiz:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Adım 4: EPS Dosyasını Değiştirilmiş XMP Meta Verileriyle Kaydetme

EPS dosyasını güncellenmiş XMP meta verileriyle kaydedin. Bir çıktı akışı oluşturun ve değiştirilen EPS dosyasını kaydedin:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Çözüm

Tebrikler! .NET'te Aspose.Page'i kullanarak bir EPS dosyasına başarıyla adlandırılmış bir değer eklediniz. Bu eğitim, Aspose.Page'in belge işlemedeki basitliğini ve etkinliğini göstererek temel adımlarda size yol gösterdi.

## SSS'ler

### S1: Aspose.Page farklı EPS dosya sürümleriyle uyumlu mudur?

Cevap1: Aspose.Page çeşitli EPS dosya sürümlerini destekleyerek çok çeşitli belgelerle uyumluluk sağlar.

### S2: Aspose.Page'i ticari projeler için kullanabilir miyim?

 C2: Evet, Aspose.Page ticari bir lisansla birlikte gelir ve onu satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).

### S3: Aspose.Page'in ücretsiz deneme sürümü mevcut mu?

 Cevap3: Evet, Aspose.Page'i ücretsiz deneme sürümüyle keşfedebilirsiniz[Burada](https://releases.aspose.com/).

### S4: Nasıl destek alabilirim veya Aspose topluluğuyla nasıl bağlantı kurabilirim?

 A4: Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) destek almak ve toplulukla bağlantı kurmak için.

### S5: Geçici lisans nedir ve nasıl edinebilirim?

 Cevap 5: Test veya değerlendirme amacıyla geçici bir lisansa ihtiyacınız varsa bir lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).