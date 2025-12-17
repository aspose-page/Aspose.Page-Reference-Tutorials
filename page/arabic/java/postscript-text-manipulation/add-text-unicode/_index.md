---
date: 2025-12-17
description: تعلم كيفية إضافة نص Unicode في Java PostScript باستخدام Aspose.Page –
  دليل خطوة بخطوة حول كيفية إضافة سلاسل Unicode بسهولة.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: كيفية إضافة نص يونيكود في Java PostScript باستخدام Aspose.Page
url: /ar/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة نص Unicode في Java PostScript باستخدام Aspose.Page

## المقدمة
إذا كنت تتساءل **كيف تضيف أحرف Unicode** إلى سير عمل PostScript (أو XPS) قائم على Java، فقد وصلت إلى المكان الصحيح. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة المطلوبة لتضمين سلاسل Unicode باستخدام مكتبة Aspose.Page للـ Java. في نهاية الدليل ستتمكن من إدراج أي نص خاص بلغة معينة—العربية، الصينية، الرموز التعبيرية، أيًا كان—مباشرةً في مخرجات PostScript الخاصة بك.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page للـ Java  
- **هل يمكنني إضافة نصوص من اليمين إلى اليسار؟** نعم، اضبط مستوى Bidi كما هو موضح في الشيفرة  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج  
- **أي بيئة تطوير متكاملة (IDE) هي الأنسب؟** أي IDE للـ Java (IntelliJ IDEA، Eclipse، NetBeans)  
- **هل الشيفرة متعددة المنصات؟** بالتأكيد—يمكن تشغيلها على Windows أو macOS أو Linux

## ما معنى “كيفية إضافة Unicode” في سياق PostScript؟
إضافة Unicode تعني إدراج أحرف تمثل نقاط شفرة تتجاوز نطاق ASCII الأساسي. تقوم Aspose.Page بتجريد تفاصيل الترميز منخفضة المستوى، مما يتيح لك التركيز على محتوى النص وموقعه البصري.

## لماذا نستخدم Aspose.Page للنصوص Unicode؟
- **دعم Unicode كامل** – يتعامل مع النصوص المعقدة، والربط الحرفي (ligatures)، واللغات من اليمين إلى اليسار.  
- **بدون تبعيات خارجية** – لا حاجة لإدارة ملفات الخطوط يدويًا؛ API يعمل مع خطوط النظام.  
- **API بسيط** – عدد قليل من استدعاءات الطرق يكفي لعرض نص متعدد اللغات.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك العناصر التالية جاهزة:

1. **مجموعة تطوير جافا (JDK)** – أي نسخة حديثة (8 أو أحدث).  
2. **Aspose.Page للـ Java** – قم بتحميل وتثبيت المكتبة من [رابط التحميل](https://releases.aspose.com/page/java/).  
3. **بيئة تطوير متكاملة (IDE) من اختيارك** – IntelliJ IDEA، Eclipse، أو أي IDE آخر للـ Java تفضله.

## استيراد الحزم
أضف الفئات المطلوبة من Aspose.Page إلى ملف المصدر الخاص بك في Java:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## الخطوة 1: إعداد المشروع
أنشئ مشروع Java جديد، أضف ملف JAR الخاص بـ Aspose.Page إلى مسار بناء المشروع، وأنشئ مجلدًا سيتم حفظ ملف XPS المُولد فيه. يُشار إلى هذا المجلد لاحقًا باسم `dataDir`.

## الخطوة 2: تهيئة مستند XPS
أنشئ مستند XPS فارغ سيحمل المحتوى:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## الخطوة 3: إضافة نص Unicode
الآن سنضيف فعليًا سلسلة Unicode. المثال أدناه يكتب العبارة المعكوسة “AVAJ rof SPX.esopsA”، والتي تحتوي فقط على أحرف ASCII، لكن يمكنك استبدالها بأي نص Unicode (مثل العربية “مرحبا” أو الصينية “你好”).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **نصيحة احترافية:** لضمان عرض اللغات من اليمين إلى اليسار بشكل صحيح، اضبط `glyphs.setBidiLevel(1);`. بالنسبة للغات من اليسار إلى اليمين يمكنك حذف هذا السطر.

## الخطوة 4: حفظ المستند
احفظ ملف XPS على القرص:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

بعد تشغيل البرنامج، افتح الملف `AddEncodingText_out.xps` باستخدام أي عارض XPS لترى نص Unicode معروضًا عند الإحداثيات المحددة.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| يظهر النص كمربعات | الخط غير موجود أو لا يدعم الأحرف | استخدم خطًا يحتوي على الأحرف المطلوبة (مثل “Arial Unicode MS”) |
| نص من اليمين إلى اليسار يُعرض من اليسار إلى اليمين | لم يتم ضبط مستوى Bidi | استدعِ `glyphs.setBidiLevel(1);` |
| الملف غير محفوظ | مسار `dataDir` غير صالح أو لا توجد صلاحيات كتابة | تأكد من وجود المجلد ومن أن التطبيق يملك صلاحية الكتابة |

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page للـ Java مع لغات برمجة أخرى؟
Aspose.Page مصممة أساسًا للـ Java، لكن Aspose توفر مكتبات لمختلف لغات البرمجة.

### هل هناك نسخة تجريبية مجانية؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الدعم والنقاشات حول Aspose.Page؟
زر منتدى [Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على الدعم والنقاشات.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### ما هي أنماط الخطوط المتاحة في Aspose.Page؟
Aspose.Page تدعم أنماط الخطوط مثل Regular، Bold، Italic، وBoldItalic.

## الخاتمة
لقد أتقنت الآن **كيفية إضافة نص Unicode** إلى مستند Java PostScript (XPS) باستخدام Aspose.Page. تفتح هذه القدرة الباب أمام تقارير متعددة اللغات، فواتير دولية، وأي سيناريو يتطلب أحرفًا غير ASCII. لا تتردد في استكشاف ميزات إضافية مثل تدوير النص، مسارات القص، أو تضمين خطوط مخصصة—التفاصيل متوفرة في [الوثائق الرسمية](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-17  
**تم الاختبار مع:** Aspose.Page للـ Java 23.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

---