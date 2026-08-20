---
date: 2026-03-19
description: Aspose.Page for .NET ile özel baskı biletleri oluşturarak bilet eklemeyi
  öğrenin. Baskı deneyiminizi ince ayarlı kontrol ile özelleştirin.
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 'Bilet Nasıl Eklenir: Aspose.Page for .NET ile Özel Yazdırma Bileti Oluşturma'
url: /tr/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bilet Ekleme: Aspose.Page for .NET ile Özel Yazdırma Bileti Oluşturma

## Giriş

Bir .NET uygulamasında **bilet ekleme** işlevine ihtiyacınız varsa, Aspose.Page kod üzerinden doğrudan özel yazdırma biletleri oluşturmanızı sağlar. Bu öğreticide ortamı kurma, bir XPS belgesi oluşturma, özel iş yazdırma bileti ekleme ve sonucu kaydetme adımlarını adım adım göstereceğiz. Sonunda, herhangi bir yazdırma iş akışına güvenle bilet desteği ekleyebileceksiniz.

## Hızlı Yanıtlar
- **“bilet ekleme” ne anlama geliyor?** Yazıcı ayarlarını kontrol eden özel bir yazdırma biletinin (XPS meta verisi) belgeye gömülmesidir.  
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET.  
- **Lisans gerekli mi?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gerekir.  
- **Bunu .NET Core ile kullanabilir miyim?** Evet, Aspose.Page .NET Framework ve .NET Core’u destekler.  
- **Uygulama ne kadar sürer?** Temel bir bilet için genellikle 15 dakikadan az sürer.

## Özel Yazdırma Bileti Nedir?
Özel bir yazdırma bileti, yazıcı tercihlerini (örneğin, birleştirme, kopya sayısı, renk yönetimi vb.) tanımlayan XML tabanlı bir açıklamadır ve bir XPS belgesiyle birlikte taşınır. Geliştiricilerin bir belgenin nasıl yazdırılacağını programlı olarak belirlemelerine olanak tanır, böylece istemci tarafında manuel yapılandırma gerekmez.

## Aspose.Page ile bilet desteği eklemenin avantajları
- **İnce ayar kontrolü:** Kod üzerinden birleştirme, kopya sayısı, medya türü ve daha fazlasını ayarlayın.  
- **Çapraz platform tutarlılığı:** Aynı bilet, XPS meta verisini anlayan herhangi bir yazıcıda çalışır.  
- **Sorunsuz entegrasyon:** Ek hizmetlere ihtiyaç duymadan mevcut .NET projelerinizle doğrudan çalışır.

## Ön Koşullar

Başlamadan önce şunların olduğundan emin olun:

- C# ve .NET geliştirme konusunda temel bilgi.  
- Visual Studio (herhangi bir güncel sürüm) yüklü.  
- Projeye eklenmiş Aspose.Page for .NET kütüphanesi.  

Kütüphaneyi henüz eklemediyseniz, [Aspose.Page for .NET belgeleri](https://reference.aspose.com/page/net/) üzerinden indirebilirsiniz. Topluluk desteği için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

## Ad Alanlarını İçe Aktarma

XPS ve meta veri sınıflarını ortaya çıkaran ad alanlarını ekleyerek başlayın.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Şimdi uygulamayı adım adım inceleyelim.

## Adım 1: Belge Dizini Ayarlama

Oluşturulacak XPS dosyasının kaydedileceği yeri tanımlayın.

```csharp
string dir = "Your Document Directory";
```

## Adım 2: Yeni bir XPS Belgesi Oluşturma

Sayfaları ve bileti tutacak yeni bir XPS belgesi örneği oluşturun.

```csharp
XpsDocument xDocs = new XpsDocument();
```

## Adım 3: Özel İş Yazdırma Bileti Ekleme

Belgeye özel bir iş yazdırma bileti ekleyin. Bu, **bilet ekleme** işlevinin çekirdeğidir—burada birleştirme, kopya sayısı, render niyeti, renk yönetimi ve ihtiyacınız olan diğer ayarları belirtirsiniz.

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **İpucu:** Yer tutucu anlık görüntü dizesini, yazıcınızın yeteneklerine uygun Base64‑kodlu bir DEVMODE yapısı ile değiştirin.

## Adım 4: Belgeyi Kaydetme

XPS belgesini (gömülü biletle birlikte) diske kalıcı olarak kaydedin.

```csharp
xDocs.Save(dir + "output1.xps");
```

*output1.xps* dosyasını XPS meta verisini dikkate alan bir görüntüleyicide açtığınızda, yazıcı bilette tanımlanan ayarları otomatik olarak uygular.

## Yaygın Sorunlar ve Çözümleri

| Sorun | Neden | Çözüm |
|-------|-------|------|
| Bilet uygulanmıyor | Görüntüleyici XPS meta verisini yok sayıyor | XPS yazdırma biletlerini destekleyen bir yazıcı sürücüsü veya Microsoft XPS Viewer gibi bir görüntüleyici kullanın. |
| Geçersiz Base64 anlık görüntü | Bozuk DEVMODE verisi | `GetPrinter` API’si ile yazıcı sürücüsünden anlık görüntüyü yeniden oluşturun. |
| İzin eksikliği | `dir` klasörüne yazma izni yok | Uygulamanın yeterli dosya sistemi haklarıyla çalıştığından emin olun. |

## Sık Sorulan Sorular

**S: Aspose.Page for .NET diğer .NET framework’leriyle kullanılabilir mi?**  
C: Evet, Aspose.Page .NET Framework, .NET Core, .NET 5/6 ve sonrası ile çalışır.

**S: Aspose.Page için geçici bir lisans nasıl alınır?**  
C: Aspose.Page için geçici lisans edinmek üzere [bu bağlantıyı](https://purchase.aspose.com/temporary-license/) ziyaret edin.

**S: Aspose.Page desteği için bir topluluk forumu var mı?**  
C: Kesinlikle, faydalı tartışmalar ve destek için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) kullanabilirsiniz.

**S: Özel yazdırma biletlerinde hangi medya türleri destekleniyor?**  
C: Aspose.Page, düz kağıt, parlak ve özel medya tanımları dahil olmak üzere çeşitli medya türlerini destekler.

**S: Aspose.Page for .NET için örnek projeler mevcut mu?**  
C: Başlangıç için örnek projeler ve kod parçacıkları için [belgelere](https://reference.aspose.com/page/net/) göz atın.

## Sonuç

Aspose.Page for .NET kullanarak bir XPS belgesine **bilet ekleme** desteği eklemeyi ele aldık. Bu adımları izleyerek dosyalarınıza zengin yazdırma talimatları gömebilir ve .NET uygulamalarınız içinde yazdırma iş akışını tam kontrol edebilirsiniz. Belirli yazdırma ortamınıza uygun ek bilet ayarlarıyla denemeler yapmaktan çekinmeyin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-03-19  
**Test Edilen Versiyon:** Aspose.Page for .NET (en son kararlı sürüm)  
**Yazar:** Aspose  

---