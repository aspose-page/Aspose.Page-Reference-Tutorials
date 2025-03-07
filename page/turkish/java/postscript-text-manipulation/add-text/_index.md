---
title: Aspose.Page Java Metin İşleme
linktitle: Java PostScript'e Metin Ekleme
second_title: Aspose.Page Java API'si
description: PostScript belgelerine metin ekleme eğitimimizde Aspose.Page for Java'nın gücünü keşfedin. Sistem ve özel yazı tiplerini kolaylıkla kullanmayı öğrenin.
weight: 10
url: /tr/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Metin İşleme

## giriiş
Aspose.Page for Java'yı kullanarak Java PostScript'e metin eklemeyle ilgili adım adım kılavuzumuza hoş geldiniz. Aspose.Page for Java, geliştiricilerin PostScript belgelerini kolaylıkla değiştirmelerine olanak tanıyan güçlü bir kütüphanedir. Bu öğreticide, görsel olarak çekici bir sonuç için metin ekleme, sistem ve özel yazı tiplerini kullanma, metnin ana hatlarını çizme ve konturları birleştirme sürecinde size yol göstereceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
-  Aspose.Page for Java kütüphanesi kuruldu. adresinden indirebilirsiniz.[Java indirme sayfası için Aspose.Page](https://releases.aspose.com/page/java/).
-  Belirtilen klasörde gerekli yazı tipleri mevcuttur. Ek bilgileri şurada bulabilirsiniz:[Java belgeleri için Aspose.Page](https://reference.aspose.com/page/java/).
## Paketleri İçe Aktar
Java projenizde Aspose.Page for Java için gerekli paketleri içe aktarın:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## 1. Adım: Belgeyi Ayarlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// PS dosyasına yazılacak bir metin
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Yeni 1 sayfalık PS Belgesi oluştur
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Adım 2: Metni Doldurmak için Sistem Yazı Tipini Kullanma
```java
// Metni doldurmak için sistem yazı tipini kullanma
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Metni varsayılan veya önceden tanımlanmış renkle (siyah) doldurun
document.fillText(str, font, 50, 100);
// Metni mavi renkle doldur
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Adım 3: Metni Doldurmak için Özel Yazı Tipini Kullanma
```java
// Metni doldurmak için özel yazı tipi kullanma
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Metni varsayılan veya önceden tanımlanmış renkle (siyah) doldurun
document.fillText(str, drFont, 50, 200);
// Metni mavi renkle doldur
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Adım 4: Sistem Yazı Tipiyle Metnin Ana Hatlarını Belirleme
```java
// Metnin ana hatlarını çizmek için sistem yazı tipini kullanma
document.outlineText(str, font, 50, 300);
// Mavi-mor renkli 2 punto genişliğinde kalemle metnin ana hatlarını çizin
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Metni turuncu renkle doldurun ve mavi renkli 2 punto genişliğinde kalemle kontur yapın
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Adım 5: Özel Yazı Tipiyle Metnin Ana Hatlarını Belirleme
```java
// Metnin ana hatlarını çizmek için özel yazı tipi kullanma
document.outlineText(str, drFont, 50, 450);
// Mavi-mor renkli 2 punto genişliğinde kalemle metnin ana hatlarını çizin
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Metni turuncu renkle doldurun ve mavi renkli 2 punto genişliğinde kalemle kontur yapın
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Adım 6: Belgeyi Kaydedin
```java
// Geçerli sayfayı kapat
document.closePage();
// Belgeyi kaydet
document.save();
```
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak Java PostScript'e nasıl metin ekleyeceğinizi başarıyla öğrendiniz. Belgenizi daha da geliştirmek için farklı yazı tipleri, renkler ve anahat seçeneklerini deneyin.
## Sıkça Sorulan Sorular
### Aspose.Page for Java'da kendi özel yazı tiplerimi kullanabilir miyim?
 Evet, yazı tipi adını ve boyutunu belirterek özel yazı tiplerini kullanabilirsiniz.`DrFont` sınıf.
### Metnin rengini nasıl değiştirebilirim?
 İstenilen rengi düğmeyi kullanarak ayarlayabilirsiniz.`Color` Metni doldururken veya ana hatlarını çizerken sınıf.
### PostScript belgesine birden fazla sayfa eklemek mümkün mü?
Kesinlikle! Belge oluşturma ve kaydetme adımlarını tekrarlayarak birden fazla sayfa oluşturabilirsiniz.
###  Amacı nedir?`ExternalFontCache` class?
`ExternalFontCache` özel yazı tiplerini getirmek ve bunların metin işleme için uygun olmasını sağlamak için kullanılır.
### Ana hatlarıyla belirtilen metne farklı konturlar uygulayabilir miyim?
 Evet, konturun genişliğini ve rengini özelleştirebilirsiniz.`Stroke` sınıf ve`Color` sırasıyla sınıf.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
