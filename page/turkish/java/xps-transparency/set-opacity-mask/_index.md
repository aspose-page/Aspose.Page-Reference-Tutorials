---
title: Java XPS'de Opaklık Maskesini Ayarlama
linktitle: Java XPS'de Opaklık Maskesini Ayarlama
second_title: Aspose.Page Java API'si
description: Aspose.Page ile Java XPS'de opaklık maskeleri ayarlamanın gücünü keşfedin. Görsel olarak geliştirilmiş bir belge deneyimi için adım adım kılavuzumuzu izleyin.
weight: 11
url: /tr/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'de Opaklık Maskesini Ayarlama

## giriiş
Aspose.Page'i kullanarak Java XPS'de opaklık maskelerini ayarlamaya ilişkin kapsamlı kılavuzumuza hoş geldiniz. Bu eğitimde, Aspose.Page for Java'nın güçlü özelliklerini kullanarak XPS belgesi oluşturma, tuval ekleme ve dikdörtgene opaklık maskesi uygulama sürecinde size yol göstereceğiz.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Java programlamanın temel anlayışı.
-  Aspose.Page for Java kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
-  Aspose.Page için geçerli bir lisans. Eğer lisansınız yoksa geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
- Java uygulamalarını çalıştırmak için ayarlanmış bir geliştirme ortamı.
## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın. Aspose.Page kütüphanesinin düzgün şekilde entegre edildiğinden emin olun. Aşağıda size yol gösterecek bir pasaj bulunmaktadır:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Şimdi örnek kodu birden çok adıma ayıralım:
## 1. Adım: Yeni Bir XPS Belgesi Oluşturun
```java
// Yeni bir XPS belgesi oluştur
XpsDocument doc = new XpsDocument();
```
## Adım 2: Kanvas Ekle
```java
// Yeni tuval
XpsCanvas canvas = doc.addCanvas();
```
## 3. Adım: Opaklık Maskesi ile Dikdörtgen Ekleyin
```java
// ImageBrush tarafından maskelenen opaklıkla sol ortadaki dikdörtgen
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Adım 4: ImageBrush ile Opaklık Maskesini Ayarlayın
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Adım 5: Ortaya Çıkan XPS Belgesini Kaydedin
```java
// Ortaya çıkan XPS belgesini kaydedin
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Aspose.Page'i kullanarak Java XPS belgenize opaklık maskeleri eklemek için bu adımları dikkatlice izleyin.
## Çözüm
Tebrikler! Aspose.Page ile Java XPS'de opaklık maskelerinin nasıl ayarlanacağını başarıyla öğrendiniz. Bu özellik, belgelerinize bir görsel zenginlik katmanı ekleyerek onları daha ilgi çekici ve dinamik hale getirir.
## SSS
### Aspose.Page tüm Java geliştirme ortamlarıyla uyumlu mu?
Evet, Aspose.Page çeşitli Java geliştirme ortamlarıyla sorunsuz çalışacak şekilde tasarlanmıştır.
### Aspose.Page'i lisanssız kullanabilir miyim?
Aspose.Page'i lisans olmadan kullanabilirsiniz ancak tüm özellik ve destek yelpazesi için bir lisans almanız önerilir.
### Deneme sürümünde herhangi bir sınırlama var mı?
Deneme sürümünde bazı özellik sınırlamaları olabilir. Ayrıntılar için belgeleri kontrol etmeniz önerilir.
### Aspose.Page için nasıl destek alabilirim?
 Ziyaret edebilirsiniz[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği için veya premium yardım için bir lisans satın alın.
### Aspose.Page'in para iade garantisi var mı?
 Bakın[satın alma sayfası](https://purchase.aspose.com/buy) Geri ödeme politikaları hakkında bilgi için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
