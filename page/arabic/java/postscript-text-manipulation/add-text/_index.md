---
date: 2025-12-14
description: تعلم كيفية ضبط لون النص في جافا باستخدام Aspose.Page for Java، وإضافة
  نص إلى PostScript، وتطبيق خط النص لتنسيق مستند غني.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: تعيين لون النص في جافا باستخدام Aspose.Page – دليل معالجة النص
url: /ar/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين لون النص في Java باستخدام Aspose.Page – دليل معالجة النصوص

## المقدمة
مرحبًا بكم في دليلنا خطوة بخطوة حول **set text color java** أثناء العمل مع ملفات PostScript باستخدام Aspose.Page for Java. Aspose.Page for Java هي مكتبة قوية تتيح للمطورين إنشاء و **generate postscript file** مستندات، ومعالجة الخطوط، وتنسيق النص بدقة. في هذا البرنامج التعليمي ستتعلم كيفية إضافة نص، تغيير لونه، تعديل حجمه، وحتى **apply stroke text** للحصول على مظهر مصقول.

## إجابات سريعة
- **ما المكتبة التي تسمح لي بتعيين لون النص في Java؟** Aspose.Page for Java.
- **هل يمكنني استخدام الخطوط النظامية والخطوط المخصصة؟** نعم، كلاهما مدعومان.
- **كيف يمكنني تغيير حجم النص؟** عن طريق تحديد حجم الخط عند إنشاء `Font` أو `DrFont`.
- **هل من الممكن تحديد النص وتعبئته معًا؟** بالتأكيد – استخدم `fillAndStrokeText`.
- **ما هو تنسيق الإخراج الذي ينتجه هذا البرنامج التعليمي؟** مستند PostScript (`.ps`).

## ما هو “set text color java”؟
تعيين لون النص في Java يعني تعريف كائن `Color` الذي يستخدمه محرك العرض (هنا، Aspose.Page) عند رسم الأحرف على الصفحة. هذه العملية أساسية لإنشاء مستندات بصرية متميزة، خاصةً عند إنشاء **postscript documents** برمجيًا.

## لماذا نستخدم Aspose.Page for Java؟
- **تحكم كامل** في إنشاء PostScript دون الحاجة إلى مفسر PostScript أصلي.
- **دعم لكل من الخطوط النظامية والخارجية**، مما يتيح لك تضمين أي طباعة تحتاجها.
- **واجهة برمجة تطبيقات سهلة** لتعبئة، وتحديد، و **fill and stroke text**، مما يمنحك مرونة في التنسيق.
- **توافق متعدد المنصات** – اكتب مرة واحدة، وشغّل في أي مكان يعمل فيه Java.

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك:

- معرفة أساسية ببرمجة Java.
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها من [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- الخطوط الضرورية متوفرة في المجلد المحدد. تفاصيل إضافية في [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم الضرورية لـ Aspose.Page for Java:

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

## الخطوة 1: إعداد المستند
أولاً، نقوم بإنشاء **PostScript document** جديد وتكوين خيارات الإخراج.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## كيفية تعيين لون النص في Java باستخدام الخط النظامي
الآن نوضح **set text color java** باستخدام خط موفر من النظام.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **نصيحة:** طريقة `fillText` تستخدم اللون الحالي تلقائيًا إذا لم تمرر معامل `Color`، والذي يكون افتراضيًا أسود.

## استخدام خط مخصص وتغيير حجم النص
يمكنك أيضًا **change text size** واستخدام خط مخصص مخزن في مجلد الخطوط الخاص بك.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## تحديد (Stroke) النص – تطبيق Stroke Text
تحديد النص يمنحه حافة واضحة. هنا نـ **apply stroke text** باستخدام `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## تحديد النص باستخدام خط مخصص
نفس التقنية تعمل مع الخطوط المخصصة.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## الخطوة 6: حفظ المستند
أخيرًا، أغلق الصفحة واكتب الملف إلى القرص.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **الخط غير موجود** | تأكد من وضع ملف الخط في `necessary_fonts` وإضافة مسار المجلد بشكل صحيح عبر `options.setAdditionalFontsFolders`. |
| **اللون غير مطبق** | تحقق من أنك تستدعي النسخة المتعددة من `fillText` أو `outlineText` التي تتضمن معامل `Color`. |
| **الحد يبدو رفيعًا جدًا** | زد عرض `BasicStroke` (مثلاً، `new BasicStroke(3)`). |
| **المستند لا يفتح** | تأكد من حفظ ملف `.ps` المُولد بالامتداد الصحيح وأن عارضك يدعم PostScript. |

## الأسئلة المتكررة

**س:** هل يمكنني استخدام خطوط مخصصة خاصة بي مع Aspose.Page for Java؟  
ج: نعم، يمكنك استخدام الخطوط المخصصة عن طريق تحديد اسم الخط والحجم في فئة `DrFont`.

**س:** كيف يمكنني تغيير لون النص؟  
ج: يمكنك تعيين اللون المطلوب باستخدام فئة `Color` عند تعبئة أو تحديد النص.

**س:** هل من الممكن إضافة صفحات متعددة إلى مستند PostScript؟  
ج: بالتأكيد! يمكنك إنشاء صفحات متعددة عن طريق تكرار خطوات إنشاء المستند وحفظه.

**س:** ما هو هدف فئة `ExternalFontCache`؟  
ج: تُستخدم فئة `ExternalFontCache` لجلب الخطوط المخصصة، مما يضمن توفرها لمعالجة النص.

**س:** هل يمكنني تطبيق حدود مختلفة على النص المحدد؟  
ج: نعم، يمكنك تخصيص عرض ولون الحد باستخدام فئة `Stroke` وفئة `Color` على التوالي.

## الخاتمة
تهانينا! الآن تعرف كيف **set text color java**، وتغيير أحجام الخطوط، و **apply stroke text**، و **create postscript document** باستخدام Aspose.Page for Java. جرّب خطوطًا وألوانًا وأنماط تحديد مختلفة لإنتاج مخرجات PostScript ذات مظهر احترافي.

---

**آخر تحديث:** 2025-12-14  
**تم الاختبار مع:** Aspose.Page for Java 23.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}