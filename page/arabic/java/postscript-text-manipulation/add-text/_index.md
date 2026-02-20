---
date: 2026-02-20
description: تعلم كيفية تعيين لون النص في جافا باستخدام Aspose.Page for Java، وتغيير
  حجم الخط في جافا، وإنشاء ملف بوستسكريبت، وتعبئة النص وتحديد حدوده، واستخدام خطوط
  مخصصة في جافا أثناء إنشاء مستند بوستسكريبت.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: تعيين لون النص في جافا باستخدام Aspose.Page – دليل تعديل النص
url: /ar/java/postscript-text-manipulation/add-text/
weight: 10
---

.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين لون النص في Java باستخدام Aspose.Page – دليل معالجة النص

## Introduction
مرحبًا بكم في دليلنا خطوة بخطوة حول **set text color java** أثناء العمل مع ملفات PostScript باستخدام Aspose.Page for Java. Aspose.Page for Java هي مكتبة قوية تتيح للمطورين **create postscript document** ملفات، وت manipulation fonts، وتنسيق النص بدقة. في هذا البرنامج التعليمي ستتعلم كيفية إضافة نص، تغيير لونه، **change font size java**، وحتى **apply fill and stroke text** للحصول على مظهر مصقول.

## Quick Answers
- **ما المكتبة التي تسمح لي بتعيين لون النص في Java؟** Aspose.Page for Java.  
- **هل يمكنني استخدام الخطوط النظامية والخطوط المخصصة؟** نعم، كلاهما مدعومان، ويمكنك **use custom fonts java** بسهولة.  
- **كيف يمكنني تغيير حجم النص؟** عن طريق تحديد حجم الخط عند إنشاء `Font` أو `DrFont`.  
- **هل من الممكن تحديد وتعبئة النص معًا؟** بالتأكيد – استخدم `fillAndStrokeText`.  
- **ما هو تنسيق الإخراج الذي ينتجه هذا البرنامج التعليمي؟** مستند PostScript (`.ps`)، والذي يمكنك **generate postscript file** برمجيًا.

## What is “set text color java”?
تعيين لون النص في Java يعني تعريف كائن `Color` الذي يستخدمه محرك العرض (هنا، Aspose.Page) عند رسم الأحرف على الصفحة. هذه العملية أساسية لإنشاء مستندات بصرية متميزة، خاصة عندما تحتاج إلى **generate postscript file** برمجيًا.

## Why use Aspose.Page for Java?
- **تحكم كامل** في إنشاء PostScript دون الحاجة إلى مفسر أصلي.  
- **دعم للخطوط النظامية والخارجية**، مما يتيح لك تضمين أي طباعة تحتاجها.  
- **واجهة برمجة تطبيقات سهلة** لتعبئة، وتحديد، و**fill and stroke text**، مما يمنحك مرونة في التنسيق.  
- **توافق عبر الأنظمة** – اكتب مرة واحدة، شغّل في أي مكان يعمل فيه Java.  

## Prerequisites
قبل الغوص، تأكد من أن لديك:

- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها من [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).  
- الخطوط الضرورية متوفرة في المجلد المحدد. تفاصيل إضافية في [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Import Packages
في مشروع Java الخاص بك، استورد الحزم اللازمة لـ Aspose.Page for Java:

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

## Step 1: Set Up the Document
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

## How to Set Text Color Java Using System Font
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

## Using Custom Font and Changing Text Size
يمكنك أيضًا **change font size java** واستخدام خط مخصص مخزن في مجلد الخطوط الخاص بك.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
إعطاء النص حدودًا يمنحه حافة واضحة. هنا نـ **apply stroke text** باستخدام `BasicStroke`.

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

## Outlining Text with Custom Font
نفس التقنية تعمل مع الخطوط المخصصة.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
أخيرًا، أغلق الصفحة واكتب الملف إلى القرص.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why This Matters
القدرة على **set text color java** ودمج التعبئة مع الحد يمنحك تحكمًا فنيًا كاملًا في الناتج النهائي لـ PostScript. سواء كنت تولد فواتير، شهادات، أو رسومات مخصصة، فإن القدرة على **create postscript document** ملفات بتنسيق دقيق تقلل الحاجة إلى المعالجة اللاحقة في برامج تحرير الرسوم.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Font not found** | تأكد من وضع ملف الخط في `necessary_fonts` وإضافة مسار المجلد بشكل صحيح عبر `options.setAdditionalFontsFolders`. |
| **Color not applied** | تحقق من أنك تستدعي النسخة المتعددة من `fillText` أو `outlineText` التي تتضمن معامل `Color`. |
| **Stroke appears too thin** | زد عرض `BasicStroke` (مثلاً، `new BasicStroke(3)`). |
| **Document not opening** | تأكد من حفظ ملف `.ps` المُولد بالامتداد الصحيح وأن عارضك يدعم PostScript. |

## Frequently Asked Questions

**س:** هل يمكنني استخدام خطوط مخصصة خاصة بي مع Aspose.Page for Java؟  
**ج:** نعم، يمكنك **use custom fonts java** عن طريق تحديد اسم الخط وحجمه في فئة `DrFont`.

**س:** كيف يمكنني تغيير لون النص؟  
**ج:** يمكنك تعيين اللون المطلوب باستخدام فئة `Color` عند تعبئة النص أو تحديده.

**س:** هل من الممكن إضافة صفحات متعددة إلى مستند PostScript؟  
**ج:** بالتأكيد! يمكنك إنشاء صفحات متعددة عن طريق تكرار خطوات إنشاء المستند وحفظه.

**س:** ما هو هدف فئة `ExternalFontCache`؟  
**ج:** تُستخدم `ExternalFontCache` لجلب الخطوط المخصصة، مما يضمن توفرها لمعالجة النص.

**س:** هل يمكنني تطبيق حدود مختلفة على النص المحدد؟  
**ج:** نعم، يمكنك تخصيص عرض ولون الحد باستخدام فئة `Stroke` وفئة `Color` على التوالي.

## Conclusion
تهانينا! الآن تعرف كيف **set text color java**، **change font size java**، **apply fill and stroke text**، و**create postscript document** ملفات باستخدام Aspose.Page for Java. جرب خطوطًا وألوانًا وأنماط حدود مختلفة لإنتاج مخرجات PostScript ذات مظهر احترافي.

---

**آخر تحديث:** 2026-02-20  
**تم الاختبار مع:** Aspose.Page for Java 23.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}