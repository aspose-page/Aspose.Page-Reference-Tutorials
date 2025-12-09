---
date: 2025-12-02
description: تعلم كيفية تغيير حجم ملفات EPS في Java بسهولة باستخدام Aspose.Page. يوضح
  لك هذا الدليل خطوة بخطوة كيفية تغيير حجم EPS باستخدام النقاط أو البوصات أو المليمترات
  أو النسب المئوية.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: كيفية تغيير حجم ملفات EPS في Java باستخدام Aspose.Page
url: /ar/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تغيير حجم ملفات EPS في Java باستخدام Aspose.Page

## المقدمة
إذا كنت تبحث عن طريقة موثوقة **كيفية تغيير حجم ملفات EPS** برمجياً، فقد وصلت إلى المكان المناسب. في هذا الدرس سنستعرض عملية تغيير حجم صور EPS في Java باستخدام مكتبة Aspose.Page. سواء كنت تحتاج إلى مضاعفة الحجم، أو تقليصه إلى قياس محدد، أو العمل بالنسب المئوية، فإن الخطوات أدناه تمنحك السيطرة الكاملة على أبعاد الناتج.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني تغيير الحجم باستخدام النقاط أو البوصات أو المليمترات؟** نعم – الـ API يدعم جميع الوحدات الثلاث بالإضافة إلى النسب المئوية.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ الترخيص مطلوب للإنتاج.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أحدث.  
- **هل الشيفرة آمنة من حيث الخيوط (thread‑safe)؟** كل كائن `PsDocument` معزول، لذا يمكنك معالجة الملفات بالتوازي.

## المتطلبات المسبقة
قبل أن نغوص في الشيفرة، تأكد من أن لديك ما يلي:

- مجموعة تطوير Java (JDK) مثبتة على جهازك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها **[هنا](https://releases.aspose.com/page/java/)**.  
- فهم أساسي لبرمجة Java.  

## استيراد الحزم
في مشروع Java الخاص بك، أدرج الاستيرادات المطلوبة حتى تتمكن من العمل مع كائنات Aspose.Page وتدفقات الإدخال/الإخراج القياسية.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## كيفية تغيير حجم EPS باستخدام النقاط
فيما يلي مثال كامل خطوة بخطوة يضاعف حجم ملف EPS باستخدام النقاط كوحدة قياس.

### الخطوة 1: إعداد تدفق الإدخال
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### الخطوة 2: تهيئة كائن `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### الخطوة 3: استخراج الحجم الحالي لصورة EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### الخطوة 4: إنشاء تدفق إخراج للملف المعاد تحجيمه
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### الخطوة 5: تغيير الحجم وحفظ EPS باستخدام النقاط
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## كيفية تغيير حجم EPS باستخدام البوصات
نفس نمط الخطوات الخمس ينطبق؛ فقط استبدل `Units.Points` بـ `Units.Inches` واضبط عامل التحجيم حسب الحاجة.

## كيفية تغيير حجم EPS باستخدام المليمترات
مرة أخرى، اتبع نفس الخطوات، مع استبدال الوحدة بـ `Units.Millimeters`. هذا مفيد عندما تحتاج إلى أبعاد مترية لعمليات الطباعة.

## كيفية تغيير حجم EPS باستخدام النسب المئوية
للتكبير/التصغير بناءً على النسبة المئوية، احتفظ بالوحدة كـ `Units.Percent`. اضرب العرض والارتفاع الأصليين في النسبة المطلوبة (مثلاً `0.5` لتقليل بنسبة 50 %).

## الأخطاء الشائعة والنصائح
- **دائمًا أغلق التدفقات** – في الشيفرة الإنتاجية، احwrap التدفقات باستخدام try‑with‑resources لتجنب حجز الملفات.  
- **حافظ على نسبة الأبعاد** – اضرب كل من العرض والارتفاع بنفس العامل ما لم تكن تريد تشويهًا مقصودًا.  
- **تحقق من DPI** – تغيير الحجم لا يغير DPI؛ إذا كنت تحتاج إلى DPI مختلف، عدّلها بشكل منفصل بعد تغيير الحجم.

## الخلاصة
أنت الآن تعرف **كيفية تغيير حجم ملفات EPS** في Java باستخدام Aspose.Page، سواء كنت تفضل النقاط أو البوصات أو المليمترات أو النسب المئوية. هذه المرونة تتيح لك دمج معالجة EPS في خطوط الأنابيب الآلية، أو الأدوات المكتبية، أو الخدمات على جانب الخادم.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذه المكتبة لتنسيقات صور أخرى؟**  
ج: لا، Aspose.Page متخصصة في ملفات PostScript و EPS فقط.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك استكشاف النسخة التجريبية **[هنا](https://releases.aspose.com/)**.

**س: أين يمكنني العثور على مساعدة إضافية ومناقشات؟**  
ج: زر **[منتدى Aspose.Page](https://forum.aspose.com/c/page/39)** للحصول على دعم المجتمع.

**س: كيف يمكنني الحصول على ترخيص مؤقت؟**  
ج: يمكنك الحصول على ترخيص مؤقت **[هنا](https://purchase.aspose.com/temporary-license/)**.

**س: هل هناك مشاريع مثال متاحة؟**  
ج: نعم، راجع الوثائق **[هنا](https://reference.aspose.com/page/java/)**.

---

**آخر تحديث:** 2025-12-02  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}