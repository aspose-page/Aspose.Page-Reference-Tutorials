---
date: 2025-11-29
description: Aspose.Page kullanarak Java'da XPS dosyalarını sorunsuz bir şekilde birleştirmeyi
  öğrenin. Verimli belge manipülasyonu için adım adım rehberimizi izleyin ve Java
  geliştirme becerilerinizi artırın.
language: tr
linktitle: Convert XPS to XPS in Java
second_title: Aspose.Page Java API
title: Aspose.Page ile Java'da XPS Dosyalarını Birleştirme
url: /java/file-merging/xps-to-xps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java ile Aspose.Page Kullanarak XPS Dosyalarını Birleştirme

XPS belgelerini birleştirmek, raporları, sunumları veya herhangi bir XPS dosyası koleksiyonunu tek bir, kolay‑paylaşılabilir paket haline getirmeniz gerektiğinde rutin bir görevdir. Bu öğreticide Aspose.Page for Java API'sini kullanarak **xps dosyalarını nasıl birleştireceğinizi** öğrenecek, net açıklamalar, gerçek‑dünya ipuçları ve çalıştırmaya hazır kod parçacıkları bulacaksınız.

## Hızlı Yanıtlar
- **XPS birleştirmeyi hangi kütüphane yönetir?** Aspose.Page for Java.  
- **Uygulama ne kadar sürer?** Temel bir birleştirme için yaklaşık 10‑15 dakika.  
- **Test için lisansa ihtiyacım var mı?** Evet – Aspose'tan geçici bir deneme lisansı temin edilebilir.  
- **Farklı sayfa sayısına sahip dosyaları birleştirebilir miyim?** Kesinlikle; Aspose.Page geçerli herhangi bir XPS belgesini birleştirir.  
- **Hangi Java sürümleri destekleniyor?** Java 8 ve üzeri (JDK 11+ önerilir).

## XPS Dosya Birleştirme Nedir?
XPS (XML Paper Specification), Microsoft'ın sabit‑düzen belge formatıdır. XPS dosyalarını birleştirmek, birden fazla XPS belgesini tek bir dosyada birleştirerek her sayfanın düzenini, yazı tiplerini ve grafikleri korumak anlamına gelir.

## Java’da XPS Dosyalarını Neden Birleştirirsiniz?
- **Otomasyon:** Birkaç modülden tek bir rapor oluşturun, manuel müdahale gerekmez.  
- **Tutarlılık:** Orijinal XPS sayfalarının tam görsel bütünlüğünü koruyun.  
- **Performans:** Aktarmanız veya saklamanız gereken dosya sayısını azaltın.  
- **Çapraz‑platform:** Java, birleştirme işlemini Windows, Linux veya macOS sunucularında çalıştırmanıza olanak tanır.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK):** Sisteminizde JDK yüklü olduğundan emin olun. [buradan](https://www.oracle.com/java/technologies/javase-downloads.html) indirebilirsiniz.  
- **Aspose.Page for Java:** Aspose.Page for Java kütüphanesini [Aspose web sitesinden](https://purchase.aspose.com/buy) indirip kurun.  
- **Integrated Development Environment (IDE):** Tercih ettiğiniz IDE'yi seçin; popüler seçenekler arasında Eclipse, IntelliJ IDEA veya NetBeans bulunur.

Her şey kurulduğuna göre, koda dalalım.

## Paketleri İçe Aktarma
Java projenizde, Aspose.Page for Java'ı kullanmak için gerekli paketleri içe aktararak başlayın. Java dosyanızın başına aşağıdaki satırları ekleyin:

```java
import java.io.FileOutputStream;

import com.aspose.xps.XpsDocument;
```

## Adım 1: Projenizi Kurun
Seçtiğiniz IDE'de yeni bir Java projesi oluşturun ve Aspose.Page JAR dosyalarını projenin derleme yoluna ekleyin. Bu, derleyicinin `XpsDocument` sınıfını bulmasını sağlar.

## Adım 2: XPS Çıktı Akışını Başlatın
Birleştirilmiş XPS dosyası için çıktı akışını ayarlayın. Birleştirilmiş dosyanın kaydedileceği dizini belirtin.

```java
String dataDir = "Your Document Directory";
FileOutputStream outStream = new FileOutputStream(dataDir + "mergedXPSfiles.xps");
```

> **Pro ipucu:** Geliştirme sırasında `FileNotFoundException` hatasından kaçınmak için mutlak bir yol kullanın, ardından üretim için göreli yola geçin.

## Adım 3: İlk XPS Dosyasını Yükleyin
Birleştirme için temel olacak ilk XPS dosyasını yükleyin.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

İlk belgenin özellikleri (sayfa boyutu ve yönü gibi) nihai birleştirilmiş dosya için varsayılan olur.

## Adım 4: XPS Dosyalarının Bir Dizisini Oluşturun
İlk dosyayla birleştirmek istediğiniz XPS dosyalarının bir dizisini hazırlayın.

```java
String[] filesForMerge = new String[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

İhtiyacınız kadar dosya yolu ekleyebilirsiniz; isterseniz dizi, bir dizin listesinden dinamik olarak oluşturulabilir.

## Adım 5: Birleştir ve Kaydet
Birleştirme işlemini yürütün ve sonucu belirtilen çıktı akışına kaydedin.

```java
document.merge(filesForMerge, outStream);
```

Bu çağrıdan sonra, `mergedXPSfiles.xps`, `input.xps`, `Demo.xps` ve `sample.xps` dosyalarındaki tüm sayfaları belirttiğiniz sırayla içerecek.

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **`FileNotFoundException`** | Yanlış `dataDir` yolu | Klasörün var olduğunu doğrulayın ve Windows'ta çift ters eğik çizgi (`\\`) kullanın. |
| **License not found** | Geçerli bir lisans olmadan çalıştırma | Aspose'tan geçici bir lisans uygulayın veya tam lisans satın alın. |
| **Merged file is empty** | Çıktı akışı temizlenmemiş/kapatılmamış | `document.merge(...)` sonrası `outStream.close()` çağırın. |
| **Mismatched page sizes** | Kaynak XPS dosyalarının boyutları farklı | Birleştirmeden önce `document.setPageSize(...)` kullanarak tek tip boyut zorlayın. |

## Sıkça Sorulan Sorular

**S: Farklı boyutlarda XPS dosyalarını birleştirebilir miyim?**  
C: Evet. Aspose.Page sayfa boyutlarını otomatik olarak normalleştirir, ancak birleştirmeden önce özel bir sayfa boyutu da ayarlayabilirsiniz.

**S: Test amaçlı geçici bir lisans mevcut mu?**  
C: Evet, test için geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Daha ayrıntılı belgeleri nerede bulabilirim?**  
C: Aspose.Page for Java dokümantasyonuna [buradan](https://reference.aspose.com/page/java/) bakın.

**S: Aspose.Page tartışmaları için topluluk forumları var mı?**  
C: Evet, toplulukla etkileşimde bulunmak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

**S: Aspose.Page for Java kütüphanesini nasıl satın alabilirim?**  
C: Kütüphaneyi [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Artık Aspose.Page for Java kullanarak **xps dosyalarını nasıl birleştireceğinize** dair eksiksiz, üretime hazır bir yönteme sahipsiniz. Yukarıdaki adımları izleyerek belge birleştirmeyi otomatikleştirebilir, iş akışı verimliliğini artırabilir ve Java uygulamalarınızı hafif ve güçlü tutabilirsiniz.

---

**Son Güncelleme:** 2025-11-29  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}