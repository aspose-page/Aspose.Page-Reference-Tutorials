---
date: 2025-12-28
description: تعرّف على كيفية إنشاء مستند XPS في جافا باستخدام Aspose.Page وإضافة صورة
  متكررة بسهولة من خلال هذا الدليل خطوة بخطوة.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: كيفية إنشاء مستند XPS بصورة مبلطة في جافا
url: /ar/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند XPS وإضافة صورة متكررة في Java

## المقدمة
في تطوير Java الحديث، القدرة على **إنشاء ملفات مستند XPS** برمجياً تُعد مهارة قيمة، خاصة عندما تحتاج إلى إثرائها بالرسومات مثل الصور المتكررة. تجعل مكتبة Aspose.Page for Java هذه العملية بسيطة، مما يسمح لك بالتركيز على التصميم البصري بدلاً من التعامل منخفض المستوى مع الملفات. في هذا الدرس ستتعلم بالضبط كيفية إنشاء مستند XPS، **إضافة صورة متكررة**، وحفظ النتيجة، كل ذلك مع أمثلة شفرة واضحة خطوة بخطوة.

## إجابات سريعة
- **ماذا تفعل Aspose.Page؟** توفر واجهة برمجة تطبيقات عالية المستوى لإنشاء ومعالجة مستندات XPS في Java.  
- **هل يمكنني تكرار صورة؟** نعم – استخدم `XpsImageBrush` مع `XpsTileMode.Tile`.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت أو تجاري للاستخدام في الإنتاج.  
- **ما نسخة Java المدعومة؟** أي JDK 8+ متوافق.  
- **كم تستغرق عملية التنفيذ؟** تقريباً 10–15 دقيقة لسيناريو الصورة المتكررة الأساسي.

## ما هو “إنشاء مستند XPS”؟
ملف XPS (XML Paper Specification) هو تنسيق مستند ثابت التخطيط مشابه لـ PDF. يتيح لك إنشاء مستند XPS برمجياً توليد ملفات قابلة للطباعة ومستقلة عن الجهاز مباشرةً من شفرة Java.

## لماذا نضيف صورة متكررة؟
تكرار الصورة يعيد رسم الرسمة عبر مساحة محددة، وهو مثالي للخلفيات أو العلامات المائية أو تعبئة الأنماط. باستخدام `XpsTileMode.Tile` في Aspose.Page يمكنك تحقيق ذلك ببضع أسطر من الشفرة فقط.

## المتطلبات المسبقة
قبل الغوص في الموضوع، تأكد من وجود ما يلي:

1. **مجموعة تطوير Java (JDK)** – JDK 8 أو أحدث مثبتة.  
2. **Aspose.Page for Java** – حمّلها من الـ[موقع الإلكتروني](https://releases.aspose.com/page/java/).  
3. **دليل قابل للكتابة** – حيث سيتم حفظ ملف XPS المُنشأ.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الفئات اللازمة:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد المشروع
أضف ملفات JAR الخاصة بـ Aspose.Page إلى مسار الفئة (classpath) لمشروعك وتأكد من أن عبارات الاستيراد تُجمع بدون أخطاء.

### الخطوة 2: إنشاء مستند XPS
أنشئ كائن `XpsDocument` جديد. هذا هو الحاوية الأساسية التي ستحتوي جميع الصفحات والمسارات والموارد.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### الخطوة 3: تحديد مسار الصورة المتكررة
ضع الصورة التي تريد تكرارها (مثلاً `R08LN_NN.jpg`) داخل الدليل المشار إليه بـ `dataDir`. ستُستخدم الصورة كنمط للفرشاة.

### الخطوة 4: إضافة صورة متكررة
أنشئ مسارًا مستطيلًا واملأه بـ `XpsImageBrush`. من خلال ضبط وضعية التكرار إلى `Tile`، ستتكرر الصورة عبر المستطيل.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### الخطوة 5: حفظ المستند
احفظ ملف XPS على القرص. سيحتوي ملف الإخراج على الصورة المتكررة التي عرّفتها للتو.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

كرر هذه الخطوات كلما احتجت إلى **إضافة صورة متكررة** إلى صفحات أو أشكال أخرى داخل نفس مستند XPS.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| الصورة لا تظهر | تحقق من صحة مسار الملف (`dataDir + "R08LN_NN.jpg"`) وأن الصورة قابلة للوصول. |
| نمط التكرار يبدو مشوّهًا | اضبط قيم `Rectangle2D` المصدر والوجهة للتحكم في حجم البلاطة. |
| الشفافية لا تؤثر | تأكد من ضبط شفافية الفرشاة **بعد** تكوين وضعية التكرار. |

## الأسئلة المتكررة

### هل Aspose.Page متوافق مع جميع إصدارات Java؟
تم تصميم Aspose.Page للعمل مع إصدارات Java المختلفة. تحقق من التوافق عبر الوثائق [هنا](https://reference.aspose.com/page/java/).

### هل يمكنني استخدام Aspose.Page في مشاريع تجارية؟
نعم، توفر Aspose.Page تراخيص تجارية. يمكنك شراؤها [هنا](https://purchase.aspose.com/buy).

### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، استكشف ميزات Aspose.Page عبر نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على دعم المجتمع والنقاشات؟
تفاعل مع مجتمع Aspose.Page على الـ[منتدى](https://forum.aspose.com/c/page/39).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟
احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2025-12-28  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (الأحدث)  
**المؤلف:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
