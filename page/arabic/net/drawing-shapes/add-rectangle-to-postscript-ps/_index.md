---
title: إضافة مستطيل إلى PostScript (PS) باستخدام Aspose.Page لـ .NET
linktitle: إضافة مستطيل إلى بوستسكريبت (PS)
second_title: Aspose.Page .NET API
description: قم بتحسين إنشاء المستندات في .NET باستخدام Aspose.Page. تعلم كيفية إضافة مستطيلات إلى ملفات PostScript (PS) خطوة بخطوة.
weight: 12
url: /ar/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مستطيل إلى PostScript (PS) باستخدام Aspose.Page لـ .NET

## مقدمة

إذا كنت تتطلع إلى تحسين قدرات إنشاء المستندات لديك في .NET، فإن Aspose.Page يوفر حلاً قويًا للتعامل مع مستندات PostScript. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة مستطيلات إلى مستند PostScript باستخدام Aspose.Page لـ .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Page لمكتبة .NET من[هنا](https://releases.aspose.com/page/net/).

- بيئة التطوير: تأكد من إعداد بيئة تطوير .NET على جهازك.

## استيراد مساحات الأسماء

قبل البدء في البرمجة، تأكد من استيراد مساحات الأسماء اللازمة للوصول إلى الفئات والطرق المطلوبة:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

الآن، دعونا نقسم المثال إلى عدة خطوات:

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

```csharp
// البداية:1
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
```

في هذه الخطوة، استبدل "دليل المستندات الخاص بك" بالمسار الذي تريد حفظ مستند PostScript فيه.

## الخطوة 2: إنشاء دفق الإخراج لمستند PostScript

```csharp
//إنشاء دفق الإخراج لمستند بوستسكريبت
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

هنا، نقوم بإنشاء دفق إخراج لمستند PostScript ونحدد اسم الملف ("AddRectangle_outPS.ps"). اضبط اسم الملف وموقعه وفقًا لتفضيلاتك.

## الخطوة 3: قم بتعيين خيارات الحفظ وإنشاء مستند PS

```csharp
//إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();

// قم بإنشاء مستند PS جديد مكون من صفحة واحدة
PsDocument document = new PsDocument(outPsStream, options, false);
```

اضبط خيارات الحفظ، مع تحديد حجم الصفحة المطلوب (A4 في هذه الحالة). ثم قم بإنشاء مستند بوستسكريبت جديد ذو صفحة واحدة.

## الخطوة 4: إضافة مستطيل وملء

```csharp
//قم بإنشاء مسار الرسومات من المستطيل الأول
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//تعيين الطلاء
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//املأ المستطيل
document.Fill(path);
```

هنا، نقوم بإنشاء مسار رسومي يمثل المستطيل الأول، ونضبط لون الطلاء (في هذه الحالة، البرتقالي)، ونملأ المستطيل.

## الخطوة 5: إضافة مستطيل آخر والسكتة الدماغية

```csharp
//قم بإنشاء مسار الرسومات من المستطيل الثاني
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//ضبط السكتة الدماغية
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//السكتة الدماغية (المخطط التفصيلي) المستطيل
document.Draw(path);
```

كما هو الحال في الخطوة السابقة، نقوم بإنشاء مسار رسومي للمستطيل الثاني، ونضبط لون الحد (أحمر بسمك 3)، ونحدد المستطيل.

## الخطوة 6: أغلق الصفحة واحفظ المستند

```csharp
//إغلاق الصفحة الحالية
document.ClosePage();

//احفظ المستند
document.Save();
```

وأخيرًا، أغلق الصفحة الحالية واحفظ المستند بأكمله.

## خاتمة

تهانينا! لقد نجحت في إضافة مستطيلات إلى مستند PostScript باستخدام Aspose.Page لـ .NET. غطى هذا البرنامج التعليمي الخطوات الأساسية، بدءًا من إعداد بيئة التطوير الخاصة بك وحتى حفظ المستند النهائي.

## الأسئلة الشائعة

### س1: هل يمكنني تخصيص ألوان المستطيلات؟

A1: نعم، يمكنك تخصيص الألوان عن طريق ضبط المعلمات في`SolidBrush` و`Pen` الطبقات.

### س2: هل Aspose.Page متوافق مع تنسيقات المستندات الأخرى؟

ج٢: نعم، يدعم Aspose.Page تنسيقات المستندات المختلفة، بما في ذلك XPS وPostScript.

### س3: كيف يمكنني إضافة نص إلى المستند؟

 ج3: يمكنك استخدام`TextFragment` فئة في Aspose.Page لإضافة نص إلى المستند الخاص بك.

### س4: أين يمكنني العثور على أمثلة ووثائق إضافية؟

 ج٤: استكشف الوثائق[هنا](https://reference.aspose.com/page/net/) وزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع.

### س5: هل يمكنني تجربة Aspose.Page قبل الشراء؟

 ج5: نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/) ، وللاستخدام الممتد، فكر في أ[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
