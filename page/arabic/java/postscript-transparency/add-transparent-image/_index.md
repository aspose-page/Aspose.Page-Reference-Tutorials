---
date: 2026-03-05
description: تعلم كيفية تعيين لون الخلفية في Java وإضافة صور شفافة إلى PostScript
  باستخدام Aspose.Page لـ Java. قم بتحويل PNG إلى PostScript بسهولة.
linktitle: Add Transparent Image in Java PostScript
second_title: Aspose.Page Java API
title: 'تعيين لون الخلفية في جافا: إضافة صورة شفافة إلى الفوتوشوب'
url: /ar/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين لون الخلفية في Java: إضافة صورة شفافة إلى PS

## Introduction
إذا كنت بحاجة إلى **set background color java** أثناء العمل مع Java PostScript، فإن إضافة صور شفافة يمكن أن تعطي مستنداتك مظهرًا مصقولًا واحترافيًا. في هذا الدرس سنرشدك خلال العملية الكاملة لتعيين خلفية ملونة، تحويل PNG إلى PostScript، ورسم كل من الصور غير الشفافة والشفافة باستخدام مكتبة Aspose.Page for Java. في النهاية ستتمكن من **add image to postscript** مع التحكم الكامل في الشفافية.

## Quick Answers
- **What library handles transparency in Java PostScript?** Aspose.Page for Java.  
- **Can I set a background color before drawing images?** Yes – use `document.setPaint()` and `fill()`.  
- **How do I convert PNG to PostScript?** Load the PNG with `ImageIO.read()` and draw it with `drawImage` or `drawTransparentImage`.  
- **Is opacity supported for images?** Use `drawTransparentImage` to specify an opacity value (0‑255).  
- **Do I need a license for production use?** A valid Aspose.Page for Java license is required; a free trial is available.

## Prerequisites
قبل البدء، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – أحدث نسخة مثبتة.  
2. **Aspose.Page for Java** – حمّلها من [الموقع الإلكتروني](https://releases.aspose.com/page/java/).  
3. **Document Directory** – مجلد ستكتب فيه ملفات PostScript.  
4. **Translucent Image File** – مثل `mask1.png`، والتي سنستخدمها لتوضيح الشفافية.

## Import Packages
في مشروع Java الخاص بك، استورد الفئات الضرورية. يبقى هذا القسم دون تغيير:

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Background Color Java
هنا نقوم بإنشاء المستند، اختيار حجم A4، وتعبئة مستطيل أحمر لتوضيح تباين الخلفية.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

## Step 2: Translate Coordinates
نحوّز مؤشر الرسم إلى موقع مناسب على الصفحة قبل وضع الصور.

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

## Step 3: Create Image Object
حمّل ملف PNG (خطوة **convert png to postscript**).

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

## Step 4: Add Opaque Image
ارسم الصورة بشكل عادي—هذا يوضح **add image to postscript** بدون شفافية.

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

## Step 5: Add Transparent Image (draw image with opacity)
الآن نستخدم `drawTransparentImage` لعرض نفس PNG بشفافية كاملة (255). عدّل القيمة للتحكم في مستوى الشفافية.

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

## Step 6: Save and Close
أكمل المستند وأفرغ الموارد.

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Why This Matters
تعيين لون الخلفية باستخدام Java يمنحك لوحة يمكنها إبراز الرسومات المتراكبة. الجمع بين ذلك و**draw image with opacity** يتيح لك إنشاء علامات مائية، شعارات، أو نماذج واجهات مستخدم مباشرة في PostScript دون الحاجة إلى أدوات تحرير خارجية.

## Common Issues & Tips
- **Image not appearing transparent:** تحقق من أن ملف PNG يحتوي فعليًا على قناة ألفا.  
- **Incorrect colors:** تذكر أن مستطيل الخلفية يُرسم قبل الصورة؛ غيّر قيم `Color` لتتناسب مع التصميم الخاص بك.  
- **Performance:** للوثائق الكبيرة، أعد استخدام كائن **AffineTransform** واحد لتقليل عبء إنشاء الكائنات.

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java with other Java libraries?**  
A: نعم، يمكن دمج Aspose.Page for Java بسلاسة مع مكتبات Java أخرى لتعزيز قدرات معالجة المستندات.

**Q: Is a free trial available for Aspose.Page for Java?**  
A: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page for Java عبر [هنا](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: يمكنك الحصول على ترخيص مؤقت من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

**Q: Are there any forums for Aspose.Page for Java support?**  
A: نعم، زر [منتدى Aspose.Page for Java](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع والنقاشات.

**Q: Where can I find the documentation for Aspose.Page for Java?**  
A: راجع [الوثائق الشاملة](https://reference.aspose.com/page/java/) للحصول على معلومات مفصلة حول Aspose.Page for Java.

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}