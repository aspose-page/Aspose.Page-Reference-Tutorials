---
date: 2025-11-29
description: تعلم كيفية حفظ XPS كملف PDF في Java باستخدام Aspose.Page Java. اتبع دليلنا
  خطوة بخطوة لتحويل XPS إلى PDF بكفاءة وإعدادات ضغط PDF.
language: ar
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: تحويل XPS إلى PDF في جافا باستخدام Aspose.Page Java
url: /java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل XPS إلى PDF في Java باستخدام Aspose.Page Java

## المقدمة
في هذا البرنامج التعليمي، ستتعلم **كيفية تحويل XPS إلى PDF في Java باستخدام Aspose.Page Java**، وهي مكتبة قوية صُممت لتحويل المستندات في Java. سواء كنت بحاجة إلى معالجة دفعات من الفواتير، أو إنشاء تقارير قابلة للطباعة، أو ببساطة ترحيل ملفات XPS القديمة، فإن Aspose.Page Java تجعل المهمة سريعة، موثوقة، وقابلة للتكوين بالكامل.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع تحويل XPS إلى PDF؟** Aspose.Page Java  
- **كم يستغرق التحويل الأساسي؟** عادةً أقل من ثانية لملف XPS من صفحة واحدة.  
- **هل أحتاج إلى ترخيص للتطوير؟** الإصدار التجريبي المجاني يكفي للتقييم؛ الترخيص مطلوب للإنتاج.  
- **هل يمكنني التحكم في ضغط PDF؟** نعم – استخدم `PdfSaveOptions` لتعيين ضغط الصور والنص.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أحدث (يوصى بـ JDK 11+).

## ما هو Aspose.Page Java؟
Aspose.Page Java هو **API عالي الأداء** يتيح للمطورين إنشاء وتحرير وتحويل مستندات XPS برمجيًا. يدعم تحويل XPS إلى PDF و PNG و JPEG وغيرها من الصيغ مع توفير تحكم دقيق في إعدادات الإخراج مثل **تعيين ضغط PDF**.

## لماذا تستخدم Aspose.Page Java لتحويل XPS إلى PDF؟
- **عروض بدون تبعيات** – لا مكتبات أصلية أو أدوات خارجية.  
- **حفظ تخطيط دقيق** – مخرجات PDF تعكس مظهر XPS الأصلي.  
- **تحكم كامل في مخرجات PDF** – يمكنك تعديل جودة الصورة، اختيار خوارزميات الضغط، وتحديد صفحات معينة للعرض.  
- **متعدد المنصات** – يعمل على Windows و Linux و macOS مع أي JDK قياسي.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أنك تمتلك:

1. **Java Development Kit (JDK) 8+** – يُنصح بأحدث JDK للأداء والأمان.  
2. **مكتبة Aspose.Page for Java** – قم بتحميل ملف JAR من [توثيق Aspose.Page Java الرسمي](https://reference.aspose.com/page/java/).  
3. **IDE** (IntelliJ IDEA، Eclipse، VS Code) أو محرر نصوص بسيط مع أدوات بناء سطر الأوامر (Maven/Gradle).

## استيراد الحزم
أضف الاستيرادات المطلوبة إلى فئة Java الخاصة بك لتتمكن من التعامل مع مستندات XPS وإخراج PDF.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## دليل خطوة بخطوة

### الخطوة 1: تعيين مسار دليل المستند
حدد المجلد الذي يحتوي على ملف XPS المصدر ومكان حفظ ملف PDF.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### الخطوة 2: تهيئة تدفق إخراج PDF
أنشئ `FileOutputStream` يشير إلى ملف PDF الوجهة.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **نصيحة احترافية:** استخدم `try‑with‑resources` لإغلاق التدفق تلقائيًا وتجنب تسرب الموارد.

### الخطوة 3: تحميل مستند XPS
أنشئ كائن `XpsDocument` بتحميل ملف XPS المصدر.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### الخطوة 4: تهيئة خيارات حفظ PDF (تعيين ضغط PDF)
قم بتكوين طريقة ضغط PDF. تسمح لك هذه الخطوة **بتعيين ضغط PDF** للصور والنص، مما يقلل حجم الملف دون التضحية بالجودة.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **لماذا هذا مهم:** تعديل جودة JPEG وأنواع الضغط يمكن أن يقلص ملف PDF بحجم 10 ميغابايت إلى أقل من 2 ميغابايت مع الحفاظ على الدقة البصرية التي تحتاجها.

### الخطوة 5: إنشاء جهاز عرض لتنسيق PDF
`PdfDevice` يرسل الصفحات المرسومة إلى تدفق إخراج PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### الخطوة 6: حفظ المستند
أخيرًا، قم برسم محتوى XPS إلى PDF باستخدام الخيارات المكوّنة.

```java
document.save(device, options);
```

> **النتيجة:** بعد التنفيذ، سيظهر `XPStoPDF.pdf` في مجلد `dataDir`، يحتوي على الصفحات المحوّلة مع إعدادات الضغط التي حددتها.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|----------|
| **`FileNotFoundException`** | مسار `dataDir` غير صحيح | تحقق من وجود الدليل وأن التطبيق يمتلك أذونات القراءة/الكتابة. |
| **صفحات PDF فارغة** | عدم تهيئة `PdfDevice` | تأكد من إنشاء `PdfDevice` باستخدام نفس `FileOutputStream` المستخدم للإخراج. |
| **حجم PDF كبير** | الضغط الافتراضي منخفض | زيادة `setJpegQualityLevel` أو التحويل إلى `PdfImageCompression.Jpeg` بجودة أقل. |
| **ظهور بعض الصفحات فقط** | مرشح `setPageNumbers` يستبعد الصفحات | عدّل المصفوفة لتشمل جميع أرقام الصفحات المطلوبة أو أزل الاستدعاء لتصدير جميع الصفحات. |

## الأسئلة المتكررة

**س: هل Aspose.Page Java متوافق مع إصدارات Java المختلفة؟**  
نعم، يدعم Aspose.Page Java Java 8 حتى Java 21، بما في ذلك توزيعات Oracle و OpenJDK.

**س: هل يمكنني تخصيص إعدادات الضغط للـ PDF المحوّل؟**  
بالطبع. استخدم `PdfSaveOptions` لتعيين جودة JPEG، نوع ضغط الصورة، وضغط النص كما هو موضح في الخطوة 4.

**س: أين يمكنني العثور على دعم إضافي أو مناقشات المجتمع؟**  
قم بزيارة [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على مساعدة المجتمع، عينات الكود، ونصائح حل المشكلات.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page؟**  
نعم، يمكنك تنزيل نسخة تجريبية كاملة الوظائف من [صفحة تنزيل Aspose](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟**  
يمكن طلب ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/).

## الخلاصة
باستخدام **Aspose.Page Java**، يمكنك بسهولة **حفظ XPS كـ PDF** والتحكم في كل جانب من جوانب الإخراج، من اختيار الصفحات إلى الضغط. يغطي هذا البرنامج التعليمي كل ما تحتاجه لدمج تحويل XPS إلى PDF في تطبيقات Java الخاصة بك، سواء كنت تبني أداة لمرة واحدة أو خط أنابيب معالجة مستندات على نطاق واسع.

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}