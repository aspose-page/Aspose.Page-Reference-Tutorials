---
date: 2026-02-25
description: تعلم كيفية استخدام فرشاة تدرج خطي في C# لإضافة تدرج إلى ملفات PS وتعبئة
  مستطيل بالتدرج باستخدام Aspose.Page لـ .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# فرشاة التدرج الخطي – إضافة تدرج عمودي إلى PostScript (PS) باستخدام Aspose.Page
url: /ar/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 عدة ألوان عبر الشكل."

We need to keep the bold markers.

Similarly for other bullet items.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# فرشاة التدرج الخطي C# – إضافة تدرج عمودي إلى PostScript (PS) باستخدام Aspose.Page

## المقدمة

في عالم معالجة وإنشاء المستندات، **Aspose.Page for .NET** يبرز كأداة قوية للمطورين. في هذا الدليل ستكتشف كيفية **إضافة تدرج إلى ملفات PS** باستخدام **فرشاة التدرج الخطي C#** لـ **ملء المستطيل بالتدرج**. بنهاية هذا البرنامج التعليمي، ستحصل على فهم واضح خطوة بخطوة للكود المطلوب ولماذا ينتج هذا الأسلوب تدرجًا عموديًا سلسًا في مخرجات PostScript الخاصة بك.

## إجابات سريعة
- **ماذا يفعل فرشاة التدرج الخطي C#؟** يخلق انتقالًا سلسًا بين عدة ألوان عبر الشكل.
- **هل يمكنني استخدامه مع أي نسخة .NET؟** نعم، Aspose.Page يدعم .NET Framework 4.5+ و .NET Core/5+.
- **هل أحتاج إلى ترخيص للإنتاج؟** الترخيص التجاري مطلوب للبُنى غير التجريبية.
- **هل التدرج عمودي فعليًا؟** يتم تدوير الفرشاة بزاوية 90°، مما يضمن تدفقًا عموديًا.
- **أين يتم حفظ المخرجات؟** إلى المسار الذي تحدده في `dataDir` (مثال: `VerticalGradient_outPS.ps`).

## ما هي فرشاة التدرج الخطي C#؟
**فرشاة التدرج الخطي C#** هي كائن GDI+ (`LinearGradientBrush`) يرسم انتقالًا لونيًا خطيًا بين نقاط محددة. عند دمجه مع واجهة برمجة تطبيقات الرسم في Aspose.Page، يتيح لك إنشاء تدرجات متقدمة مباشرة داخل مستند PostScript (PS).

## لماذا نستخدم فرشاة التدرج الخطي لـ PostScript؟
- **مخرجات عالية الجودة:** يتم رسم التدرجات على مستوى الطابعة، مما يحافظ على الدقة.
- **تحكم كامل:** يمكنك ضبط نقاط اللون المخصصة، الدوران، والتمدد.
- **كود قابل لإعادة الاستخدام:** نفس منطق الفرشاة يعمل مع PDF، SVG، وغيرها من الصيغ التي يدعمها Aspose.Page.

## المتطلبات المسبقة

قبل الغوص في البرنامج التعليمي، تأكد من توفر ما يلي:

- Aspose.Page for .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك العثور على الموارد والوثائق اللازمة [هنا](https://reference.aspose.com/page/net/).
- بيئة التطوير: إعداد بيئة تطوير مناسبة، بما في ذلك بيئة تطوير متكاملة (IDE) لتطوير .NET.
- فهم أساسي: التعرف على أساسيات تطوير .NET، بما في ذلك التعامل مع التدفقات، مسارات الرسومات، وتعديل الألوان.

## استيراد المساحات الاسمية

في مشروع C# الخاص بك، أدرج المساحات الاسمية المطلوبة في بداية ملف الكود:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إعداد دليل المستند

ابدأ بتحديد المسار إلى دليل المستندات الخاص بك. هذا هو الموقع الذي سيُحفظ فيه مستند PS.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء تدفق إخراج لمستند PostScript

أنشئ تدفق إخراج لمستند PostScript باستخدام فئة `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## الخطوة 3: إنشاء خيارات الحفظ ومستند PS

أنشئ خيارات حفظ بحجم A4 وابدأ مستند PS جديد بصفحة واحدة.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 4: تعريف أبعاد المستطيل

حدد أبعاد وموقع المستطيل الذي سيُطبق عليه التدرج العمودي.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## الخطوة 5: إنشاء مسار رسومي

أنشئ مسارًا رسوميًا من المستطيل المحدد.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## الخطوة 6: تعريف ألوان الاستيفاء

أنشئ مصفوفة من ألوان الاستيفاء ومواقعها للتدرج.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## الخطوة 7: إنشاء فرشاة التدرج الخطي

كوّن فرشاة التدرج الخطي باستخدام المستطيل كحدود، ولون البداية والنهاية.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## الخطوة 8: ضبط تحويل الفرشاة

أنشئ تحويلًا للفرشاة، مع التأكد من أن مكوّنات المقياس X و Y تتطابق مع عرض وارتفاع المستطيل.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## الخطوة 9: ضبط الطلاء وملء المستطيل

اضبط الطلاء للمستند، و**املأ المستطيل بالتدرج** باستخدام المسار المعرفة مسبقًا.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## الخطوة 10: إغلاق الصفحة الحالية وحفظ المستند

أغلق الصفحة الحالية واحفظ مستند PostScript.

```csharp
document.ClosePage();
document.Save();
```

تهانينا! لقد نجحت في **إضافة تدرج عمودي إلى مستند PostScript** باستخدام **فرشاة التدرج الخطي C#** مع Aspose.Page for .NET. جرّب معلمات وألوان مختلفة لتحقيق تأثيرات بصرية متنوعة في مستنداتك.

## المشكلات الشائعة والحلول

| المشكلة | لماذا يحدث | كيفية الإصلاح |
|-------|----------------|------------|
| يظهر التدرج أفقيًا | عدم تطبيق دوران الفرشاة | تأكد من استدعاء `brushTransform.Rotate(90);` قبل تعيينه إلى `brush.Transform`. |
| الألوان باهتة | تدفق إخراج منخفض الدقة | استخدم `PsSaveOptions` بدقة أعلى أو زد حجم المستند. |
| ملف الإخراج فارغ | عدم تفريغ التدفق | تحقق من استدعاء `document.Save();` خارج كتلة `using`. |

## الأسئلة المتكررة

**س1: هل يمكنني تطبيق تدرجات متعددة على مناطق مختلفة من نفس المستند؟**  
ج: نعم، يمكنك. كرّر الخطوات لكل منطقة بأبعادها ومخطط ألوانها الخاص.

**س2: كيف يمكنني دمج هذا الكود في مشروعي .NET الحالي؟**  
ج: انسخ الكود وألصقه في ملف مشروعك وتأكد من إضافة مرجع مكتبة Aspose.Page.

**س3: هل هناك أنواع تدرج أخرى متاحة في Aspose.Page for .NET؟**  
ج: يدعم Aspose.Page أنواع تدرج متعددة، بما في ذلك التدرج الشعاعي وتدرج المسار. راجع الوثائق للمزيد من التفاصيل.

**س4: هل يمكنني استخدام Aspose.Page في مشاريع تجارية؟**  
ج: نعم. تفضل بزيارة [هنا](https://purchase.aspose.com/buy) لاستكشاف خيارات الترخيص.

**س5: هل هناك منتدى مجتمع لـ Aspose.Page يمكنني طلب المساعدة منه؟**  
ج: بالتأكيد! انتقل إلى [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع مطورين آخرين والحصول على الدعم.

---

**آخر تحديث:** 2026-02-25  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}