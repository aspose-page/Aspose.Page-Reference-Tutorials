---
title: Görüntüyü Java'da EPS olarak kaydet
linktitle: Görüntüyü Java'da EPS olarak kaydet
second_title: Aspose.Page Java API'si
description: Görüntüleri zahmetsizce EPS olarak kaydetme konusunda Aspose.Page for Java'nın gücünü keşfedin. Bu çok yönlü Java kitaplığıyla grafik ve yazdırma yeteneklerinizi geliştirin.
weight: 12
url: /tr/java/postscript-conversion/save-image-as-eps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Görüntüyü Java'da EPS olarak kaydet

## giriiş
Java programlama dünyasında, Aspose.Page for Java, görüntüleri çeşitli formatlarda düzenlemek ve kaydetmek için güçlü bir araç olarak ortaya çıkıyor. Çok yönlü özellikleri arasında görüntüleri, profesyonel grafik ve baskıda yaygın olarak kullanılan bir format olan Encapsulated PostScript (EPS) dosyaları olarak kaydetme yeteneği yer alır.
Bu eğitim, Aspose.Page for Java'yı kullanarak bir görüntüyü EPS olarak kaydetme sürecinde size rehberlik edecektir. Önkoşulları, gerekli paketleri içe aktarmayı ele alacağız ve her adımı ayrıntılı açıklamalarla parçalara ayıracağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1.  Java Geliştirme Kiti (JDK): Aspose.Page for Java, sisteminizde çalışan bir JDK'nın kurulu olmasını gerektirir. En son JDK'yı indirebilirsiniz[Burada](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Page for Java Kütüphanesi: Aspose.Page for Java kütüphanesine sahip olduğunuzdan emin olun. Değilse, sürümden indirin[sayfa](https://releases.aspose.com/page/java/).
## Paketleri İçe Aktar
Önkoşulları ayarladıktan sonra, gerekli paketleri Java projenize aktarmanın zamanı geldi. Kodunuza aşağıdaki satırları ekleyin:
```java
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Varsayılan seçenekler oluştur
PsSaveOptions options = new PsSaveOptions();
```
Bu satırlar belge dizinini ayarlar ve görüntüyü EPS olarak kaydetmek için varsayılan seçenekler oluşturur.
Şimdi açık ve anlaşılır bir kılavuz için eğitimin giriş bölümünde sağlanan kod pasajını birden fazla adıma ayıralım.
## 1. Adım: Belge Dizinini Ayarlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
```
"Belge Dizininiz"i, çıktı EPS dosyasını depolamak istediğiniz gerçek yolla değiştirin.
## 2. Adım: Kaydetme Seçenekleri Oluşturun
```java
// Varsayılan seçenekler oluştur
PsSaveOptions options = new PsSaveOptions();
```
Bu adım, görüntüyü EPS olarak kaydetmek için varsayılan seçenekleri başlatır. Bu seçenekleri gereksinimlerinize göre özelleştirebilirsiniz.
## 3. Adım: Görüntüyü EPS olarak kaydedin
```java
// JPEG görüntüsünü EPS dosyasına kaydedin
PsDocument.saveImageAsEps(dataDir + "input1.jpg", dataDir + "output1.eps", options);
```
Bu son adımda kod, giriş görüntüsünü (bu durumda "input1.jpg") belirtilen dizinde "output1.eps" adlı bir EPS dosyası olarak kaydetmek için Aspose.Page kitaplığını kullanır.
Bu adımları kendi görüntü dosyası yollarınız ve dizin bilgilerinizle tekrarlayın.
## Çözüm
Tebrikler! Aspose.Page'i kullanarak bir görüntüyü Java'da EPS olarak nasıl kaydedeceğinizi başarıyla öğrendiniz. Bu güçlü işlevsellik, Java uygulamalarınızdaki gelişmiş grafik ve yazdırma yeteneklerinin kapılarını açar.
 Aspose.Page for Java'nın diğer özelliklerini aşağıdaki bağlantıya bakarak keşfedebilirsiniz.[dokümantasyon](https://reference.aspose.com/page/java/).
## Sıkça Sorulan Sorular
### Aspose.Page for Java tüm görüntü formatlarıyla uyumlu mu?
Evet, Aspose.Page for Java çok çeşitli görüntü formatlarını destekler, bu da onu çeşitli uygulamalar için çok yönlü kılar.
### EPS kaydetme seçeneklerini özelleştirebilir miyim?
Kesinlikle! Öğreticide varsayılan seçenekler tanıtılmaktadır, ancak bunları özel ihtiyaçlarınıza göre değiştirebilirsiniz.
### Aspose.Page for Java hakkında ek destek ve tartışmaları nerede bulabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) toplulukla etkileşime geçmek ve yardım istemek.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici bir lisans edinin[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
