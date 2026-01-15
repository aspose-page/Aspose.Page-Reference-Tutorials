---
date: 2026-01-15
description: تعلم كيفية دمج مستندات XPS باستخدام Aspose.Page لـ .NET – دليل خطوة بخطوة
  للدمج السلس للمستندات.
linktitle: Merge XPS Documents
second_title: Aspose.Page .NET API
title: كيفية دمج مستندات XPS باستخدام Aspose.Page لـ .NET
url: /ar/net/document-merging/merge-xps-documents/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية دمج مستندات XPS باستخدام Aspose.Page لـ .NET

## المقدمة

هل تبحث عن طريقة موثوقة **كيفية دمج XPS** برمجياً؟ في هذا الدرس سنرشدك خطوة بخطوة إلى دمج مستندات XPS باستخدام Aspose.Page لـ .NET. سواء كنت بحاجة إلى دمج تقارير، فواتير، أو أي ملفات أخرى تعتمد على XPS، فإن العملية بسيطة ومؤتمتة بالكامل. لنبدأ ونرى كيف يمكنك الحصول على مخرجات XPS مدمجة ونظيفة باستخدام بضع أسطر من كود C# فقط.

## إجابات سريعة
- **ما المكتبة التي تدير دمج XPS؟** Aspose.Page لـ .NET  
- **كم يستغرق التنفيذ؟** عادةً أقل من 10 دقائق  
- **هل أحتاج إلى ترخيص؟** الترخيص مطلوب للاستخدام في الإنتاج؛ تتوفر نسخة تجريبية مجانية  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7  
- **هل يمكن دمج ملفات XPS مشفرة؟** نعم – Aspose.Page يمكنه التعامل مع المستندات المشفرة

## ما هو دمج مستندات XPS؟
XPS (XML Paper Specification) هو تنسيق مستند ثابت تم إنشاؤه بواسطة مايكروسوفت. يعني دمج ملفات XPS ربط عدة مستندات XPS في ملف واحد مستمر مع الحفاظ على التخطيط الأصلي، الخطوط، والرسومات.

## لماذا نستخدم Aspose.Page لـ .NET؟
- **تحكم كامل** في عملية الدمج دون الحاجة إلى Microsoft XPS Viewer  
- **بدون تبعيات خارجية** – كل شيء يعمل داخل تطبيق .NET الخاص بك  
- **أداء عالي** – يعمل بكفاءة حتى مع المستندات الكبيرة  
- **متعدد المنصات** – متوافق مع .NET Framework، .NET Core، و .NET 5+  

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

- فهم أساسي للغة C# وبيئة .NET.  
- **Aspose.Page لـ .NET** مثبت – يمكنك تنزيله [هنا](https://releases.aspose.com/page/net/).  
- ملف أو أكثر من ملفات XPS تريد دمجها.

## استيراد المساحات الاسمية

في مشروع C# الخاص بك، استورد المساحة الاسمية التي تمنحك الوصول إلى API الخاص بـ XPS:

```csharp
using Aspose.Page.XPS;
```

## الخطوة 1: إعداد المشروع

أنشئ مشروع console أو مكتبة C# جديد في Visual Studio أو Rider أو أي بيئة تطوير تفضلها. أضف مرجعًا إلى ملف Aspose.Page DLL (أو قم بتثبيت حزمة NuGet `Aspose.Page`). سيتيح لك ذلك الوصول إلى الفئة `XpsDocument` المستخدمة لاحقًا.

## الخطوة 2: تهيئة التدفقات

افتح ملفات XPS المصدر كـ streams إدخال وأنشئ stream إخراج للمستند المدمج. تضمن عبارات `using` إغلاق جميع الـ streams بشكل صحيح بعد العملية.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Initialize XPS output stream
using (System.IO.Stream outStream = System.IO.File.Open(dataDir + "mergedXPSfiles.xps", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream inStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

## الخطوة 3: تحميل مستند XPS

أنشئ مثيلًا من `XpsDocument` باستخدام stream الإدخال الأساسي. يتيح لك كائن `XpsLoadOptions` تخصيص سلوك التحميل إذا لزم الأمر.

```csharp
XpsDocument document = new XpsDocument(inStream, new XpsLoadOptions());
```

## الخطوة 4: إنشاء مصفوفة من ملفات XPS

جهّز مصفوفة من السلاسل النصية التي تسرد كل ملف XPS تريد دمجه. يحدد ترتيب العناصر في المصفوفة ترتيب الصفحات في المستند النهائي.

```csharp
string[] filesToMerge = new string[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

## الخطوة 5: دمج ملفات XPS

استدعِ طريقة `Merge`، مع تمرير مصفوفة مسارات الملفات وstream الإخراج. يتولى Aspose.Page كل الأعمال الشاقة – دمج الصفحات، الحفاظ على الموارد، وكتابة ملف XPS النهائي.

```csharp
document.Merge(filesToMerge, outStream);
```

## المشكلات الشائعة والنصائح

- **الملف غير موجود** – تحقق مرة أخرى من المسارات في `filesToMerge`. يمكن أن يساعد استخدام `Path.Combine` في تجنب أخطاء فواصل المسار.  
- **استهلاك الذاكرة** – عند دمج عدد كبير من الملفات، فكر في معالجتها على دفعات للحفاظ على استهلاك الذاكرة منخفضًا.  
- **المستندات المشفرة** – إذا كان أي ملف XPS مصدر محميًا بكلمة مرور، قم بتحميله باستخدام الاعتمادات المناسبة قبل الدمج.

## الأسئلة المتكررة

**س1: هل يمكن دمج ملفات XPS بأحجام صفحات مختلفة؟**  
ج: نعم. يقوم Aspose.Page تلقائيًا بتطبيع أبعاد الصفحات أثناء الدمج.

**س2: هل هناك حد لعدد ملفات XPS التي يمكن دمجها؟**  
ج: لا يوجد حد صريح، لكن مجموعات الملفات الكبيرة جدًا قد تؤثر على الأداء؛ راقب استهلاك الذاكرة.

**س3: هل أحتاج إلى ترخيص خاص لدمج مستندات XPS مشفرة؟**  
ج: يتطلب أي ميزة على مستوى الإنتاج، بما في ذلك معالجة المستندات المشفرة، ترخيص كامل لـ Aspose.Page.

**س4: كيف يمكن إضافة تذييل مخصص لكل صفحة بعد الدمج؟**  
ج: بعد الدمج، يمكنك إعادة فتح ملف XPS الناتج باستخدام `XpsDocument` واستخدام API الرسم لإدراج التذييلات.

**س5: هل يدعم Aspose.Page .NET Core؟**  
ج: بالتأكيد. المكتبة متوافقة مع .NET Core 3.1 وما بعده، وكذلك .NET 5/6/7.

## الخاتمة

لقد تعلمت الآن **كيفية دمج XPS** بفعالية باستخدام Aspose.Page لـ .NET. باتباع الخطوات السابقة، يمكنك أتمتة دمج المستندات في أي تطبيق .NET، مما يوفر الوقت ويقلل الجهد اليدوي. استكشف الـ API أكثر لإضافة علامات مائية، تشفير الملف النهائي، أو تعديل الصفحات الفردية حسب الحاجة.

---

**آخر تحديث:** 2026-01-15  
**تم الاختبار مع:** Aspose.Page لـ .NET (أحدث نسخة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}