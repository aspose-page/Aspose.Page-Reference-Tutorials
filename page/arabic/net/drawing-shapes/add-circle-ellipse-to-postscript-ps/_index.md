---
title: أضف دائرة القطع الناقص إلى PostScript (PS) باستخدام Aspose.Page
linktitle: إضافة دائرة القطع الناقص إلى بوستسكريبت (PS)
second_title: Aspose.Page .NET API
description: تعرف على كيفية إضافة علامات الحذف الدائرية بسهولة إلى مستندات PostScript (PS) باستخدام Aspose.Page for .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 10
url: /ar/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف دائرة القطع الناقص إلى PostScript (PS) باستخدام Aspose.Page

## مقدمة

مرحبًا بك في هذا البرنامج التعليمي الشامل حول إضافة علامات الحذف الدائرية إلى مستندات PostScript (PS) باستخدام Aspose.Page لـ .NET. Aspose.Page هي مكتبة قوية تتيح للمطورين العمل مع PostScript وتنسيقات المستندات الأخرى بسلاسة. في هذا الدليل، سنرشدك خلال عملية دمج علامات الحذف الدائرية في مستندات PS الخاصة بك بسهولة.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Page لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Page لمكتبة .NET من[هنا](https://releases.aspose.com/page/net/).

2. بيئة التطوير: تأكد من أن لديك بيئة تطوير .NET عاملة تم إعدادها على جهازك.

الآن، دعونا نبدأ مع الدليل خطوة بخطوة.

## استيراد مساحات الأسماء

في الخطوة الأولى، تحتاج إلى استيراد مساحات الأسماء الضرورية لجعل وظيفة Aspose.Page متاحة في التعليمات البرمجية الخاصة بك.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

الآن، دعنا نقسم المثال المقدم إلى خطوات متعددة لإرشادك خلال عملية إضافة علامات الحذف الدائرية إلى مستند PostScript.

## الخطوة 1: قم بتعيين دليل المستندات

```csharp
// البداية:1
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي لدليل المستندات الخاص بك.

## الخطوة 2: إنشاء دفق الإخراج لمستند PostScript

```csharp
//إنشاء دفق الإخراج لمستند بوستسكريبت
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

هنا، يتم إنشاء FileStream لكتابة مستند PostScript، ويتم ضبط وضع الملف لإنشاء ملف جديد.

## الخطوة 3: إنشاء خيارات الحفظ ومستند PS

```csharp
//إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();

// قم بإنشاء مستند PS جديد مكون من صفحة واحدة
PsDocument document = new PsDocument(outPsStream, options, false);
```

تتضمن هذه الخطوة إنشاء خيارات حفظ بحجم A4 وتهيئة مستند PS جديد مكون من صفحة واحدة.

## الخطوة 4: إنشاء مسار الرسومات للقطع الناقص الأول

```csharp
//إنشاء مسار الرسومات من القطع الناقص الأول
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

يتم إنشاء مسار رسومي للقطع الناقص الأول، مع تحديد موضعه وأبعاده.

## الخطوة 5: تعيين الطلاء وملء القطع الناقص

```csharp
//تعيين الطلاء
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//ملء القطع الناقص
document.Fill(path);
```

هنا يتم ضبط الطلاء، ويتم ملء الشكل الناقص الأول باللون المحدد.

## الخطوة 6: إنشاء مسار الرسومات للقطع الناقص الثاني

```csharp
//إنشاء مسار الرسومات من القطع الناقص الثاني
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

وبالمثل، يتم إنشاء مسار رسومي للقطع الناقص الثاني، مع تحديد موضعه وأبعاده.

## الخطوة 7: اضبط الحد وارسم الشكل الناقص

```csharp
//ضبط السكتة الدماغية
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//السكتة الدماغية (المخطط التفصيلي) للقطع الناقص
document.Draw(path);
```

في هذه الخطوة، يتم تعيين الحد، ويتم تحديد الشكل البيضاوي الثاني باللون المحدد وسمك الخط.

## الخطوة 8: أغلق الصفحة الحالية واحفظ المستند

```csharp
//إغلاق الصفحة الحالية
document.ClosePage();

//احفظ المستند
document.Save();
```

وأخيرًا، يتم إغلاق الصفحة الحالية، ويتم حفظ المستند بأكمله، وبذلك تكتمل العملية.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية إضافة علامات الحذف الدائرية إلى مستندات PostScript باستخدام Aspose.Page لـ .NET. قدم هذا البرنامج التعليمي دليلاً تفصيليًا خطوة بخطوة لمساعدتك على دمج هذه الوظيفة في مشاريعك بسلاسة.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع تنسيقات المستندات الأخرى؟

 A1: يركز Aspose.Page بشكل أساسي على PostScript، لكن Aspose يوفر مكتبات أخرى لتنسيقات المستندات المختلفة. افحص ال[اطرح الوثائق](https://reference.aspose.com/page/net/) لمزيد من التفاصيل.

### س2: أين يمكنني العثور على دعم إضافي ومناقشات مجتمعية؟

 ج2: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للمناقشات المجتمعية والدعم.

### س3: هل تتوفر نسخة تجريبية مجانية من Aspose.Page لـ .NET؟

 ج3: نعم، يمكنك الوصول إلى[تجربة مجانية](https://releases.aspose.com/)لاستكشاف ميزات Aspose.Page لـ .NET.

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟

 ج4: الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار والتقييم.

### س5: أين يمكنني شراء Aspose.Page لـ .NET؟

 A5: قم بشراء Aspose.Page لـ .NET من[صفحة الشراء](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
