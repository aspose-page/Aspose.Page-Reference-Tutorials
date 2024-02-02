---
title: Aspose.Page ile Java'da EPS Dosyalarını Yeniden Boyutlandırın
linktitle: Java'da EPS Dosyasını Yeniden Boyutlandır
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java ile EPS dosyalarını Java'da zahmetsizce nasıl yeniden boyutlandıracağınızı öğrenin. Adım adım talimatlar için kapsamlı kılavuzumuzu takip edin.
type: docs
weight: 11
url: /tr/java/manipulation-eps/resize/
---
## giriiş
Güçlü Aspose.Page kitaplığını kullanarak EPS dosyalarını Java'da yeniden boyutlandırmaya ilişkin adım adım kılavuzumuza hoş geldiniz. EPS görsellerinizin boyutlarını programlı olarak ayarlamanız gerekiyorsa doğru yerdesiniz. Bu eğitimde, size özel gereksinimleriniz için ihtiyaç duyduğunuz esnekliği sağlayacak şekilde nokta, inç, milimetre ve yüzdeler dahil olmak üzere çeşitli yeniden boyutlandırma seçeneklerini inceleyeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Page Java kütüphanesi için. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
- Java programlamanın temel anlayışı.
## Paketleri İçe Aktar
Aspose.Page işlevlerini kullanmak için Java projenizde gerekli içe aktarımlara sahip olduğunuzdan emin olun. İşte bir örnek:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Şimdi öğreticiyi her yeniden boyutlandırma seçeneği için birden fazla adıma ayıralım:
## Noktaları kullanarak EPS'yi yeniden boyutlandırın
### 1. Adım: Giriş akışını ayarlayın
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### 2. Adım: PsDocument nesnesini başlatın
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### 3. Adım: EPS görüntüsünün geçerli boyutunu çıkarın
```java
Dimension oldSize = doc.extractEpsSize();
```
### 4. Adım: Çıkış akışı oluşturun
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### 5. Adım: Yeniden boyutlandırın ve noktaları kaydedin
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## İnç kullanarak EPS'yi yeniden boyutlandırın
Örnek 1'dekine benzer adımları izleyin, "Puan"ı "İnç" ile değiştirin ve yeni boyutu buna göre ayarlayın.
## Milimetre kullanarak EPS'yi yeniden boyutlandırın
Örnek 1'dekine benzer adımları izleyin, "Nokta"yı "Milimetre" ile değiştirin ve yeni boyutu buna göre ayarlayın.
## Yüzdeleri kullanarak EPS'yi yeniden boyutlandırın
Örnek 1'dekine benzer adımları izleyin, "Puan"ı "Yüzdeler" ile değiştirin ve yeni boyutu buna göre ayarlayın.
## Çözüm
Tebrikler! Aspose.Page'i kullanarak EPS dosyalarını Java'da nasıl yeniden boyutlandıracağınızı başarıyla öğrendiniz. Bu kılavuz size çok yönlü seçenekler sunarak, yeniden boyutlandırma sürecini özel ihtiyaçlarınızı karşılayacak şekilde uyarlamanızı sağlar.

## SSS
### Bu kütüphaneyi diğer resim formatları için kullanabilir miyim?
Hayır, Aspose.Page özellikle PostScript ve EPS dosyalarını işlemek için tasarlanmıştır.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Ek yardım ve tartışmaları nerede bulabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği için.
### Geçici lisansı nasıl alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Örnek projeler mevcut mudur?
 Evet, belgeleri kontrol edin[Burada](https://reference.aspose.com/page/java/).