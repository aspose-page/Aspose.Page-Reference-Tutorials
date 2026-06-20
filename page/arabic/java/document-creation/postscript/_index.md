---
date: 2026-06-20
description: تعرف على كيفية ضبط حجم الصفحة A4، وإنشاء ملفات PostScript في Java، وإضافة
  خطوط مخصصة باستخدام Aspose.Page. جرّب النسخة التجريبية المجانية اليوم!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: إنشاء مستند في Java باستخدام PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: كيفية ضبط حجم الصفحة A4 وإنشاء PostScript في Java باستخدام Aspose.Page
url: /ar/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضبط حجم صفحة A4 وإنشاء PostScript في Java باستخدام Aspose.Page

## مقدمة
إذا كنت بحاجة إلى **ضبط حجم صفحة A4** أثناء إنشاء ملفات PostScript من Java، فإن Aspose.Page توفر واجهة برمجة تطبيقات سريعة وموثوقة تخفي التفاصيل منخفضة المستوى. في هذا الدرس سنستعرض سير العمل بالكامل—إنشاء مستند PostScript، تكوين أبعاد صفحة A4، و**إضافة خطوط مخصصة** عند الحاجة. في النهاية ستحصل على مقتطف كود جاهز يمكنك إدراجه في أي مشروع Java.

## إجابات سريعة
- **ما المكتبة التي تنشئ PostScript في Java؟** Aspose.Page for Java.  
- **ما حجم الصفحة الذي يستهدفه هذا الدليل؟** A4 (210 مم × 297 مم).  
- **هل يمكنني تضمين خطوط خاصة بي؟** نعم – اضبط مجلد الخطوط الإضافية في خيارات الحفظ.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم ترخيص تجاري؛ نسخة تجريبية مجانية متاحة.  
- **ما إصدارات Java المدعومة؟** Java 8 وما بعدها.

## كيفية ضبط حجم صفحة A4 وإنشاء PostScript في Java
حمّل مكتبة Aspose.Page، اضبط `PsSaveOptions` باستخدام ثوابت A4، واكتب المستند إلى ملف – كل ذلك في أقل من عشر أسطر من الكود. يضمن هذا النهج المباشر أبعاد الصفحة الصحيحة ويسمح لك بإضافة خطوط مخصصة دون إعدادات إضافية.

## ما هو حجم PostScript A4؟
حجم PostScript A4 هو معيار ISO 216 (210 مم × 297 مم) معبرًا عنه بلغة وصف صفحات PostScript. يحدد المنطقة القابلة للطباعة التي يفسرها الطابعات وعارضو المستندات، مما يضمن تخطيطًا متسقًا عبر المنصات. لأن PostScript يصف محتوى الصفحة بطريقة مستقلة عن الجهاز، فإن استخدام حجم A4 يضمن ظهور المستند بنفس الشكل على أي طابعة أو عارض يدعم A4 حول العالم.

## لماذا نستخدم Aspose.Page لضبط حجم صفحة PostScript؟
يدعم Aspose.Page **أكثر من 30 عامل PostScript** ويمكنه توليد ملفات تصل إلى **500 ميغابايت** دون تحميل المستند بالكامل في الذاكرة. يمنحك هذا تحكمًا دقيقًا في أبعاد الصفحة مع معالجة أحمال عمل كبيرة بكفاءة. كما أن المكتبة تج abstracts بنية PostScript المعقدة، تدير الموارد تلقائيًا، وتوفر بثًا عالي الأداء، مما يجعلها مثالية لكل من النشرات البسيطة ذات صفحة واحدة والتقارير المتعددة الصفحات المعقدة.

## كيفية إضافة خطوط مخصصة في Java
تضمن تضمين الخطوط الخاصة أن يظهر المستند المُولد كما صُمم على أي طابعة أو عارض، وتكتشف Aspose.Page الخطوط الموجودة في المجلد المحدد تلقائيًا. من خلال تسجيل مجلد خطوط إضافي، يمكنك استخدام أي خط TrueType أو OpenType، وتجنب الاستبدالات الافتراضية، والحفاظ على تناسق العلامة التجارية عبر جميع أجهزة الإخراج.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود:

- معرفة عملية ببرمجة Java.  
- تثبيت Aspose.Page for Java. يمكنك تنزيله [هنا](https://releases.aspose.com/page/java/).  
- مجلد اسمه `necessary_fonts` (أو أي اسم تفضله) يحتوي على أي خطوط مخصصة تريد تضمينها.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الفئات المطلوبة من Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

الآن لنقسم المثال إلى خطوات واضحة مرقمة.

### الخطوة 1: ضبط دليل المستند
الثابت `OUTPUT_DIR` يخبر المكتبة أين تكتب الملف المُولد.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### الخطوة 2: تعريف مجلد الخطوط
`FONTS_FOLDER` يشير إلى الدليل الذي يحتوي على خطوط TrueType أو OpenType المخصصة الخاصة بك.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### الخطوة 3: إنشاء تدفق إخراج لمستند PostScript
`FileOutputStream` يفتح تدفقًا سيتلقى الناتج النهائي لـ PostScript بحجم A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### الخطوة 4: إنشاء خيارات الحفظ بحجم A4
`PsSaveOptions` يتيح لك تحديد حجم الصفحة المستهدف.  
**التعريف:** `PsPageSize` هو تعداد يحتوي على ثوابت أحجام الصفحات القياسية مثل A4 وLetter وLegal.  
ضبط `options.setPageSize(PsPageSize.A4)` يكوّن المستند لأبعاد A4 القياسية.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### الخطوة 5: ضبط هوامش الصفحة وإضافة مجلد الخطوط المخصصة
`options.setMargins(0, 0, 0, 0)` يزيل جميع الهوامش لصفحة تمتد إلى الحافة، و`options.setAdditionalFontsFolder(FONTS_FOLDER)` يسجل خطوطك المخصصة.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### الخطوة 6: إنشاء مستند PS متعدد الصفحات أو صفحة واحدة
`PsDocument document = new PsDocument(outputStream, options)` ينشئ المستند. `PsDocument` يمثل مستند PostScript يمكن أن يحتوي على صفحة واحدة أو عدة صفحات. اضبط `multiPaged` إلى `true` للحصول على إخراج متعدد الصفحات.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### الخطوة 7: إغلاق الصفحة الحالية وحفظ المستند
استدعاء `document.close()` يُنهي الملف ويكتب ناتج **PostScript بحجم A4** إلى القرص.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## المشكلات الشائعة والنصائح
- **الخط غير ظاهر؟** تأكد من أن ملف الخط هو تنسيق TrueType أو OpenType مدعوم وأن `FONTS_FOLDER` ينتهي بشرطة مائلة (`/`).  
- **الهوامش لا تزال تظهر؟** استدعِ `options.setMargins(...)` **قبل** إنشاء كائن `PsDocument`.  
- **الإخراج متعدد الصفحات يظهر فارغًا؟** تذكر استدعاء `document.newPage()` لكل صفحة إضافية تحتاجها.

## الأسئلة المتكررة

**س: هل يمكنني استخدام خطوط مخصصة في مستند PostScript الخاص بي؟**  
ج: نعم، اضبط مجلد الخطوط الإضافية في خيارات الحفظ (انظر الخطوة 5) وستقوم Aspose.Page بتضمين الخطوط تلقائيًا.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الوصول إلى مرجع API الكامل؟**  
ج: راجع الوثائق [هنا](https://reference.aspose.com/page/java/).

**س: أين يمكنني شراء ترخيص لـ Aspose.Page for Java؟**  
ج: يمكنك شراء ترخيص [هنا](https://purchase.aspose.com/buy).

**س: أين يمكنني طلب المساعدة من المجتمع؟**  
ج: زر منتدى Aspose.Page [المنتدى](https://forum.aspose.com/c/page/39).

**س: هل يمكنني توليد ملفات PostScript متعددة الصفحات؟**  
ج: بالتأكيد—اضبط `multiPaged` إلى `true` في الخطوة 6 واستدعِ `document.newPage()` لكل صفحة إضافية.

## الخاتمة
باتباع هذه الخطوات أصبحت الآن تعرف **كيفية ضبط حجم صفحة A4** وإنشاء ملفات **PostScript** في Java باستخدام Aspose.Page، بالإضافة إلى القدرة على **إضافة خطوط مخصصة في Java** والتحكم في خيارات حجم الصفحة. تتولى Aspose.Page الجزء الثقيل، لتتمكن من التركيز على محتوى مستنداتك.

---

**آخر تحديث:** 2026-06-20  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## الدروس ذات الصلة

- [دروس Aspose.Page Java – ضبط حجم الصفحة المخصص أثناء إضافة صفحات في PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [كيفية إضافة نص في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [دروس Aspose Page Java - تحويل PostScript إلى PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```