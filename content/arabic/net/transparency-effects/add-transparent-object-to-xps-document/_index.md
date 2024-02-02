---
title: أضف كائنًا شفافًا إلى مستند XPS باستخدام Aspose.Page
linktitle: إضافة كائن شفاف إلى مستند XPS
second_title: Aspose.Page .NET API
description: تعرف على كيفية إضافة كائنات شفافة إلى مستندات XPS في .NET باستخدام Aspose.Page. تعزيز الجاذبية البصرية مع إرشادات خطوة بخطوة.
type: docs
weight: 11
url: /ar/net/transparency-effects/add-transparent-object-to-xps-document/
---
## مقدمة

في هذا البرنامج التعليمي، سنستكشف كيفية إضافة كائنات شفافة إلى مستند XPS باستخدام Aspose.Page لـ .NET. يمكن أن تعمل الشفافية في مستندات XPS على تحسين المظهر المرئي ونقل المعلومات بشكل فعال. سنقوم بتقسيم العملية إلى خطوات يمكن التحكم فيها، مما يضمن الوضوح وسهولة الفهم.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page لـ .NET. يمكنك تنزيله من[Aspose.Page للتوثيق .NET](https://reference.aspose.com/page/net/).

## استيراد مساحات الأسماء

للبدء، قم بتضمين مساحات الأسماء الضرورية في مشروعك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

الآن، دعونا نتابع الدليل خطوة بخطوة.

## الخطوة 1: إنشاء مستند XPS جديد

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```

يقوم هذا الرمز بتهيئة مستند XPS جديد باستخدام Aspose.Page لـ .NET.

## الخطوة الثانية: إظهار الشفافية

```csharp
// فقط لإظهار الشفافية
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

تقوم هذه الخطوط بإنشاء مسارات شفافة لعرض تأثير الشفافية في المستند.

## الخطوة 3: إنشاء مسار بهندسة مستطيل مغلق

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

هنا، نقوم بإنشاء مسار بهندسة مستطيلة مغلقة، ونضع فرشاة زرقاء صلبة لملئه، ونضيفه إلى الصفحة الحالية.

## الخطوة 4: التعامل مع المسارات والألوان

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

توضح هذه الخطوة كيف يمكن معالجة المسارات وتغيير الألوان.

## الخطوة 5: استنساخ المسارات وتحويلها

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

استنساخ المسارات وتحويلها، وتغيير لون المسار المستنسخ وتغييره.

## الخطوة 6: كرر وتعديل المسارات

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

كرر العملية، وقم بإنشاء مسار جديد بناءً على المسار السابق، مع إجراء التعديلات.

## الخطوة 7: إدارة التعتيم

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

وضح كيف يمكن إدارة العتامة بشكل مستقل لمسارات مختلفة.

## الخطوة 8: احفظ مستند XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

وأخيرًا، احفظ مستند XPS الناتج بالشفافية المطبقة.

## خاتمة

توفر إضافة كائنات شفافة إلى مستندات XPS باستخدام Aspose.Page لـ .NET طريقة متعددة الاستخدامات لتحسين العروض التقديمية المرئية. قم بتجربة أشكال هندسية وألوان وعتامة مختلفة لتحقيق التأثير المطلوب.

## الأسئلة الشائعة

### س١: هل يمكنني تطبيق الشفافية على أي كائن في مستند XPS؟

ج1: نعم، يمكن تطبيق الشفافية على كائنات متعددة مثل المسارات والأشكال والصور الموجودة في مستند XPS.

### س2: كيف يمكنني ضبط عتامة عنصر معين؟

ج2: يمكنك تعيين خاصية العتامة للتعبئة أو الحد لضبط شفافية عنصر معين.

### س3: هل Aspose.Page متوافق مع .NET Core؟

ج3: نعم، يدعم Aspose.Page .NET Core، مما يتيح التطوير عبر الأنظمة الأساسية.

### س٤: هل يمكنني تصدير مستندات XPS إلى تنسيقات أخرى باستخدام Aspose.Page؟

A4: يوفر Aspose.Page وظيفة لتصدير مستندات XPS إلى تنسيقات مختلفة، بما في ذلك PDF والصور.

### س5: أين يمكنني العثور على دعم إضافي ومناقشات مجتمعية؟

 ج5: للحصول على دعم إضافي ومناقشات مجتمعية، قم بزيارة[Aspose.صفحة المنتدى](https://forum.aspose.com/c/page/39).