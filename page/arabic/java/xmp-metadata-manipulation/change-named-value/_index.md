---
date: 2025-12-21
description: دروس Aspose Page XMP – تعلم كيفية تعديل بيانات XMP الوصفية في ملفات EPS
  باستخدام Aspose.Page للغة Java في دليل واضح خطوة بخطوة.
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: دليل Aspose.Page XMP – تغيير القيمة المسماة في XMP باستخدام Java
url: /ar/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page XMP tutorial – تغيير قيمة مسماة في XMP باستخدام Java

## الإجابات السريعة
- **ما الذي يغطيه هذا الدرس؟** تغيير قيمة XMP مسماة في ملف EPS باستخدام Aspose.Page for Java.  
- **ما نسخة المكتبة المطلوبة؟** أي إصدار حديث من Aspose.Page for Java (API مستقر منذ عدة سنوات).  
- **هل أحتاج إلى ترخيص؟** يلزم ترخيص مؤقت أو كامل للإنتاج؛ نسخة تجريبية مجانية تكفي للاختبار.  
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 10‑15 دقيقة للمطور المألوف بـ Java I/O.  
- **هل يمكنني استخدامه مع صيغ ملفات أخرى؟** API XMP متاح أيضًا لـ PDF و SVG وغيرها من الصيغ المدعومة من Aspose.Page.

## ما هو XMP metadata؟
XMP (Extensible Metadata Platform) هو تنسيق موحد لتضمين بيانات وصفية غنية—مثل المُنشئ، العنوان، والخصائص المخصصة—مباشرة داخل الملفات. في مستندات EPS، يعيش XMP جنبًا إلى جنب مع تعليقات PostScript التقليدية، مما يتيح للتطبيقات قراءة وتعديل البيانات الوصفية دون تغيير المحتوى البصري.

## لماذا نستخدم Aspose.Page for Java لتعديل XMP؟
- **تحكم كامل** – الوصول إلى أي خاصية XMP، بما في ذلك الهياكل المخصصة، دون الحاجة إلى تحليل XML الخام.  
- **اتساق عبر الصيغ** – نفس الـ API يعمل مع EPS و PDF و SVG، مما يبسط صيانة الكود.  
- **بدون تبعيات خارجية** – مكتبة Java صافية، لا تحتاج إلى كود أصلي أو محللات إضافية.  
- **معالجة أخطاء قوية** – التحقق المدمج يضمن بقاء EPS الناتج متوافقًا مع المعايير.

## المقدمة
Aspose.Page for Java هي مكتبة Java قوية تسهل معالجة ملفات EPS. عندما يتعلق الأمر بالتعامل مع بيانات XMP الوصفية داخل هذه الملفات، تمنح Aspose.Page المطورين مجموعة شاملة من الميزات. في هذا الدرس، سنركز على تغيير قيمة مسماة في XMP، مقدمين دليلًا واضحًا وموجزًا للمطورين الراغبين في تعزيز قدراتهم على معالجة المستندات.

## المتطلبات المسبقة
قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:
1. **بيئة تطوير Java** – تأكد من إعداد بيئة تطوير Java على جهازك.  
2. **مكتبة Aspose.Page for Java** – قم بتحميل وتكامل المكتبة في مشروعك. يمكنك العثور على المكتبة والوثائق التفصيلية [هنا](https://reference.aspose.com/page/java/).  
3. **ملف EPS تجريبي** – احرص على وجود ملف EPS تجريبي جاهز للتجربة. إذا لم يكن لديك ملف، يمكنك استخدام الملف المثال المسمى **"xmp4.eps."**

## استيراد الحزم
لبدء العملية، استورد الحزم الضرورية في كود Java الخاص بك. هذه الحزم أساسية للتفاعل مع Aspose.Page for Java. أضف السطور التالية في بداية ملف Java:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

الآن، لنقسم عملية تغيير قيمة مسماة في XMP باستخدام Aspose.Page for Java إلى عدة خطوات:

## الخطوة 1: تهيئة تدفق ملف EPS الإدخالي
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## الخطوة 2: تهيئة PsDocument
```java
PsDocument document = new PsDocument(psStream);
```

## الخطوة 3: الحصول على بيانات XMP الوصفية
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## الخطوة 4: تعيين قيمة جديدة في XMP
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## الخطوة 5: تهيئة تدفق ملف EPS الإخراجي
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## الخطوة 6: حفظ المستند مع بيانات XMP الوصفية المعدلة
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## الخطوة 7: إغلاق تدفق ملف EPS الإدخالي
```java
// Close input EPS stream
psStream.close();
```

هذا الدليل خطوة بخطوة يضمن نهجًا منهجيًا لتغيير قيمة مسماة في XMP باستخدام Aspose.Page for Java. باتباع هذه الخطوات، يمكنك دمج هذه الوظيفة بسلاسة في تطبيقات Java الخاصة بك.

## المشكلات الشائعة والحلول
- **FileNotFoundException** – تأكد من أن `dataDir` يشير إلى المجلد الصحيح وأن `xmp4.eps` موجود.  
- **LicenseException** – إذا ظهرت أخطاء الترخيص، تأكد من تحميل ملف ترخيص Aspose.Page صالح قبل إنشاء `PsDocument`.  
- **Metadata Not Updated** – بعد الحفظ، افتح الـ EPS الناتج في عارض بيانات وصفية (مثل Adobe Bridge) لتأكيد ظهور القيمة الجديدة.

## الخاتمة
في الختام، يبسط Aspose.Page for Java عملية العمل مع بيانات XMP الوصفية في ملفات EPS. لقد زودك هذا الدرس بالمعرفة اللازمة لتغيير قيمة مسماة في XMP بفعالية، مما يعزز قدراتك في معالجة المستندات.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟
Aspose.Page يدعم أساسًا Java، لكن Aspose توفر مكتبات مشابهة لمختلف لغات البرمجة.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟
نعم، يمكنك تجربة نسخة تجريبية مجانية من Aspose.Page for Java [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على دعم إضافي ومناقشات حول Aspose.Page for Java؟
زر منتدى [Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع ومناقشاته.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني شراء Aspose.Page for Java؟
لشراء Aspose.Page for Java، زر صفحة [الشراء](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-21  
**تم الاختبار مع:** Aspose.Page for Java (latest release)  
**المؤلف:** Aspose