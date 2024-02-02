---
title: Java XPS Görüntüsü Ekleme - Aspose.Page ile Basit Bir Kılavuz
linktitle: Java XPS'de Resim Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page'i kullanarak Java'da XPS belgelerine zahmetsizce nasıl resim ekleyeceğinizi öğrenin. Bu adım adım kılavuzla belge işleme sürecinizi geliştirin.
type: docs
weight: 10
url: /tr/java/xps-image-manipulation/add-image/
---
Java geliştirme dünyasında, XPS belgeleriyle çalışma yeteneği çeşitli uygulamalar için çok önemlidir. Aspose.Page for Java, XPS belgelerini yönetmek için güçlü bir araç seti sağlar ve önemli görevlerden biri de görüntüleri eklemektir. Bu adım adım kılavuzda, Aspose.Page for Java'yı kullanarak bir XPS belgesine resim ekleme sürecinde size yol göstereceğiz.
## giriiş
XPS belgelerine resim eklemek, rapor oluşturmadan belge işlemeye kadar pek çok Java uygulamasında ortak bir gereksinimdir. Aspose.Page for Java, görüntüleri XPS dosyalarınıza sorunsuz bir şekilde entegre etmek için etkili yöntemler sunarak bu görevi basitleştirir. Bu eğitimde Aspose.Page for Java kullanarak bir XPS belgesine nasıl resim ekleneceğini göstereceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1.  Aspose.Page for Java Library: Aspose.Page for Java kütüphanesini şu adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/page/java/).
2. Java Geliştirme Ortamı: Makinenizde bir Java geliştirme ortamının kurulu olduğundan emin olun.
Şimdi sonraki adımlara geçelim.
## Paketleri İçe Aktar
Gerekli sınıflara ve yöntemlere erişmek için Java projenizde gerekli Aspose.Page for Java paketlerini içe aktarın.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```
## 1. Adım: Belge Dizinini Ayarlayın
XPS belgesinin ve görüntü dosyalarının depolanacağı belge dizininizin yolunu tanımlayın.
```java
String dataDir = "Your Document Directory";
```
## 2. Adım: Yeni Bir XPS Belgesi Oluşturun
Aşağıdaki kod parçacığını kullanarak yeni bir XPS belgesi başlatın:
```java
XpsDocument doc = new XpsDocument();
```
## 3. Adım: XPS Belgesine Görüntü Ekleme
Bir görüntü eklemek için XPS belgesinde bir yol oluşturun ve sağlanan görüntü dosyasını ve koordinatları kullanarak görüntü fırçasını ayarlayın.
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```
## Adım 4: Sonuçtaki XPS Belgesini Kaydetme
Değiştirilen XPS belgesini belirttiğiniz dizine kaydedin.
```java
doc.save(dataDir + "AddImage_out.xps");
```
Daha fazla görsel eklemek veya mevcut görselleri proje gereksinimlerinize göre özelleştirmek için bu adımları tekrarlayın.
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak bir XPS belgesine nasıl görsel ekleyeceğinizi başarıyla öğrendiniz. Bu beceri, Java uygulamalarınızın ve belgelerinizin görsel çekiciliğini artırmak için çok değerlidir.
### Sıkça Sorulan Sorular
### Aspose.Page for Java'yı kullanarak aynı XPS belgesine birden fazla görüntü ekleyebilir miyim?
Evet, her görsel için bu eğitimde özetlenen adımları tekrarlayarak birden fazla görsel ekleyebilirsiniz.
### Aspose.Page for Java hangi görüntü formatlarını destekliyor?
Aspose.Page for Java, TIFF, JPEG, PNG ve GIF dahil olmak üzere çeşitli görüntü formatlarını destekler.
### Aspose.Page for Java'nın deneme sürümü mevcut mu?
 Evet, Aspose.Page for Java'nın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[bu bağlantı](https://releases.aspose.com/).
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 adresinden geçici lisans alabilirsiniz.[bu bağlantı](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java ile ilgili ek desteği nerede bulabilirim veya sorunları tartışabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) yardım istemek, deneyimleri paylaşmak ve Aspose.Page topluluğuyla bağlantı kurmak için.