---
date: 2026-09-04
description: Aspose.Page kullanarak Java'da EPS dosyalarını kırparak EPS dosya boyutunu
  nasıl azaltacağınızı öğrenin – eps kırpma, eps görüntüsü kırpma ve eps dosyasını
  budama adımlarını gösteren adım adım bir rehber.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: Java'da EPS Dosyasını Kırp
og_description: Aspose.Page kullanarak Java'da EPS dosyalarını kırparak EPS dosya
  boyutunu nasıl azaltacağınızı öğrenin – kod ve ipuçları içeren hızlı bir rehber.
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: Java'da EPS dosyalarını kırparak EPS dosya boyutunu azaltma
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: Java'da EPS dosyalarını kırparak EPS dosya boyutunu azaltma
url: /tr/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da EPS dosyalarını kırparak EPS dosya boyutunu azaltma

## Giriş
Java uygulamasında **EPS** dosyalarını programlı olarak **kırpmanız** ve **EPS dosya boyutunu azaltmanız** gerekiyorsa doğru yerdesiniz. Bu öğreticide, güçlü Aspose.Page for Java kütüphanesini kullanarak bir EPS görüntüsünü kırpma sürecini adım adım inceleyeceğiz. Rehberin sonunda EPS kırpmanın neden önemli olduğunu anlayacak, ihtiyacınız olan tam kodu görecek ve çözümü kendi projelerinize entegre etmeye hazır olacaksınız.

## Hızlı cevaplar
- **Java'da EPS kırpma işlemini hangi kütüphane yönetir?** Aspose.Page for Java.  
- **Temel bir kırpmanın uygulanması ne kadar sürer?** Yaklaşık 5‑10 dakika.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümleri destekleniyor?** Java 8 ve üzeri.  
- **Herhangi bir özel sınırlayıcı kutu tanımlayabilir miyim?** Evet – ihtiyacınız olan koordinatları sağlarsınız.

## EPS kırpma nedir ve neden kullanılır?
**EPS kırpma, bir EPS dosyasının görünen bölgesini tanımlayan yeni bir sınırlayıcı kutu oluşturur.**  
Bir EPS dosyasını kırpmak, istenmeyen boşlukları kaldırır ve grafiği gerçekten ihtiyacınız olan alana kadar keser; bu doğrudan **EPS dosya boyutunu azaltır** ve PDF'ler ya da raporlar gibi sonraki belgelerde düzen tutarlılığını artırır.

## Neden EPS dosyalarını kırparız?
EPS dosyalarını kırpmak, **dosya boyutunu %30'a kadar küçültmenizi**, fazla kenar boşluklarını ortadan kaldırmanızı ve toplu işleme hatları için grafikleri standartlaştırmanızı sağlar. Özellikle çok sayıda EPS varlığını tek bir PDF'e gömmek ya da düşük güçlü cihazlarda render süresini hızlandırmak istediğinizde çok faydalıdır.

## Önkoşullar
Kodlamaya başlamadan önce şunların yüklü olduğundan emin olun:

- **Aspose.Page for Java** kütüphanesi yüklü – resmi sayfadan indirin: [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 veya daha yeni bir sürüm makinenizde kurulu.  
- **Bir klasör** giriş EPS dosyanızı (`input.eps`) ve ortaya çıkan kırpılmış dosyayı (`output_crop.eps`) saklamak için.

## Paketleri içe aktar
İlk olarak gerekli Java sınıflarını içe aktarın. Bu kod parçacığı orijinal öğreticidekiyle tamamen aynı kalır:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## Java'da EPS görüntüsünü nasıl kırparız
Kaynak EPS dosyanızı yükleyin, yeni bir sınırlayıcı kutu tanımlayın ve kırpma API'sını çağırın – tüm işlem beş kısa adımda tamamlanır.

### Adım 1: belge dizinini ve giriş akışını ayarla
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Burada kodu, kaynak EPS dosyamızın bulunduğu klasöre yönlendiriyor ve dosyayı okumak için bir akış açıyoruz.

### Adım 2: PsDocument nesnesini başlat
`PsDocument` sınıfı, bir EPS dosyasını bellek içinde temsil eder ve özelliklerini okumanıza ve değiştirmenize olanak tanır.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
Bu nesne, orijinal sınırlayıcı kutuya ve diğer meta verilere erişim sağlar.

### Adım 3: başlangıç sınırlayıcı kutusunu çıkar
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Orijinal sınırlayıcı kutuyu çıkarmak, mevcut görünen alanın koordinatlarını verir – ne kadar kesmeniz gerektiğine karar vermeniz için kullanışlıdır.

### Adım 4: çıktı akışı oluştur
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Kırpılmış EPS'nin yazılacağı bir akış açıyoruz.

### Adım 5: yeni sınırlayıcı kutuyu tanımla ve kırp
`cropEps` yöntemi belgeyi yeni bir sınırlayıcı kutuya kadar kırpar ve sonucu bir çıktı akışına yazar.  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Tutmak istediğiniz alanı tanımlayan dört koordinatı (sol‑alt x, sol‑alt y, sağ‑üst x, sağ‑üst y) sağlayın. Yöntem kırpma işlemini gerçekleştirir ve sonucu `output_crop.eps` dosyasına yazar.

## Yaygın sorunlar ve çözümler
- **Yanlış koordinatlar:** EPS, nokta birimini (1/72 inç) kullanır. Kırpma hatalı görünüyorsa birim dönüşümünü tekrar kontrol edin.  
- **Dosya bulunamadı hataları:** `dataDir` değişkeninin uygun yol ayırıcıyla (`/` veya `\`) bittiğinden emin olun.  
- **Lisans istisnaları:** Geçerli bir lisans olmadan kodu çalıştırmak çıktıya bir filigran ekleyebilir. Üretim kullanımı öncesinde geçici ya da kalıcı lisansınızı uygulayın.

## Sıkça Sorulan Sorular

**S: Aspose.Page Java 8 ile uyumlu mu?**  
C: Evet, Aspose.Page Java 8 ve sonraki tüm sürümlerle çalışır.

**S: Aspose.Page'i ticari projelerde kullanabilir miyim?**  
C: Kesinlikle. Üretim dağıtımları için ticari bir lisans gereklidir. Bir lisans alabilirsiniz [Aspose purchase page](https://purchase.aspose.com/buy).

**S: Ek kaynakları ve topluluk desteğini nerede bulabilirim?**  
C: Resmi [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresinde tartışmalar, kod örnekleri ve sorun giderme ipuçları bulunur.

**S: Test için ücretsiz bir deneme mevcut mu?**  
C: Evet, ücretsiz deneme sürümünü yayın sayfasından indirebilirsiniz [Aspose.Page releases page](https://releases.aspose.com/).

**S: Kısa vadeli değerlendirme için geçici bir lisans nasıl alınır?**  
C: Geçici lisans, lisans portalından talep edilebilir [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Sonuç
Artık **Java'da Aspose.Page kullanarak EPS dosyalarını nasıl kırpacağınızı** ve **EPS dosya boyutunu nasıl azaltacağınızı** biliyorsunuz. Özel bir sınırlayıcı kutu tanımlayarak ve `cropEps` metodunu çağırarak sadece birkaç satır kodla istenmeyen kenar boşluklarını temizleyebilir veya bir EPS grafiğinin belirli bölümlerini izole edebilirsiniz. Bu kod parçacığını daha büyük belge‑işleme hatlarınızda EPS manipülasyonunu otomatikleştirmek, **EPS görüntüsü** varlıklarını kırpmak ve **EPS dosyasını** verimli bir şekilde kesmek için entegre edin.

---

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## İlgili Eğitimler

- [Java'da Aspose.Page ile EPS Dosyalarını Yeniden Boyutlandırma](/page/java/manipulation-eps/resize/)
- [Aspose.Page Java ile EPS'yi PNG'ye Dönüştürme (Ölçülü Lisans)](/page/java/license-management/set-metered-license/)
- [Aspose Page Java Öğreticisi – EPS Dosyalarına XMP Meta Verisi Ekleme](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}