---
title: أضف قيمة مسماة باستخدام Aspose.Page
linktitle: إضافة القيمة المسماة
second_title: Aspose.Page .NET API
description: تعرف على كيفية إضافة قيم مسماة إلى ملفات EPS في .NET باستخدام Aspose.Page. يرشدك هذا البرنامج التعليمي الشامل خلال العملية خطوة بخطوة.
type: docs
weight: 12
url: /ar/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## مقدمة

في مجال معالجة المستندات باستخدام .NET، يبرز Aspose.Page كأداة قوية للتعامل مع ملفات EPS. يعمل Aspose.Page على تمكين المطورين من التعامل مع بيانات تعريف XMP، وتسهيل المهام مثل إضافة القيم المسماة. سيرشدك هذا البرنامج التعليمي خلال عملية إضافة قيم مسماة إلى ملف EPS باستخدام Aspose.Page بطريقة خطوة بخطوة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- تثبيت بيئة تطوير متكاملة (IDE) مثل Visual Studio.
-  Aspose.Page لمكتبة .NET. إذا لم يتم تثبيته، يمكنك تنزيله من[هنا](https://releases.aspose.com/page/net/).

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية إلى كود C# الخاص بك. تعتبر مساحات الأسماء هذه حيوية للوصول إلى الوظائف التي توفرها Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## الخطوة 1: تهيئة دفق إدخال ملف EPS

 تتضمن الخطوة الأولى تهيئة دفق الإدخال لملف EPS. يستبدل`"Your Document Directory"` مع المسار إلى دليل المستندات الخاص بك:

```csharp
// البداية:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## الخطوة 2: احصل على بيانات تعريف XMP

استرداد بيانات تعريف XMP من ملف EPS. إذا كان ملف EPS يفتقر إلى بيانات تعريف XMP، فسيتم إنشاء ملف جديد مملوء بالقيم من تعليقات بيانات تعريف PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## الخطوة 3: تغيير قيم بيانات تعريف XMP

الآن، دعونا نجري تغييرات على بيانات تعريف XMP. في هذا المثال، سنضيف قيمة مسماة إلى البنية "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## الخطوة 4: احفظ ملف EPS مع بيانات تعريف XMP التي تم تغييرها

احفظ ملف EPS ببيانات تعريف XMP المحدثة. قم بإنشاء دفق إخراج واحفظ ملف EPS المعدل:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## خاتمة

تهانينا! لقد قمت بنجاح بإضافة قيمة مسماة إلى ملف EPS باستخدام Aspose.Page في .NET. يرشدك هذا البرنامج التعليمي عبر الخطوات الأساسية، ويعرض بساطة وفعالية Aspose.Page في معالجة المستندات.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع إصدارات ملفات EPS المختلفة؟

A1: يدعم Aspose.Page إصدارات ملفات EPS المختلفة، مما يضمن التوافق مع نطاق واسع من المستندات.

### س2: هل يمكنني استخدام Aspose.Page للمشاريع التجارية؟

 ج2: نعم، Aspose.Page يأتي مع ترخيص تجاري، ويمكنك شرائه[هنا](https://purchase.aspose.com/buy).

### س3: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page؟

 ج3: نعم، يمكنك استكشاف Aspose.Page مع توفر نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### س4: كيف يمكنني الحصول على الدعم أو التواصل مع مجتمع Aspose؟

 ج4: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على الدعم والتواصل مع المجتمع.

### س5: ما هو الترخيص المؤقت وكيف يمكنني الحصول عليه؟

 ج5: إذا كنت بحاجة إلى ترخيص مؤقت لأغراض الاختبار أو التقييم، فيمكنك الحصول على واحد[هنا](https://purchase.aspose.com/temporary-license/).