---
title: Aspose.Page Java ile Zahmetsiz Ölçülü Lisans Entegrasyonu
linktitle: Java'da Ölçülü Lisansı Ayarlama
second_title: Aspose.Page Java API'si
description: Aspose.Page'in Java ile kusursuz entegrasyonunu keşfedin. Ölçülü lisansları zahmetsizce ayarlayın ve belge işleme yeteneklerinizi geliştirin.
type: docs
weight: 10
url: /tr/java/license-management/set-metered-license/
---
## giriiş
Aspose.Page'i kullanarak Java'da ölçülü lisans ayarlamaya ilişkin kapsamlı kılavuzumuza hoş geldiniz. Belge işleme yeteneklerinizi geliştirmek ve Aspose.Page ile kusursuz entegrasyon sağlamak istiyorsanız doğru yerdesiniz. Bu eğitimde, her adımı kolayca sindirilebilir parçalara ayırarak süreç boyunca size yol göstereceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java programlamanın temel bilgisi.
-  Aspose.Page kütüphanesi kuruldu. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/java/).
- Aspose hesabınız aracılığıyla edinebileceğiniz ölçülü genel ve özel anahtarlar.
## Paketleri İçe Aktar
Java programımız için gerekli paketleri içe aktararak başlayalım. Aspose.Page kütüphanesinin projenize entegre olduğundan emin olun.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## 1. Adım: Belgeyi ve Görüntü Formatını Başlatın
İlk adım, belgeyi hazırlamak ve istenen görüntü formatını tanımlamaktır.
```java
// ölçülü genel ve özel anahtarları ayarlama
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// setMeteredKey özelliğine erişin ve genel ve özel anahtarları parametre olarak iletin
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## 2. Adım: PostScript Giriş Akışını Başlatın
Bu adımda PostScript giriş akışını işlenmek üzere başlatıyoruz.
```java
// PostScript giriş akışını başlat
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## 3. Adım: Belge Lisansını Kontrol Edin
Devam etmeden önce belgenin uygun şekilde lisanslanıp lisanslanmadığını doğrulamak çok önemlidir.
```java
// Belgenin lisanslı olup olmadığını kontrol edin
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Adım 4: Seçenekleri ve Görüntü Cihazını Başlatın
Şimdi seçenekleri ve görüntü cihazını varsayılan parametrelerle başlatalım.
```java
// Seçenekler nesnesini varsayılan parametrelerle başlatın.
ImageSaveOptions options = new ImageSaveOptions();
// ImageDevice nesnesini varsayılan parametrelerle başlatın.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Adım 5: EPS Dosyasını Görüntü Olarak Kaydetme
Tanımlanan seçenekleri ve cihazı kullanarak EPS dosyasını görüntü olarak kaydedin.
```java
// EPS dosyasını resim olarak kaydet
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## 6. Adım: Görüntü Baytlarını Alın ve Kaydedin
Görüntü baytlarını alın ve bunları bir dosyaya kaydedin.
```java
// Görüntü baytlarını alın. Bir sayfa için bir bayt dizisi. Bizim durumumuzda bir sayfamız var.
byte[][] imagesBytes = device.getImagesBytes();
// Görüntü baytlarını dosyaya kaydet
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Çözüm
Tebrikler! Aspose.Page'i kullanarak Java'da başarıyla ölçülü bir lisans kurdunuz. Bu eğitimde, sorunsuz bir entegrasyon süreci sağlamak için adım adım bir kılavuz sağlanmıştır.
## SSS
### S: Ölçülü genel ve özel anahtarları nasıl edinebilirim?
Bu anahtarları Aspose hesabınız üzerinden alabilirsiniz.
### S: Aspose.Page kütüphanesi ücretsiz mi?
 Aspose.Page hem ücretsiz deneme hem de ücretli sürümler sunuyor. Ziyaret etmek[Burada](https://releases.aspose.com/) ücretsiz deneme için.
### S: Aspose.Page'i ticari projeler için kullanabilir miyim?
 Evet, Aspose.Page ticari lisanslar sunmaktadır. Bunları satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### S: Ek belgeleri nerede bulabilirim?
 Belgelere bakın[Burada](https://reference.aspose.com/page/java/).
### S: Geçici lisansları nasıl alabilirim?
 Geçici lisans alınabilecek[Burada](https://purchase.aspose.com/temporary-license/).