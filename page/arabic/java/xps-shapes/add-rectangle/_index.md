---
date: 2026-04-24
description: تعلم كيفية تعيين لون المستطيل وإضافة مستطيل في Java XPS باستخدام Aspose.Page.
  يغطي هذا الدليل إضافة مستطيل في Java وتغيير حد المستطيل.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: إضافة مستطيل في Java XPS
second_title: Aspose.Page Java API
title: تعيين لون المستطيل وإضافة مستطيل في Java XPS
url: /ar/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين لون المستطيل وإضافة مستطيل في Java XPS

## مقدمة
في هذا الدليل، ستتعلم كيفية **تعيين لون المستطيل** و**إضافة مستطيل** في Java XPS باستخدام مكتبة Aspose.Page. سواءً كنت تحتاج إلى رسم أشكال بسيطة لتقرير أو إنشاء رسومات متجهة معقدة، فإن إتقان تنسيق المستطيل يمنحك تحكمًا دقيقًا في مستندات XPS الخاصة بك.  

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني تغيير حد المستطيل؟** نعم، باستخدام `setStroke` و `setStrokeThickness`  
- **هل يتم دعم ملف تعريف لون CMYK؟** بالتأكيد – يمكنك تحميل ملفات ICC كما هو موضح  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم ترخيص تجاري للاستخدام غير التجريبي  
- **كم من الوقت تستغرق التنفيذ؟** عادةً أقل من 10 دقيقة لمستطيل أساسي

## ما هو **set rectangle color**؟
تعيين لون المستطيل يعني تحديد لون التعبئة أو الحد الذي سيظهر به الشكل في مستند XPS النهائي. مع Aspose.Page يمكنك استخدام RGB أو CMYK أو حتى ملفات تعريف ألوان ICC مخصصة لتحقيق مطابقة ألوان دقيقة.

## لماذا تستخدم Aspose.Page لـ **add rectangle java** و **change rectangle stroke**؟
- **Full‑featured API** – يدعم كل من الألوان الصلبة والتدرجات.  
- **Cross‑platform** – يعمل على أي بيئة تشغيل Java دون تبعيات أصلية.  
- **Rich geometry support** – إنشاء مسارات معقدة، تطبيق التحويلات، وإدارة سمك الحد بسهولة.  

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود:

- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page مثبتة. إذا لم تكن كذلك، قم بتحميلها من [وثائق Aspose.Page Java](https://reference.aspose.com/page/java/).  
- بيئة تطوير Java تعمل (IDE، JDK، إلخ).  

## استيراد الحزم
للبدء، استورد الحزم اللازمة إلى مشروع Java الخاص بك. تأكد من إضافة مكتبة Aspose.Page إلى مسار الفئة (classpath). إليك مثالًا أساسيًا:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

الآن، لنفصل المثال المقدم إلى خطوات متعددة لـ **إضافة مستطيل** و**تعيين لونه** في Java XPS.

## الخطوة 1: تعيين دليل المستند
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
استبدل `"Your Document Directory"` بالمسار المطلق حيث تريد قراءة/كتابة ملفات XPS.

## الخطوة 2: إنشاء مستند XPS جديد
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
هذا السطر يهيئ مستند XPS جديد سيحتوي على أشكالنا.

## الخطوة 3: إضافة مستطيل بخط صلب بلون CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
هذه الخطوة تضيف **مستطيلًا بحد** بلون صلب CMYK. طريقة `setStroke` تحدد لون حدود المستطيل، بينما `setStrokeThickness` تتحكم في عرض الخط — مثالي لـ **تغيير حد المستطيل**.

### نصحة احترافية:
إذا كنت تفضل لون RGB، استبدل استدعاء `createColor` بـ `doc.createColor(0, 0, 255)` للحصول على تعبئة زرقاء صلبة.

## الخطوة 4: حفظ مستند XPS الناتج
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
أخيرًا، احفظ مستند XPS على القرص. الملف `AddRectangle_out.xps` الآن يحتوي على مستطيل تم تعريف لونه وحده.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|----------|
| **المستطيل غير مرئي** | هندسة مسار غير صحيحة أو سمك الحد مضبوط على 0 | تحقق من سلسلة المسار (`"M 20,10 L 220,10 220,100 20,100 Z"`) وتأكد من أن `setStrokeThickness` أكبر من 0. |
| **لون خاطئ** | استخدام ملف ICC لا يتطابق مع مساحة اللون المطلوبة | استخدم `doc.createColor(r, g, b)` لـ RGB أو تحقق مرة أخرى من مسار ملف ICC. |
| **الملف غير محفوظ** | `dataDir` يشير إلى مجلد غير موجود أو يفتقر إلى صلاحية الكتابة | أنشئ المجلد مسبقًا أو اختر موقعًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س:** *هل يمكنني إضافة مستطيلات متعددة في مستند XPS واحد؟*  
**ج:** نعم. ببساطة كرر خطوات إنشاء الهندسة وتنسيقها لكل مستطيل تحتاجه.

**س:** *كيف يمكنني تغيير لون تعبئة المستطيل بدلاً من الحد؟*  
**ج:** استخدم `path.setFill(...)` بفرشاة لون صلبة، مشابهًا لكيفية استخدام `setStroke`.

**س:** *هل Aspose.Page مناسب لتعاملات مستندات XPS المعقدة؟*  
**ج:** بالطبع. المكتبة تدعم ميزات متقدمة مثل التدرجات، التحويلات، والخطوط المدمجة.

**س:** *أين يمكنني العثور على أمثلة إضافية ودعم المجتمع؟*  
**ج:** استكشف [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لمزيد من عينات الشيفرة ومساعدة الأقران.

**س:** *هل يمكنني تجربة Aspose.Page قبل الشراء؟*  
**ج:** نعم، يمكنك تجربة [نسخة تجريبية مجانية](https://releases.aspose.com/) لتقييم قدرات الـ API.

---

**آخر تحديث:** 2026-04-24  
**تم الاختبار مع:** Aspose.Page for Java 24.12  
**المؤلف:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}