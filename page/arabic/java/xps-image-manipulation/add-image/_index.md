---
date: 2025-12-28
description: تعلم كيفية إضافة صورة إلى مستندات XPS في جافا باستخدام Aspose.Page. يوضح
  لك هذا الدليل خطوة بخطوة كيفية إضافة الصور بسهولة وتعزيز معالجة المستندات الخاصة
  بك.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: كيفية إضافة صورة إلى مستندات XPS في جافا – دليل بسيط مع Aspose.Page
url: /ar/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة صورة إلى مستندات Java XPS باستخدام Aspose.Page

إضافة الصور إلى ملفات XPS هي متطلب شائع لمطوري Java الذين يحتاجون إلى إثراء التقارير أو الفواتير أو أي مستند بصري. في هذا البرنامج التعليمي ستكتشف **كيفية إضافة صورة** إلى مستند XPS باستخدام مكتبة Aspose.Page القوية لـ Java. سنستعرض كل خطوة، نشرح لماذا كل سطر مهم، ونقدم لك نصائح لتجنب المشكلات الشائعة.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني إضافة صور متعددة؟** نعم – كرّر خطوات إضافة الصورة لكل صورة  
- **ما صيغ الصور المدعومة؟** TIFF, JPEG, PNG, GIF (وغيرها المدعومة من .NET)  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج  
- **الوقت المتوقع للتنفيذ؟** حوالي 10‑15 دقيقة لإدراج صورة أساسية

## المقدمة
إضافة الصور إلى مستندات XPS هي متطلب شائع في العديد من تطبيقات Java، من توليد التقارير إلى معالجة المستندات. تُبسّط Aspose.Page for Java هذه المهمة، حيث توفر طرقًا فعّالة لدمج الصور بسلاسة في ملفات XPS الخاصة بك. في هذا البرنامج التعليمي، سنوضح كيفية إضافة صورة إلى مستند XPS باستخدام Aspose.Page for Java.

## المتطلبات المسبقة
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:
1. **Aspose.Page for Java Library** – قم بتحميل وتثبيت مكتبة Aspose.Page for Java من [الموقع الإلكتروني](https://releases.aspose.com/page/java/).  
2. **بيئة تطوير Java** – تأكد من إعداد بيئة تطوير Java على جهازك.

الآن، لننتقل إلى الخطوات التالية.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم اللازمة من Aspose.Page for Java للوصول إلى الفئات والطرق المطلوبة.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## الخطوة 1: إعداد مسار المستند
حدد المسار إلى دليل المستندات حيث سيتم تخزين ملف XPS وملفات الصور.

```java
String dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء مستند XPS جديد
قم بتهيئة مستند XPS جديد باستخدام مقتطف الشيفرة التالي:

```java
XpsDocument doc = new XpsDocument();
```

## الخطوة 3: إضافة صورة إلى مستند XPS
لإضافة صورة، أنشئ مسارًا في مستند XPS، واضبط فرشاة الصورة باستخدام ملف الصورة والإحداثيات المقدمة.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## الخطوة 4: حفظ مستند XPS الناتج
احفظ مستند XPS المعدل إلى الدليل المحدد لديك.

```java
doc.save(dataDir + "AddImage_out.xps");
```

كرر هذه الخطوات لإضافة المزيد من الصور أو تخصيص الصور الحالية وفقًا لمتطلبات مشروعك.

## الخاتمة
تهانينا! لقد تعلمت بنجاح **كيفية إضافة صورة** إلى مستند XPS باستخدام Aspose.Page for Java. هذه المهارة لا تقدر بثمن لتعزيز الجاذبية البصرية لتطبيقات Java ومستنداتك.

### الأسئلة المتكررة
### هل يمكنني إضافة صور متعددة إلى نفس مستند XPS باستخدام Aspose.Page for Java؟
نعم، يمكنك إضافة صور متعددة عن طريق تكرار الخطوات الموضحة في هذا البرنامج التعليمي لكل صورة.

### ما صيغ الصور التي تدعمها Aspose.Page for Java؟
تدعم Aspose.Page for Java صيغ صور متعددة، بما في ذلك TIFF و JPEG و PNG و GIF.

### هل تتوفر نسخة تجريبية من Aspose.Page for Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page for Java من [هذا الرابط](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟
يمكنك الحصول على ترخيص مؤقت من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

### أين يمكنني العثور على دعم إضافي أو مناقشة المشكلات المتعلقة بـ Aspose.Page for Java؟
قم بزيارة [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على المساعدة، مشاركة التجارب، والتواصل مع مجتمع Aspose.Page.

## نصائح إضافية ومخاطر شائعة
- **دقة هندسة المسار** – تأكد من أن سلسلة المسار بنمط SVG تتطابق مع أبعاد صورتك؛ وإلا قد تظهر الصورة مشوهة أو مقطوعة.  
- **تحجيم فرشاة الصورة** – طريقة `createImageBrush` تأخذ مستطيلات المصدر والوجهة؛ تعديل هذه القيم يتيح لك التحكم بدقة في الموضع والتحجيم.  
- **تفعيل الترخيص** – إذا شغلت الشيفرة بدون ترخيص صالح، سيضيف Aspose علامة مائية إلى ملف XPS المُولد.

---

**آخر تحديث:** 2025-12-28  
**تم الاختبار مع:** Aspose.Page for Java 23.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}