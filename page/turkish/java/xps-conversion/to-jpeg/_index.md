---
date: 2026-03-13
description: Aspose.Page Java ile Java'da XPS'yi JPEG'e nasıl dönüştüreceğinizi öğrenin.
  Bu adım adım kılavuz, Aspose.Page Java kütüphanesini kullanarak XPS'yi JPEG'e verimli
  bir şekilde nasıl dönüştüreceğinizi gösterir.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java kullanarak Java'da XPS'yi JPEG'e nasıl dönüştürülür
url: /tr/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java’da Aspose.Page Java Kullanarak XPS’yi JPEG’e Nasıl Dönüştürülür

## Aspose.Page Java’ya Giriş
Bu öğreticide **Aspose.Page Java** kütüphanesi ile **XPS’yi JPEG’e nasıl dönüştüreceğinizi** öğreneceksiniz. XPS dosyalarını JPEG görüntülerine dönüştürmek, belge sayfalarını web portallarında, masaüstü görüntüleyicilerde veya e‑posta eklerinde raster grafik olarak göstermeniz gerektiğinde sıkça karşılaşılan bir gereksinimdir. Kodun her satırını adım adım inceleyecek, her ayarın neden önemli olduğunu açıklayacak ve bu dönüşüm hattını kendi Java uygulamalarınıza güvenle entegre edebilmeniz için pratik ipuçları paylaşacağız.

## Hızlı Yanıtlar
- **Dönüşümü hangi kütüphane gerçekleştirir?** Aspose.Page Java  
- **Belirli sayfaları seçebilir miyim?** Evet – `JpegSaveOptions` içinde `setPageNumbers` kullanın  
- **Hangi görüntü kalitesini kontrol edebilirim?** Düzleştirme modu, çözünürlük ve JPEG kalite ayarları  
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans gereklidir (ücretsiz deneme mevcuttur)  
- **Kod Java 8 ile uyumlu mu?** Kesinlikle – API Java 8 ve üzeri sürümlerle çalışır  

## XPS Nedir ve Neden XPS JPEG’e Dönüştürülür?
XPS (XML Paper Specification), PDF’ye benzer sabit‑düzen belge formatıdır. XPS’yi JPEG’e dönüştürmek, küçük resimler, e‑posta ekleri için raster görüntülere ihtiyaç duyduğunuzda veya yalnızca görüntü dosyalarını kabul eden sistemlerle entegrasyon yaparken faydalıdır. JPEG, görsel kalite ile dosya boyutu arasında iyi bir denge sağlar ve web‑tabanlı ön izlemeler için idealdir.

## Ön Koşullar
Koda geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Geliştirme Ortamı** – Yüklü ve yapılandırılmış JDK 8 veya daha yeni bir sürüm.  
- **Aspose.Page for Java** – En son kütüphaneyi resmi siteden [buradan](https://releases.aspose.com/page/java/) indirin.  
- **Örnek XPS Belgesi** – JPEG görüntülerine dönüştürmek istediğiniz bir XPS dosyası.  

## Paketleri İçe Aktarma
Gerekli sınıfları Java kaynak dosyanıza içe aktararak başlayın:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Adım 1: Yolları Başlatma ve XPS Belgesini Yükleme
Kaynak XPS dosyanızı içeren dizini ayarlayın ve bir `XpsDocument` örneği oluşturun:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Pro tip:** Platform bağımsız yol işleme için `java.nio.file` içinden `Paths.get()` kullanın.

## Adım 2: JPEG Kaydetme Seçeneklerini Yapılandırma
JPEG görüntülerinin nasıl oluşturulacağını tanımlayın—çözünürlük, düzleştirme ve hangi sayfaların dışa aktarılacağı:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` yazdırma için uygun yüksek çözünürlüklü çıktı üretir.  
- `setPageNumbers` sadece ihtiyacınız olan sayfaları seçmenizi sağlar, zaman ve bellek tasarrufu sağlar.

## Adım 3: Render Cihazını Oluşturma
`ImageDevice`, render edilen sayfaları bayt dizileri olarak yakalar:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Adım 4: XPS Belgesini JPEG’e Render Etme
`save` metodunu çağırın, cihazı ve yapılandırdığınız seçenekleri geçirin:

```java
document.save(device, options);
```

Bu noktada `device`, her bir öğenin JPEG kodlu bir sayfayı temsil ettiği iki boyutlu bir dizi tutar.

## Adım 5: Sonuç Üzerinde Döngü Oluşturup Dosyaları Yazma
Render edilen sayfalar üzerinde döngü yapın ve her bayt dizisini ayrı bir JPEG dosyasına yazın:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Her dosya `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` şeklinde adlandırılacak, böylece kaynak belge ve sayfa numarasını kolayca tanımlayabilirsiniz.

## Yaygın Kullanım Senaryoları
- **Belge yönetim sistemleri** için küçük resimler oluşturma.  
- Sadece görüntü formatlarının desteklendiği web uygulamalarına sayfa ön izlemeleri **gömme**.  
- Arşivleme veya raporlama amaçları için büyük XPS arşivlerini JPEG’e **toplu işleme**.  

## Yaygın Sorunlar ve Sorun Giderme
| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| **Boş JPEG dosyaları** | Çıktı akışı düzgün şekilde temizlenmemiş veya kapatılmamış | `imageStream.close()`'un iç döngü içinde (gösterildiği gibi) çağrıldığından emin olun. |
| **Büyük XPS dosyalarında bellek yetersizliği hataları** | Tüm sayfaları bir anda render etmek çok fazla RAM tüketir | Sayfaları daha küçük partilerde işleyin veya JVM yığın boyutunu (`-Xmx`) artırın. |
| **Eksik sayfalar** | `setPageNumbers` istenen sayfayı içermiyor | Sayfa numaraları dizisinin gerçek XPS sayfa indeksleriyle (1‑tabanlı) eşleştiğini doğrulayın. |

## Sıkça Sorulan Sorular

### Q: Aspose.Page ticari projeler için uygun mu?
A: Evet, Aspose.Page lisans seçenekleri bulunan ticari bir üründür. Detaylar için [buraya](https://purchase.aspose.com/buy) bakın.

### Q: Aspose.Page'ı satın almadan önce deneyebilir miyim?
A: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) edinebilirsiniz.

### Q: Aspose.Page belgelerini nerede bulabilirim?
A: Belgeler [burada](https://reference.aspose.com/page/java/) mevcuttur.

### Q: Aspose.Page için nasıl destek alabilirim?
A: Topluluk tabanlı destek için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

### Q: Test için geçici bir lisansa ihtiyacım var mı?
A: Evet, geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

## Sonuç
Artık **Aspose.Page Java** kullanarak **XPS’yi JPEG’e nasıl dönüştüreceğinizi** öğrendiniz. Adım adım rehberi izleyerek bu dönüşüm hattını herhangi bir Java uygulamasına—masaüstü aracı, web servisi veya toplu işleme yardımcı programı olsun—entegre edebilirsiniz. Projenizin ihtiyaçlarına göre farklı çözünürlükler, sayfa seçimleri ve görüntü formatlarıyla denemeler yapmaktan çekinmeyin.

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Page 24.11 for Java (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}