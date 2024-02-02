---
title: Java'da EPS Dosyalarını Kırpma - Aspose.Page ile Adım Adım Kılavuz
linktitle: Java'da EPS Dosyasını Kırp
second_title: Aspose.Page Java API'si
description: Aspose.Page'i kullanarak Java'da EPS dosyalarını kırpmaya ilişkin adım adım kılavuzu keşfedin. Belge işleme becerilerinizi zahmetsizce geliştirin.
type: docs
weight: 10
url: /tr/java/manipulation-eps/crop/
---
## giriiş
Java uygulamanızda EPS dosyalarını değiştirmek mi istiyorsunuz ve bunları nasıl verimli bir şekilde kırpacağınızı mı merak ediyorsunuz? Başka yerde arama! Bu kapsamlı kılavuzda, güçlü Aspose.Page for Java kütüphanesini kullanarak EPS dosyalarını kırpma işleminde size adım adım yol göstereceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
-  Aspose.Page for Java kütüphanesi: Aspose.Page for Java kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
- Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun.
- Belge Dizininiz: Giriş ve çıkış EPS dosyalarınızı depolamak için özel bir dizin oluşturun.
## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın. Aşağıdaki kod parçacığı gerekli paketlerin nasıl içe aktarılacağını gösterir:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```
Şimdi daha net bir anlayış için yukarıdaki kodun her adımını ayrı ayrı inceleyelim.
## 1. Adım: Belge Dizinini ve Giriş Akışını Ayarlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// EPS dosyası için bir giriş akışı oluşturun
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Bu adımda EPS dosyalarınızın bulunduğu dizin yolunu ayarlayıp hedef EPS dosyası için bir giriş akışı oluşturuyoruz.
## Adım 2: PsDocument Nesnesini Başlatın
```java
// PsDocument nesnesini giriş akışıyla başlat
PsDocument doc = new PsDocument(inputEpsStream);
```
Burada, önceki adımda oluşturulan giriş akışını kullanarak bir PsDocument nesnesini başlatıyoruz.
## Adım 3: İlk Sınırlayıcı Kutuyu Çıkarın
```java
// EPS görüntüsünün ilk sınırlayıcı kutusunu alın
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Kırpma parametrelerinin tanımlanmasına yardımcı olan EPS görüntüsünün ilk sınırlayıcı kutusunu alın.
## 4. Adım: Çıktı Akışı Oluşturun
```java
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Kırpılan EPS görüntüsünü kaydetmek için bir çıktı akışı oluşturun.
## Adım 5: Yeni Sınırlayıcı Kutuyu Tanımlayın ve Kırpın
```java
// Yeni sınırlayıcı kutu oluştur
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// EPS görüntüsünü kırpın ve çıktı akışına kaydedin
doc.cropEps(outputEpsStream, newBoundingBox);
```
Belirli koordinatlara ve boyutlara sahip yeni bir sınırlayıcı kutu tanımlayın ve ardından EPS görüntüsünü buna göre kırpmaya devam edin.
## Çözüm
Tebrikler! Aspose.Page'i kullanarak EPS dosyalarını Java'da nasıl kırpacağınızı başarıyla öğrendiniz. Belge işleme yeteneklerinizi geliştirmek için bu bilgiyi projelerinize ekleyin.
## SSS
### S: Aspose.Page Java 8 ile uyumlu mu?
C: Evet, Aspose.Page, Java 8 ve üzeri sürümlerle uyumludur.
### S: Aspose.Page'i ticari amaçlarla kullanabilir miyim?
 C: Evet, yapabilirsiniz. Lisans ayrıntıları için şu adresi ziyaret edin:[Burada](https://purchase.aspose.com/buy).
### S: Ek kaynakları ve desteği nerede bulabilirim?
 C: Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) Tartışma ve destek için.
### S: Ücretsiz deneme mevcut mu?
 C: Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### S: Geçici lisansı nasıl alabilirim?
 C: Geçici bir lisans alın[Burada](https://purchase.aspose.com/temporary-license/).