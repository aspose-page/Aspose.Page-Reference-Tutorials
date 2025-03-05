---
title: Java PostScript'i Özelleştirin - Aspose.Page ile Dikdörtgenler Ekleme
linktitle: Java PostScript'te Dikdörtgen Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java kullanarak Java PostScript belgelerine canlı dikdörtgenler eklemeye ilişkin adım adım kılavuzu keşfedin. Belge özelleştirmenizi zahmetsizce geliştirin!
type: docs
weight: 11
url: /tr/java/postscript-shapes/add-rectangle/
---
## giriiş
Java PostScript belgelerinizi canlı dikdörtgenlerle geliştirmek mi istiyorsunuz? Başka yerde arama! Bu adım adım kılavuzda, PostScript belgelerinize dikdörtgenler eklemek için Aspose.Page for Java'yı nasıl kullanacağınızı keşfedeceğiz. Aspose.Page, PostScript dosyalarıyla çalışmak için sağlam özellikler sunan güçlü bir kütüphanedir; bu da onu, belgelerini değiştirmek ve özelleştirmek isteyen geliştiriciler için ideal bir seçim haline getirir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Java programlamanın temel anlayışı.
-  Aspose.Page for Java kütüphanesi kuruldu. Değilse, şuradan indirin:[Java belgeleri için Aspose.Page](https://reference.aspose.com/page/java/).
- Makinenizde kurulu bir Java geliştirme ortamı.
## Paketleri İçe Aktar
Java projenizde gerekli paketleri içe aktararak başlayın:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Öğretici: Java PostScript'te Dikdörtgenler Ekleme
## Adım 1: Dikdörtgeni Doldurmak için Boyayı Ayarlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
// Sayfa açıkken yeni PS Belgesi oluşturun
PsDocument document = new PsDocument(outPsStream, options, false);
// Dikdörtgeni doldurmak için boyayı ayarla
document.setPaint(Color.ORANGE);        
// İlk dikdörtgeni doldurun
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Adım 2: Dikdörtgeni Vurmak için Boyayı Ayarlayın
```java
// Dikdörtgeni okşamak için boyayı ayarla
document.setPaint(Color.RED);
// Konturu ayarla
document.setStroke(new BasicStroke(3));
// İkinci dikdörtgenin konturunu (ana hatlarını) çizin
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## 3. Adım: Geçerli Sayfayı Kapatın ve Belgeyi Kaydedin
```java
// Geçerli sayfayı kapat
document.closePage();
// Belgeyi kaydet
document.save();
```
Tebrikler! Aspose.Page'i kullanarak Java PostScript belgenize başarıyla canlı dikdörtgenler eklediniz.
## Çözüm
Bu eğitimde, Aspose.Page for Java'yı kullanarak Java PostScript belgelerinizi dikdörtgenlerle geliştirme sürecini inceledik. Bu güçlü kitaplık, belgelerini zahmetsizce özelleştirmek ve değiştirmek isteyen geliştiricilere fırsatlar dünyasının kapılarını açar.
Belgelerinizi görsel olarak çekici hale getirmek için farklı şekil ve renkleri deneyerek eğlenin!
## Sıkça Sorulan Sorular

### Aspose.Page for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Page öncelikle Java'yı destekler ancak diğer diller için de benzer kütüphaneler mevcuttur.
### Aspose.Page for Java'nın deneme sürümü mevcut mu?
 Evet, Aspose.Page for Java'nın özelliklerini şu adresle keşfedebilirsiniz:[ücretsiz deneme sürümü](https://releases.aspose.com/).
### Ek yardım ve tartışmaları nerede bulabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) toplulukla etkileşime geçmek ve yardım almak.
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java'nın lisanslı sürümünü nereden satın alabilirim?
 Lisanslı bir sürüm satın alın[Burada](https://purchase.aspose.com/buy).