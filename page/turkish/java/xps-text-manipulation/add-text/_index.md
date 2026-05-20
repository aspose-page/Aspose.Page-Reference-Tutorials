---
date: 2026-04-24
description: Aspose.Page kullanarak Java’da XPS metni eklemeyi öğrenin – XPS belgeleri
  oluşturmak, metin eklemek ve XPS dosyalarını zahmetsizce kaydetmek için adım adım
  bir rehber.
keywords:
- how to add xps
- create xps document
- aspose.page add text
linktitle: Java XPS'te Metin Ekle
second_title: Aspose.Page Java API
title: Java'da XPS Metni Nasıl Eklenir – Aspose.Page Öğreticisi
url: /tr/java/xps-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java’da XPS Metni Nasıl Eklenir – Aspose.Page Öğreticisi

## Giriş
Programlı olarak **XPS metni ekleme** ihtiyacınız varsa, Aspose.Page for Java, XPS (XML Paper Specification) dosyalarıyla çalışmak için temiz ve yüksek performanslı bir API sunar. Bu öğreticide bir XPS belgesi oluşturmayı, stil verilmiş metin eklemeyi ve sonucu kaydetmeyi adım adım göstereceğiz—kısa ve takip etmesi kolay kodlarla. Rapor motoru oluşturuyor, fatura üretiyor ya da sadece bir sayfaya metin bindirmeniz gerektiğinde, bu adımlar sizi hızlıca çalışır duruma getirir.

## Hızlı Yanıtlar
- **Java’da XPS manipülasyonu için en iyi kütüphane nedir?** Aspose.Page for Java.
- **Lisans olmadan XPS dosyaları oluşturup kaydedebilir miyim?** Değerlendirme için ücretsiz deneme çalışır; üretim için bir lisans gerekir.
- **Hangi IDE'ler destekleniyor?** IntelliJ IDEA, Eclipse, NetBeans veya Java destekleyen herhangi bir IDE.
- **Basit bir metin eklemek için kaç satır kod gerekir?** Kurulum dahil yaklaşık 10 satır.
- **Yazı tipi stilini ayarlamak mümkün mü?** Evet – yazı tipi ailesi, boyutu, stili ve rengi ayarlayabilirsiniz.

## XPS Nedir ve Neden Metin Eklenir?
XPS (XML Paper Specification), Microsoft’un sabit‑düzen belge formatıdır; PDF’ye benzer ancak XML tabanlıdır. XPS dosyasına metin eklemek, etiketler, filigranlar veya raporlardaki dinamik veriler gibi kesin konumlandırma gerektiğinde yaygındır. Aspose.Page kullanarak düşük‑seviye XML yapılarıyla uğraşmadan XPS dosyalarını manipüle edebilirsiniz.

## XPS Metni Eklemek İçin Aspose.Page Neden Kullanılmalı?
- **Tam kontrol** glif konumlandırması, yazı tipi stilleri ve fırçalar üzerinde.  
- **Harici bağımlılık yok** – saf Java API.  
- **Yüksek doğrulukta** renderleme, düzeni platformlar arasında korur.  
- **Kapsamlı dokümantasyon** ve hızlı başlangıç için örnek kod.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

- **Java Development Kit (JDK)** – son sürüm (8 veya üzeri) yüklü.
- **Aspose.Page for Java** – kütüphaneyi resmi siteden [burada](https://releases.aspose.com/page/java/) indirin.
- **Bir Java IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz herhangi bir editör.

## Paketleri İçe Aktarma
XPS manipülasyonu için ihtiyaç duyacağınız sınıfları içe aktararak başlayın:

```java
import java.awt.Color;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
```

## Adım 1: Belge Dizini Ayarla (xps dosyası oluştur)
Oluşturulan XPS dosyasının nereye kaydedileceğini tanımlayın:

```java
String dataDir = "Your Document Directory";
```

## Adım 2: XPS Belgesi Oluştur (xps belgesi oluştur)
Yeni, boş bir XPS belgesi örnekleyin:

```java
XpsDocument doc = new XpsDocument();
```

## Adım 3: Metin Stili İçin Fırça Oluştur
Katı renkli bir fırça metnin rengini belirler. Burada siyah kullanıyoruz:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
```

## Adım 4: Glifleri Ekle – Gerçek Metin (aspose.page metin ekleme)
Belgede görünmesini istediğiniz metni ekleyin. `addGlyphs` yöntemiyle yazı tipi, boyut, stil ve tam koordinatları belirtebilirsiniz:

```java
XpsGlyphs glyphs = doc.addGlyphs("Arial", 12, XpsFontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.setFill(textFill);
```

## Adım 5: Oluşturulan XPS Belgesini Kaydet (xps dosyasını kaydet)
Son olarak belgeyi diske yazın:

```java
doc.save(dataDir + "AddText_out.xps");
```

Gerekli olduğunda ek satırlar eklemek, yazı tiplerini değiştirmek veya konumları ayarlamak için **Glifleri Ekle** adımını tekrarlayın.

## Yaygın Sorunlar ve Profesyonel İpuçları
- **Yanlış koordinatlar:** XPS, nokta (1/72 inç) cinsinden ölçülen bir koordinat sistemi kullanır. Metni hassas konumlandırmak için `x` ve `y` değerlerini ayarlayın.
- **Yazı tipi bulunamadı:** Yazı tipi adının (ör. “Arial”) kodu çalıştıran makinede yüklü olduğundan emin olun.
- **Lisans istisnası:** Geçerli bir lisans olmadan oluşturulan XPS bir filigran içerebilir. Bunu önlemek için lisansınızı uygulamanın erken aşamasında ekleyin.

## Sık Sorulan Sorular

### Aspose.Page tüm Java IDE'leriyle uyumlu mu?
Evet, Aspose.Page popüler Java IDE'leriyle, IntelliJ IDEA ve Eclipse dahil, çalışır.

### Eklenen metne farklı yazı tipi stilleri uygulayabilir miyim?
Kesinlikle! `XpsFontStyle.Bold`, `Italic` gibi stilleri `addGlyphs` çağrısında kullanabilir veya stilleri birleştirebilirsiniz.

### Aspose.Page için ek örnekler ve dokümantasyon nerede bulunur?
Kapsamlı dokümantasyonu [burada](https://reference.aspose.com/page/java/) inceleyin.

### Aspose.Page için ücretsiz deneme mevcut mu?
Evet, ücretsiz denemeye [burada](https://releases.aspose.com/) ulaşabilirsiniz.

### Aspose.Page için geçici lisans nasıl alınır?
Geçici lisansı [burada](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Metinle birlikte resim gömebilir miyim?**  
C: Evet – `XpsImage` nesnelerini gliflerle birlikte kullanarak zengin düzenler oluşturabilirsiniz.

**S: Aspose.Page Unicode karakterleri destekliyor mu?**  
C: Tamamen Unicode destekler, istediğiniz dilde metin eklemenize olanak tanır.

**S: Test için hangi Aspose.Page sürümü kullanıldı?**  
C: Kod, Aspose.Page 23.12 for Java ile test edilmiştir.

---

**Son Güncelleme:** 2026-04-24  
**Test Edilen Versiyon:** Aspose.Page 23.12 for Java  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}