---
date: 2026-05-05
description: Aspose.Page for Java kullanarak EPS dosyalarına XMP adlandırılmış değerleri
  eklemeyi öğrenin – adım adım kod örnekli bir rehber.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: Java kullanarak XMP'ye Adlandırılmış Değer Ekle
second_title: Aspose.Page Java API
title: Java Kullanarak EPS Dosyalarına XMP Adlandırılmış Değer Nasıl Eklenir
url: /tr/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Kullanarak XMP Metaverisine Adlandırılmış Değer Ekleme

## Giriş
Modern Java geliştirmede, EPS dosyaları içinde **XMP** metaverisini nasıl ekleyeceğinizi öğrenmek, belge kökenini korumak ve aranabilirliği artırmak için gereklidir. **asp** (Aspose.Page for Java) ile XMP paketine özel adlandırılmış değerleri zahmetsizce enjekte edebilirsiniz. Bu öğretici, tam kod parçacıklarıyla birlikte kesin adımları size göstererek, bugün EPS belgelerinize XMP metaverisi eklemeye başlamanızı sağlar.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java (asp)  
- **Hedeflenen dosya türü nedir?** XMP metaverisi içeren EPS dosyaları  
- **Ana kullanım durumu?** XMP'ye özel adlandırılmış değerler (ör. sayfa boyutu limitleri) eklemek  
- **Önkoşullar?** JDK 8+ ve Aspose.Page for Java kütüphanesi  
- **Tipik uygulama süresi?** Kütüphane kurulduktan sonra 5–10 dakika  

## asp Nedir?
*asp*, **Aspose**'un kısaltmasıdır; belge işleme süreçlerini basitleştiren .NET ve Java API'lerinden oluşan bir aile. Aspose.Page for Java bileşeni, PostScript ve EPS dosyalarını oluşturmanıza, düzenlemenize ve dönüştürmenize olanak tanırken, XMP dahil olmak üzere metaverilerine tam programatik erişim sağlar.

## Neden XMP Metaverisine Adlandırılmış Değerler Eklenir?
- **Arama motoru dostu:** Özel etiketler keşfedilebilirliği artırır.  
- **İş akışı otomasyonu:** Sonraki araçlar, karar vermek için özel değerlerinizi okuyabilir.  
- **Uyumluluk:** Düzenleyici bilgileri doğrudan belge paketine gömebilirsiniz.  

## Bunun Önemi
XMP'ye adlandırılmış değerler eklemek, tüm EPS dosyasını ayrıştırmadan okunabilen key‑value çiftlerini saklamanızı sağlar. Bu yetenek, otomatik yayınlama hatları, dijital varlık yönetim sistemleri ve metaverinin sonraki adımları yönlendirdiği uyumluluk odaklı iş akışları gibi ortamlarda özellikle değerlidir.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK):** Makinenizde kurulu olan güncel bir JDK (8 veya üzeri).  
- **Aspose.Page for Java Kütüphanesi:** Resmi [download link](https://releases.aspose.com/page/java/) adresinden indirin. JAR dosyasını projenizin sınıf yoluna ekleyin.  
- **Bir EPS dosyası** zaten XMP metaverisi içeren ya da otomatik olarak oluşturulacak bir EPS dosyası.

## Paketleri İçe Aktarma
Gerekli Java paketlerini içe aktararak başlayın. Bu importlar, dosya akışlarına, EPS belge modeline ve XMP işleme sınıflarına erişim sağlar.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Java Kullanarak EPS Dosyalarına XMP Adlandırılmış Değer Ekleme
Aşağıda, bir EPS belgesine **XMP** adlandırılmış değerlerin nasıl ekleneceğini adım adım gösteren kısa bir numaralı rehber bulunmaktadır.

### Adım 1: Giriş EPS Dosya Akışını Başlatma
Kaynak EPS dosyasını bir `FileInputStream` içine yükleyin. Bu akış, belgeyi Aspose API'sine besler.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Pro ipucu:** `dataDir` değişkenini yapılandırılabilir tutun, böylece aynı kod farklı ortamlar arasında çalışabilir.

### Adım 2: XMP Metaverisini Almak
Mevcut XMP paketini alın. EPS dosyasında bir paket yoksa, Aspose PS yorumlarından doldurulmuş yeni bir XMP nesnesi oluşturur.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Adım 3: Adlandırılmış Değer Ekleme
XMP yapısına özel bir adlandırılmış değer ekleyin. Bu örnekte `xmpTPg:MaxPageSize` ad alanı altında yeni bir anahtar ekliyoruz.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Neden önemli:** Adlandırılmış değerler, sonraki uygulamaların belgeyi tamamen ayrıştırmadan okuyabileceği key‑value çiftlerini saklamanızı sağlar.

### Adım 4: Çıkış EPS Dosya Akışını Başlatma
Değiştirilen EPS'nin kaydedileceği bir `FileOutputStream` hazırlayın.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Adım 5: Belgeyi Kaydetme
Değişiklikleri kalıcı hale getirin. `save` çağrısı, güncellenmiş XMP paketini EPS dosyasına geri yazar.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Adım 6: Giriş EPS Akışını Kapatma
Kaynak sızıntılarını önlemek için orijinal dosya tutamacını serbest bırakın.

```java
psStream.close();
```

Bu altı adımı izleyerek, **asp** (Aspose.Page for Java) kullanarak **XMP metaverisine bir adlandırılmış değer eklemiş** oldunuz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-----|
| `xmp` üzerinde `NullPointerException` | EPS dosyasında XMP yok ve Aspose bir tane oluşturamadı | EPS'nin en az bir PS yorumu içerdiğinden emin olun veya manuel olarak yeni bir `XmpMetadata` örneği oluşturun. |
| Çıktı dosyası boş | Çıktı akışı temizlenmemiş/kapatılmamış | `outPsStream.close()`'un bir `finally` bloğunda çağrıldığını doğrulayın (gösterildiği gibi). |
| Aynı anahtar hatası | Aynı adlandırılmış değer iki kez eklenmiş | Eklemeden önce anahtarın `xmp.containsNamedValue(...)` ile zaten var olup olmadığını kontrol edin. |

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java'ı diğer Java kütüphaneleriyle kullanabilir miyim?**  
C: Evet, Aspose.Page for Java, diğer Java kütüphaneleriyle sorunsuz çalışacak şekilde tasarlanmıştır ve geliştirme ortamınızda esneklik sağlar.

**S: Aspose.Page for Java için ücretsiz deneme mevcut mu?**  
C: Evet, Aspose.Page for Java'ın ücretsiz denemesine [buradan](https://releases.aspose.com/) erişebilirsiniz.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Aspose.Page for Java için geçici lisans almak üzere [bu bağlantıyı](https://purchase.aspose.com/temporary-license/) ziyaret edin.

**S: Aspose.Page for Java için daha fazla öğretici ve örnek nerede bulunabilir?**  
C: Kapsamlı öğreticiler ve örnekler için [belgelendirmeyi](https://reference.aspose.com/page/java/) inceleyin.

**S: Aspose.Page for Java büyük ölçekli projeler için uygun mu?**  
C: Kesinlikle, Aspose.Page for Java büyük ölçekli projeleri verimli bir şekilde yönetmek için tasarlanmıştır ve güçlü belge işleme yetenekleri sunar.

## Sonuç
Bu rehberde, **asp** (Aspose.Page for Java) kullanarak EPS dosyalarında **XMP metaverisine adlandırılmış değerler eklemenin** ne kadar basit olduğunu gösterdik. Yukarıdaki adımlarla, belgelerinizi özel metaveriyle zenginleştirebilir, aranabilirliği artırabilir ve daha akıllı sonraki işlemeyi mümkün kılabilirsiniz.

---

**Son Güncelleme:** 2026-05-05  
**Test Edilen Sürüm:** Aspose.Page for Java 24.12 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}