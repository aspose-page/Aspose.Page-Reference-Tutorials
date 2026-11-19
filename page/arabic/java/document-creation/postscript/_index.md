---
date: 2026-11-19
description: تعلم كيفية إنشاء ملفات PostScript في Java، ضبط حجم الصفحة A4، وإضافة
  خطوط مخصصة باستخدام Aspose.Page. جرّب النسخة التجريبية المجانية اليوم!
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: إنشاء مستند في Java باستخدام PostScript
og_description: تعلم كيفية إنشاء ملف PostScript في Java، ضبط حجم الصفحة A4، وإضافة
  خطوط مخصصة باستخدام Aspose.Page. دليل البدء السريع للمطورين.
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: إنشاء ملف PostScript في Java بحجم A4 باستخدام Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: كيفية إنشاء ملف PostScript في Java بحجم A4
url: /ar/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء ملف PostScript في Java بحجم A4

## مقدمة
إذا كنت بحاجة إلى **إنشاء ملف PostScript في Java** مع ضبط أبعاد صفحة A4 القياسية، فإن Aspose.Page for Java يوفّر لك واجهة برمجة تطبيقات مختصرة وعالية الأداء تُجرد صsyntax PostScript منخفض المستوى. في هذا الدرس سنستعرض كل خطوة — من تحميل المكتبة وتكوين `PsSaveOptions` إلى تضمين خطوط TrueType أو OpenType الخاصة بك. في النهاية ستحصل على مقتطف جاهز للتنفيذ يمكنك إدراجه في أي مشروع Java.

## إجابات سريعة
- **ما المكتبة التي تُنشئ PostScript في Java؟** Aspose.Page for Java.  
- **ما حجم الصفحة المستهدف في هذا الدليل؟** A4 (210 مم × 297 مم).  
- **هل يمكنني تضمين خطوطي الخاصة؟** نعم – قم بتعيين مجلد الخطوط الإضافية في خيارات الحفظ.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم ترخيص تجاري؛ يتوفر إصدار تجريبي مجاني.  
- **ما إصدارات Java المدعومة؟** Java 8، 11، و 17 مدعومة بالكامل.

## كيفية ضبط حجم صفحة A4 وإنشاء PostScript في Java؟
حمّل مكتبة Aspose.Page، قم بتكوين `PsSaveOptions` باستخدام ثوابت A4، واكتب المستند إلى ملف — كل ذلك في أقل من عشر أسطر من الشيفرة. يضمن هذا النهج الأبعاد الصحيحة للصفحة ويسمح لك بإضافة خطوط مخصصة دون إعداد إضافي.

## ما هو حجم PostScript A4؟
حجم PostScript A4 هو معيار ISO 216 (210 مم × 297 مم) المُعبّر عنه بلغة وصف صفحات PostScript. يحدد المنطقة القابلة للطباعة التي يفسرها الطابعات وعارضات المستندات، مما يضمن تخطيطًا متسقًا عبر المنصات. نظرًا لأن PostScript يصف محتوى الصفحة بطريقة مستقلة عن الجهاز، فإن استخدام حجم A4 يضمن أن يظهر المستند بنفس الشكل على أي طابعة أو عارض يدعم A4 في جميع أنحاء العالم.

## لماذا نستخدم Aspose.Page لضبط حجم صفحة PostScript؟
يدعم Aspose.Page أكثر من 30 عاملًا من عوامل PostScript ويمكنه إنشاء ملفات تصل إلى 500 ميغابايت دون تحميل المستند بالكامل في الذاكرة. يعالج مستندًا مكوّنًا من 200 صفحة في أقل من ثانيتين، مما يوفر تحكمًا دقيقًا في أبعاد الصفحة مع معالجة الأحمال الكبيرة بكفاءة. كما أن المكتبة تُجرد صsyntax PostScript المعقد وتدير الموارد تلقائيًا، مما يجعلها مثالية لكل من النشرات البسيطة والتقارير المتعددة الصفحات المعقدة.

## كيفية إضافة خطوط مخصصة في Java
يضمن تضمين خطوطك الخاصة أن يظهر المستند المُنشأ تمامًا كما صُمم على أي طابعة أو عارض، وتكتشف Aspose.Page تلقائيًا الخطوط الموجودة في المجلد المحدد. من خلال تسجيل مجلد خطوط إضافي، يمكنك استخدام أي خط TrueType أو OpenType، وتجنب استبدالات الخطوط الافتراضية، والحفاظ على اتساق العلامة التجارية عبر جميع أجهزة الإخراج.

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك:

- معرفة عملية ببرمجة Java.  
- تثبيت Aspose.Page for Java. يمكنك تنزيله من [صفحة تنزيل Aspose.Page Java](https://releases.aspose.com/page/java/).  
- مجلد باسم `necessary_fonts` (أو أي اسم تفضله) يحتوي على أي خطوط مخصصة تريد تضمينها.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الفئات المطلوبة من Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

الآن لنقسم المثال إلى خطوات واضحة مرقمة.

### الخطوة 1: تعيين دليل المستند
الثابت `OUTPUT_DIR` يُخبر المكتبة بمكان كتابة الملف المُولَّد.

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
`PsSaveOptions` يحدد طريقة حفظ مستند PostScript، بما في ذلك حجم الصفحة والهوامش والضغط.  
**التعريف:** `PsPageSize` هو تعداد يحتوي على ثوابت أحجام الصفحات القياسية مثل A4 وLetter وLegal.  
ضبط `options.setPageSize(PsPageSize.A4)` يكوّن المستند بأبعاد A4 القياسية.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### الخطوة 5: ضبط هوامش الصفحة وإضافة مجلد الخطوط المخصص
`options.setMargins(0, 0, 0, 0)` يزيل جميع الهوامش لصفحة تمتد إلى الحافة بالكامل، و`options.setAdditionalFontsFolder(FONTS_FOLDER)` يسجل خطوطك المخصصة.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### الخطوة 6: إنشاء مستند PS متعدد الصفحات أو صفحة واحدة
`PsDocument` يمثل مستند PostScript يمكن أن يحتوي على صفحة واحدة أو عدة صفحات. إنشاء نسخة منه باستخدام `new PsDocument(outputStream, options)` ينشئ كائن المستند. اضبط `multiPaged` على `true` لإنتاج مستند متعدد الصفحات، ثم استدعِ `document.newPage()` لكل صفحة إضافية تحتاجها.

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
- **الخط غير ظاهر؟** تحقق من أن ملف الخط هو بصيغة TrueType أو OpenType مدعومة وأن `FONTS_FOLDER` ينتهي بشرطة مائلة (`/`).  
- **الهوامش لا تزال تظهر؟** استدعِ `options.setMargins(...)` **قبل** إنشاء كائن `PsDocument`.  
- **ناتج متعدد الصفحات يظهر فارغًا؟** تذكر استدعاء `document.newPage()` لكل صفحة إضافية تحتاجها.  
- **الملفات الكبيرة تسبب أخطاء نفاد الذاكرة؟** تقوم Aspose.Page ببث البيانات، لذا يمكنك بأمان إنشاء ملفات تصل إلى 500 ميغابايت؛ فقط تأكد من أن مساحة heap في JVM لا تقل عن 1 جيجابايت للعبء الكبير جدًا.

## الأسئلة المتكررة

**س: هل يمكنني استخدام خطوط مخصصة في مستند PostScript الخاص بي؟**  
ج: نعم، اضبط مجلد الخطوط الإضافية في خيارات الحفظ (انظر الخطوة 5) وستقوم Aspose.Page بتضمين الخطوط تلقائيًا.

**س: هل تتوفر نسخة تجريبية من Aspose.Page for Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من خلال [صفحة التجربة المجانية لـ Aspose.Page](https://releases.aspose.com/).

**س: كيف يمكنني الوصول إلى مرجع API الكامل؟**  
ج: راجع الوثائق عبر [توثيق مرجع API](https://reference.aspose.com/page/java/).

**س: أين يمكنني شراء ترخيص لـ Aspose.Page for Java؟**  
ج: يمكنك شراء ترخيص من خلال [صفحة شراء الترخيص](https://purchase.aspose.com/buy).

**س: أين يمكنني طلب المساعدة من المجتمع؟**  
ج: زر منتدى مجتمع Aspose.Page عبر [منتدى مجتمع Aspose.Page](https://forum.aspose.com/c/page/39).

**س: هل يمكنني إنشاء ملفات PostScript متعددة الصفحات؟**  
ج: بالتأكيد — اضبط `multiPaged` على `true` في الخطوة 6 واستدعِ `document.newPage()` لكل صفحة إضافية.

## الخلاصة
باتباع هذه الخطوات، أنت الآن تعرف **كيفية إنشاء ملف PostScript في Java** وتعيين **حجم صفحة A4** باستخدام Aspose.Page، بالإضافة إلى القدرة على **إضافة خطوط مخصصة في Java** والتحكم في خيارات حجم الصفحة. تتولى Aspose.Page الجزء الصعب، لذا يمكنك التركيز على محتوى مستنداتك بدلاً من تفاصيل لغة PostScript.

---

**آخر تحديث:** 2026-11-19  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

## دروس ذات صلة

- [دروس Aspose.Page Java – ضبط حجم صفحة مخصص أثناء إضافة صفحات في PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [كيفية إضافة نص في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [دروس Aspose Page Java - تحويل PostScript إلى PDF](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}