---
title: Java XPS'de Dikdörtgen Ekleme
linktitle: Java XPS'de Dikdörtgen Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page'i kullanarak Java XPS'de nasıl dikdörtgen ekleyeceğinizi öğrenin. Kusursuz belge işleme için adım adım kılavuzumuzu izleyin. #JavaXPS #AsposePage
type: docs
weight: 11
url: /tr/java/xps-shapes/add-rectangle/
---
## giriiş
Aspose.Page kullanarak Java XPS'de dikdörtgen eklemeye ilişkin bu kapsamlı kılavuza hoş geldiniz! İster deneyimli bir geliştirici olun ister Java XPS'ye yeni başlıyor olun, bu eğitim size adım adım talimatlarla süreç boyunca yol gösterecek ve konuyu derinlemesine anlamanızı sağlayacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Java programlama dili hakkında temel bilgiler.
-  Aspose.Page kütüphanesi kuruldu. Değilse, adresinden indirebilirsiniz.[Aspose.Page Java belgeleri](https://reference.aspose.com/page/java/).
- Çalışan bir Java geliştirme ortamı.
## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın. Aspose.Page kütüphanesinin sınıf yolunuza doğru şekilde eklendiğinden emin olun. İşte temel bir örnek:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Şimdi Java XPS'de dikdörtgen eklemek için verilen örneği birden çok adıma ayıralım.
## 1. Adım: Belge Dizinini Ayarlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
```
"Belge Dizininiz"i istediğiniz dizinin yolu ile değiştirin.
## 2. Adım: Yeni Bir XPS Belgesi Oluşturun
```java
// Yeni XPS Belgesi oluştur
XpsDocument doc = new XpsDocument();
```
Bu, yeni bir XPS belgesini başlatır.
## Adım 3: CMYK Düz Renk Konturlu Dikdörtgen Ekleme
```java
// Sol altta CMYK (mavi) düz renkli konturlu dikdörtgen
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Bu adım, CMYK düz rengine sahip konturlu bir dikdörtgen ekler.
## 4. Adım: Ortaya Çıkan XPS Belgesini Kaydedin
```java
// Ortaya çıkan XPS belgesini kaydedin
doc.save(dataDir + "AddRectangle_out.xps");
```
Son olarak, değiştirilen XPS belgesini eklenen dikdörtgenle kaydedin.
Dikdörtgenlerinizi daha da özelleştirmek için parametreleri gerektiği gibi ayarlayarak bu adımları tekrarlayın.
## Çözüm
Tebrikler! Aspose.Page'i kullanarak Java XPS'de nasıl dikdörtgen ekleyeceğinizi başarıyla öğrendiniz. Bu eğitim, XPS belge işleme çalışmalarınız için sağlam bir temel sağlar.
## SSS
### Tek bir XPS belgesine birden çok dikdörtgen ekleyebilir miyim?
Evet, öğreticide özetlenen adımları tekrarlayarak gerektiği kadar dikdörtgen ekleyebilirsiniz.
### Dikdörtgenin rengini nasıl değiştirebilirim?
 Renk değerlerini değiştirin`createColor` İstenilen rengi elde etme yöntemi.
### Aspose.Page karmaşık XPS belge manipülasyonlarını yönetmeye uygun mudur?
Kesinlikle! Aspose.Page, çeşitli XPS belge görevlerini yerine getirmek için güçlü bir dizi özellik sunar.
### Ek örnekleri ve desteği nerede bulabilirim?
 Keşfedin[Aspose.Page forumu](https://forum.aspose.com/c/page/39)Daha fazla örnek için topluluktan yardım isteyin.
### Satın almadan önce Aspose.Page'i deneyebilir miyim?
 Evet, keşfedebilirsiniz[ücretsiz deneme](https://releases.aspose.com/) Aspose.Page'in yeteneklerini deneyimlemek için.