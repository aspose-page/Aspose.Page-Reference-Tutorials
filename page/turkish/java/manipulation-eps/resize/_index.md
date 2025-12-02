---
date: 2025-12-02
description: Java'da Aspose.Page ile EPS dosyalarını sorunsuz bir şekilde yeniden
  boyutlandırmayı öğrenin. Bu adım adım rehber, EPS'yi puan, inç, milimetre veya yüzde
  olarak nasıl yeniden boyutlandıracağınızı gösterir.
language: tr
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Java'da Aspose.Page ile EPS Dosyalarını Yeniden Boyutlandırma
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Aspose.Page ile EPS Dosyalarını Yeniden Boyutlandırma

## Giriş
Programatik olarak **EPS dosyalarını yeniden boyutlandırma** için güvenilir bir yol arıyorsanız, doğru yerdesiniz. Bu öğreticide Aspose.Page kütüphanesini kullanarak Java'da EPS görüntülerinin yeniden boyutlandırılmasını adım adım göstereceğiz. Boyutu iki katına çıkarmanız, belirli bir ölçüye küçültmeniz ya da yüzde olarak çalışmanız gerekse, aşağıdaki adımlar çıktının boyutları üzerinde tam kontrol sağlar.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for Java  
- **Noktalar, inçler veya milimetreler kullanarak yeniden boyutlandırabilir miyim?** Evet – API üç birimi ve yüzdeyi destekler.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için lisans gereklidir.  
- **Gerekli Java sürümü nedir?** Java 8 veya üzeri.  
- **Kod iş parçacığı güvenli mi?** Her `PsDocument` örneği izole edildiğinden dosyaları paralel olarak işleyebilirsiniz.

## Önkoşullar
Koda geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde yüklü Java Development Kit (JDK).  
- Aspose.Page for Java kütüphanesi. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.  
- Java programlamaya temel bir anlayış.

## Paketleri İçe Aktarma
Java projenizde, Aspose.Page nesneleri ve standart I/O akışlarıyla çalışabilmek için gerekli içe aktarmaları ekleyin.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Noktalar Kullanarak EPS Yeniden Boyutlandırma
Aşağıda, ölçü birimi olarak nokta kullanarak bir EPS dosyasının boyutunu iki katına çıkaran eksiksiz, adım adım bir örnek bulunmaktadır.

### Adım 1: Giriş akışını ayarlama
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Adım 2: `PsDocument` nesnesini başlatma
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Adım 3: EPS görüntüsünün mevcut boyutunu çıkarma
```java
Dimension oldSize = doc.extractEpsSize();
```

### Adım 4: Yeniden boyutlandırılmış dosya için bir çıktı akışı oluşturma
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Adım 5: EPS'yi nokta kullanarak yeniden boyutlandırma ve kaydetme
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## İnç Kullanarak EPS Yeniden Boyutlandırma
Aynı beş adımlı desen uygulanır; sadece `Units.Points` yerine `Units.Inches` koyun ve ölçek faktörünü gerektiği gibi ayarlayın.

## Milimetre Kullanarak EPS Yeniden Boyutlandırma
Yine aynı adımları izleyin, birimi `Units.Millimeters` olarak değiştirin. Bu, baskı iş akışları için metrik tabanlı boyutlara ihtiyaç duyduğunuzda kullanışlıdır.

## Yüzde Kullanarak EPS Yeniden Boyutlandırma
Yüzde tabanlı ölçeklendirme için birimi `Units.Percent` olarak tutun. Orijinal genişlik ve yüksekliği istenen yüzdeyle çarpın (örneğin, %50 azalma için `0.5`).

## Yaygın Tuzaklar ve İpuçları
- **Her zaman akışları kapatın** – Üretim kodunda, dosya kilitlenmelerini önlemek için akışları try‑with‑resources ile sarın.  
- **En‑boy oranını koruyun** – Bozulma istemediğiniz sürece genişlik ve yüksekliği aynı faktörle çarpın.  
- **DPI'yi kontrol edin** – Yeniden boyutlandırma DPI'yı değiştirmez; farklı bir DPI'ye ihtiyacınız varsa, yeniden boyutlandırmadan sonra ayrı olarak ayarlayın.

## Sonuç
Artık **EPS dosyalarını yeniden boyutlandırma** konusunda Java'da Aspose.Page kullanarak, nokta, inç, milimetre ya da yüzde tercih etseniz de biliyorsunuz. Bu esneklik, EPS manipülasyonunu otomatik iş akışlarına, masaüstü araçlarına veya sunucu‑tarafı hizmetlerine entegre etmenizi sağlar.

## Sıkça Sorulan Sorular

**S: Bu kütüphaneyi diğer görüntü formatları için kullanabilir miyim?**  
C: Hayır, Aspose.Page yalnızca PostScript ve EPS dosyaları için özelleşmiştir.

**S: Aspose.Page for Java için ücretsiz bir deneme mevcut mu?**  
C: Evet, ücretsiz denemeyi **[buradan](https://releases.aspose.com/)** keşfedebilirsiniz.

**S: Ek yardım ve tartışmaları nerede bulabilirim?**  
C: Topluluk desteği için **[Aspose.Page forumunu](https://forum.aspose.com/c/page/39)** ziyaret edin.

**S: Geçici bir lisans nasıl alabilirim?**  
C: Geçici lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** alabilirsiniz.

**S: Kullanılabilir örnek projeler var mı?**  
C: Evet, belgeleri **[buradan](https://reference.aspose.com/page/java/)** kontrol edin.

---

**Son Güncelleme:** 2025-12-02  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (yazım zamanındaki en son)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}