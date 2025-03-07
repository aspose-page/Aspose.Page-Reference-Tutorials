---
title: Java XPS'de Döşenmiş Görüntü Ekleme
linktitle: Java XPS'de Döşenmiş Görüntü Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page ile sorunsuz Java XPS belge işlemeyi keşfedin. Bu adım adım kılavuzu kullanarak döşemeli görüntüleri zahmetsizce eklemeyi öğrenin.
weight: 11
url: /tr/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'de Döşenmiş Görüntü Ekleme

## giriiş
Java geliştirmenin dinamik dünyasında, verimli belge işleme ve oluşturma ihtiyacı giderek artıyor. Aspose.Page for Java, geliştiricilere XPS belgeleriyle sorunsuz bir şekilde çalışma yeteneği sağlayan güçlü bir araç olarak ortaya çıkıyor. Bu eğitim belirli bir göreve odaklanmaktadır; Java XPS belgesine döşenmiş bir görüntü ekleme.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Page for Java: Aspose.Page for Java'yı şu adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/page/java/).
3. Belge Dizininiz: XPS belgenizi kaydetmek istediğiniz dizini seçin veya oluşturun.
## Paketleri İçe Aktar
Aspose.Page işlevlerini kullanmak için Java projenize gerekli paketleri içe aktarın:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Şimdi Java XPS belgesine döşenmiş bir görüntüyü net, yönetilebilir adımlara ekleme sürecini inceleyelim.
## 1. Adım: Projenizi Kurun
Aspose.Page for Java'nın düzgün şekilde entegre edildiğinden emin olarak Java projenizi kurarak başlayın.
## Adım 2: XPS Belgesi Oluşturun
Aşağıdaki kodu kullanarak yeni bir XPS belgesi başlatın:
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Yeni XPS Belgesi oluştur
XpsDocument doc = new XpsDocument();
```
## 3. Adım: Döşenmiş Görüntü Yolunu Tanımlayın
XPS belgesine eklemek istediğiniz döşenmiş görüntünün yolunu belirtin.
## Adım 4: Döşenmiş Görüntü Ekle
XPS belgesine döşenmiş bir görüntü eklemek için aşağıdaki kod parçacığını kullanın:
```java
// Döşeme resmi
// ImageBrush dolgulu dikdörtgen aşağıda sağ üstte
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Adım 5: Belgeyi Kaydedin
Son olarak, ortaya çıkan XPS belgesini aşağıdaki kodu kullanarak kaydedin:
```java
// Ortaya çıkan XPS belgesini kaydedin
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Aspose.Page'i kullanarak döşemeli bir görüntüyü Java XPS belgenize zahmetsizce dahil etmek için bu adımları tekrarlayın.
## Çözüm
Aspose.Page for Java, XPS belgeleriyle çalışma sürecini kolaylaştırarak geliştiricilere belge manipülasyonu için etkili bir çözüm sunar. Bu adım adım kılavuzu izleyerek, Java XPS belgenize döşemeli bir görüntüyü zahmetsizce ekleyebilirsiniz.

## SSS
### Aspose.Page tüm Java sürümleriyle uyumlu mu?
 Aspose.Page çeşitli Java sürümleriyle çalışacak şekilde tasarlanmıştır. Belgeleri kontrol ederek uyumluluğu sağlayın[Burada](https://reference.aspose.com/page/java/).
### Aspose.Page'i ticari projeler için kullanabilir miyim?
Evet, Aspose.Page ticari lisanslar sunmaktadır. Onları satın al[Burada](https://purchase.aspose.com/buy).
### Ücretsiz deneme mevcut mu?
 Evet, Aspose.Page özelliklerini ücretsiz deneme sürümüyle keşfedin[Burada](https://releases.aspose.com/).
### Topluluk desteğini ve tartışmalarını nerede bulabilirim?
 Aspose.Page topluluğuyla etkileşime geçin[forum](https://forum.aspose.com/c/page/39).
### Aspose.Page için nasıl geçici lisans alabilirim?
 Geçici bir lisans edinin[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
