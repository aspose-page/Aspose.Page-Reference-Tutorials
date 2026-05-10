---
date: 2026-03-29
description: تعلم كيفية إضافة كائنات شفافة إلى مستندات XPS ثم تصدير XPS إلى PDF باستخدام
  Aspose.Page لـ .NET. دليل خطوة بخطوة مع نصائح عملية.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: تصدير XPS إلى PDF – إضافة كائن شفاف باستخدام Aspose.Page
url: /ar/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تصدير XPS إلى PDF – إضافة كائن شفاف باستخدام Aspose.Page

## المقدمة

في هذا الدرس ستتعلم كيفية إضافة كائنات شفافة إلى مستند XPS ثم **تصدير XPS إلى PDF** باستخدام Aspose.Page لـ .NET. يمكن للشفافية أن تجعل مستنداتك تبدو أكثر حداثة وتساعدك على إبراز المعلومات المهمة. سنستعرض كل خطوة، نشرح السبب وراء الكود، ونظهر لك كيفية إكمال سير العمل بتحويل ملف XPS إلى PDF لتسهيل المشاركة.

## إجابات سريعة
- **ماذا يعني “تصدير XPS إلى PDF”؟** تحويل ملف XPS إلى ملف PDF مع الحفاظ على التخطيط والألوان والشفافية.  
- **لماذا نضيف الشفافية أولاً؟** الكائنات الشفافة تتيح لك إنشاء رسومات طبقية تبدو رائعة في PDF النهائي.  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Page للاستخدام في الإنتاج.  
- **هل يمكن تشغيل هذا على .NET Core؟** بالتأكيد – يدعم Aspose.Page .NET Core، .NET 5/6 والإطار الكامل لـ .NET.  
- **أين يمكنني العثور على مزيد من الأمثلة؟** راجع وثائق Aspose.Page ومنتدى المجتمع المرتبط أدناه.

## المتطلبات المسبقة

قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:

- Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page لـ .NET. يمكنك تنزيلها من [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## استيراد المساحات الاسمية

لبدء العمل، أدرج المساحات الاسمية الضرورية في مشروعك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

الآن، لننتقل إلى الدليل خطوة بخطوة.

## الخطوة 1: إنشاء مستند XPS جديد

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

يقوم هذا الكود بتهيئة مستند XPS جديد باستخدام Aspose.Page لـ .NET.

## الخطوة 2: إظهار الشفافية

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

هذه الأسطر تنشئ مسارين رماديين سيعملان كخلفية للأشكال الشفافة التي سنضيفها لاحقًا.

## الخطوة 3: إنشاء مسار مع هندسة مستطيل مغلق

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

هنا ننشئ مستطيلًا أزرق. بما أننا سنغير شفافيته لاحقًا، سيظهر المستطيل شبه شفاف في PDF النهائي.

## الخطوة 4: تعديل المسارات والألوان

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

نستنسخ المستطيل الأول، نضيفه إلى الصفحة، ونغيّر لون التعبئة إلى الأخضر. يوضح ذلك مدى سهولة إعادة استخدام الهندسة الموجودة.

## الخطوة 5: استنساخ وتحويل المسارات

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

المسار المستنسخ يُنقل إلى الأسفل بمقدار 300 وحدة ويُلون بالأحمر، مما يمنحك تأثير طبقة مكدسة.

## الخطوة 6: تكرار وتعديل المسارات

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

نُعيد استخدام بيانات الهندسة من `path2`، ننقلها إلى اليمين، ونطبق تعبئة زرقاء مرة أخرى.

## الخطوة 7: إدارة الشفافية

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

ضبط خاصية `Opacity` إلى 0.8 يجعل هذا المستطيل شفافًا بنسبة 80 %، موضحًا كيف يمكنك ضبط الشفافية بدقة لكل عنصر.

## الخطوة 8: حفظ مستند XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

تم الآن حفظ ملف XPS مع تطبيق جميع الكائنات الشفافة.  

**تصدير إلى PDF:** لت **تصدير XPS إلى PDF**، ما عليك سوى استدعاء `doc.Save` مرة أخرى بامتداد `.pdf`، مثلًا `doc.Save(dataDir + "TransparentDocument.pdf");`. يتم الحفاظ على نفس الدقة البصرية، بما في ذلك إعدادات الشفافية، في ملف PDF الناتج.

## لماذا تصدير XPS إلى PDF بعد إضافة الشفافية؟

- **التوافق العالمي:** PDF مدعوم على نطاق واسع عبر المنصات، بينما XPS أقل شيوعًا.  
- **الحفاظ على التأثيرات البصرية:** يحافظ Aspose.Page على الشفافية، التدرجات، وتحويلات المصفوفة أثناء التحويل.  
- **سهولة المشاركة:** يمكن فتح ملفات PDF في المتصفحات، الأجهزة المحمولة، والعديد من القارئات الطرفية دون الحاجة إلى إضافات.

## حالات الاستخدام الشائعة

- **الكتيبات التسويقية** حيث تعطي الرسومات الطبقية إحساسًا فخمًا.  
- **المخططات التقنية** التي تحتاج إلى أقسام مميزة دون إغراق التخطيط.  
- **إنشاء التقارير** حيث تريد وضع علامات مائية أو شعارات بشفافية جزئية.

## نصائح وملاحظات

- **نصيحة احترافية:** دائمًا اضبط قيمة `Opacity` بين 0 و 1. القيم خارج هذا النطاق تُقيد وقد تنتج نتائج غير متوقعة.  
- **نصيحة الأداء:** إعادة استخدام الهندسة (`path2.Data`) يقلل من استهلاك الذاكرة عندما تحتاج إلى العديد من الأشكال المتشابهة.  
- **ملاحظة:** الحفظ مباشرةً إلى PDF بعد إضافة الشفافية يعمل مباشرةً، لكن إذا قمت بتحرير PDF لاحقًا بأدوات أخرى، قد لا تعرض بعض المشاهدات القديمة الشفافية بشكل صحيح.

## الخلاصة

إضافة كائنات شفافة إلى مستندات XPS باستخدام Aspose.Page لـ .NET توفر طريقة متعددة الاستخدامات لتعزيز العروض البصرية. بمجرد أن يبدو ملف XPS كما تريد، يمكنك **تصدير XPS إلى PDF** بسطر واحد من الكود، مع الحفاظ على جميع تأثيرات الشفافية لتوزيع واسع.

## الأسئلة الشائعة

### س1: هل يمكنني تطبيق الشفافية على أي كائن في مستند XPS؟

A1: نعم، يمكن تطبيق الشفافية على كائنات مختلفة مثل المسارات، الأشكال، والصور في مستند XPS.

### س2: كيف يمكنني ضبط شفافية عنصر محدد؟

A2: يمكنك ضبط خاصية الشفافية للملء أو الحد لتعديل شفافية العنصر المحدد.

### س3: هل Aspose.Page متوافق مع .NET Core؟

A3: نعم، يدعم Aspose.Page .NET Core، مما يتيح تطويرًا متعدد المنصات.

### س4: هل يمكنني تصدير مستندات XPS إلى صيغ أخرى باستخدام Aspose.Page؟

A4: يوفر Aspose.Page وظائف لتصدير مستندات XPS إلى صيغ متعددة، بما في ذلك PDF والصور.

### س5: أين يمكنني العثور على دعم إضافي ومناقشات المجتمع؟

A5: للحصول على دعم إضافي ومناقشات المجتمع، زر [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### س6: هل يحافظ تحويل PDF على إعدادات الشفافية الخاصة بي؟

A6: بالتأكيد. عند تصدير XPS إلى PDF باستخدام Aspose.Page، يتم الاحتفاظ بجميع إعدادات الشفافية والخلط.

### س7: هل يمكنني معالجة عدة ملفات XPS إلى PDF دفعة واحدة؟

A7: نعم، يمكنك تكرار مجموعة من ملفات XPS واستدعاء `doc.Save(...".pdf")` لكل منها، مما يتيح أتمتة التحويلات الجماعية.

**آخر تحديث:** 2026-03-29  
**تم الاختبار مع:** Aspose.Page 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}