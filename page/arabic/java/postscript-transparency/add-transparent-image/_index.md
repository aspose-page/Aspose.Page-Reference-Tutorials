---
date: 2025-12-18
description: تعلم كيفية إنشاء مستند بوستسكريبت باستخدام جافا وإضافة صورة شفافة باستخدام
  Aspose.Page لجافا. يوضح هذا الدليل كيفية إضافة صورة إلى بوستسكريبت بسهولة.
linktitle: Create PostScript Document Java – Add Transparent Image
second_title: Aspose.Page Java API
title: إنشاء مستند PostScript في Java – إضافة صورة شفافة
url: /ar/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة صورة شفافة في Java PostScript

## المقدمة
في عالم Java PostScript، تحسين المظهر البصري للمستندات غالبًا ما يتضمن إضافة صور شفافة. سيوجهك هذا الدليل خلال عملية **create postscript document java** مع دمج الرسومات الشفافة باستخدام مكتبة Aspose.Page for Java القوية. ستتعرف على كيفية إضافة صورة إلى PostScript، وتحديد موقعها بدقة، والتحكم في شفافيتها للحصول على نتائج احترافية.

## إجابات سريعة
- **ماذا يغطي هذا الدليل؟** إضافة صورة PNG شفافة إلى مستند PostScript باستخدام Aspose.Page for Java.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (قم بتحميلها من الموقع الرسمي).  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص مؤقت أو كامل للإنتاج؛ يتوفر نسخة تجريبية مجانية.  
- **هل يمكنني استخدام صيغ صور أخرى؟** نعم، لكن PNG مع قناة ألفا هو الأنسب للشفافية.  
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 10‑15 دقيقة لمثال أساسي.

## ما هو مستند PostScript في Java؟
مستند PostScript هو ملف لغة وصف الصفحات يصف النصوص والرسومات والصور. باستخدام Java، يمكنك إنشاء هذه الملفات برمجيًا، مما يمنحك تحكمًا كاملًا في التخطيط والعرض. الكلمة المفتاحية الأساسية **create postscript document java** تعكس هذه القدرة.

## لماذا نضيف صورًا شفافة؟
تتيح لك الصور الشفافة وضع رسومات فوق المحتوى دون إخفائه، وهو مثالي للعلامات المائية، والشعارات، أو العناصر الزخرفية. الجمع بين الشفافية وتحديد الموقع بدقة ينتج مستندات مصقولة ومتسقة مع العلامة التجارية.

## المتطلبات المسبقة
قبل الغوص في الدليل، تأكد من توفر المتطلبات التالية:
1. Java Development Kit (JDK): تأكد من تثبيت أحدث نسخة من JDK على جهازك.  
2. Aspose.Page for Java: قم بتحميل وتثبيت مكتبة Aspose.Page for Java من [الموقع](https://releases.aspose.com/page/java/).  
3. دليل المستندات: أنشئ مجلدًا على نظامك لتخزين مستندات Java PostScript.  
4. ملف صورة شفافة: جهّز ملف صورة شفافة (مثال: "mask1.png") لاستخدامه في الدليل.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم الضرورية للاستفادة من الوظائف التي توفرها Aspose.Page for Java. إليك كتلة الاستيراد الدقيقة التي ستحتاجها:

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

## كيف تنشئ مستند postscript java بصورة شفافة؟
فيما يلي دليل خطوة بخطوة. كل خطوة تتضمن شرحًا قصيرًا يليه كتلة الكود الأصلية (بدون تعديل).

### الخطوة 1: تعيين لون الخلفية
نبدأ بإنشاء مستند PostScript، وفتح تدفق إخراج، ورسم مستطيل أحمر كمرجع بصري للصورة الشفافة.

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

### الخطوة 2: تحويل الإحداثيات
قبل الرسم، ننقل نقطة الأصل إلى موقع ملائم على الصفحة بحيث تظهر الصورة في المكان المطلوب.

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

### الخطوة 3: إنشاء كائن الصورة
حمّل ملف PNG الذي يحتوي على قناة ألفا. ستُستخدم هذه الصورة لكل من العرض غير الشفاف والشفاف.

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

### الخطوة 4: إضافة صورة غير شفافة
أولاً، نرسم الصورة كصورة RGB عادية. يوضح هذا الفرق عندما نطبق الشفافية لاحقًا.

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

### الخطوة 5: إضافة صورة شفافة
الآن نرسم نفس الصورة بعتامة كاملة (255) أو بأي قيمة بين 0‑255 للتحكم في الشفافية. هنا نستخدم 255 للعتامة الكاملة، لكن يمكنك خفض القيمة للحصول على تأثير شفافية.

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

### الخطوة 6: الحفظ والإغلاق
أخيرًا، نستعيد حالة الرسومات، نغلق الصفحة، ونحفظ المستند على القرص.

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## المشكلات الشائعة والحلول
- **FileNotFoundException** – تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن `mask1.png` موجود.  
- **ImageIO.read returns null** – تأكد من أن ملف PNG بصيغة صالحة وغير معطوب.  
- **الصورة الشفافة تظهر غير شفافة** – عدّل المعامل الثالث في `drawTransparentImage` (0 = شفافية كاملة، 255 = عتامة كاملة).  

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java مع مكتبات Java أخرى؟
نعم، يمكن دمج Aspose.Page for Java بسلاسة مع مكتبات Java أخرى لتعزيز قدرات معالجة المستندات.

### هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page for Java من [هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟
يمكنك الحصول على ترخيص مؤقت من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

### هل هناك منتديات لدعم Aspose.Page for Java؟
نعم، زر [منتدى Aspose.Page for Java](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع والنقاشات.

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page for Java؟
راجع الوثائق الشاملة في [documentation](https://reference.aspose.com/page/java/) للحصول على معلومات مفصلة حول Aspose.Page for Java.

## الخاتمة
تهانينا! لقد تعلمت بنجاح كيفية **create postscript document java** وإضافة صور شفافة باستخدام Aspose.Page for Java. جرّب صورًا مختلفة، مستويات عتامة مختلفة، ومواقع متنوعة لإنشاء مستندات بصرية مذهلة تلبي احتياجات علامتك التجارية.

---

**آخر تحديث:** 2025-12-18  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}