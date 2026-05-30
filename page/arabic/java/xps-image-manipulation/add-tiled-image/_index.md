---
date: 2026-05-30
description: تعلم كيفية إنشاء مستند XPS في Java باستخدام Aspose.Page وإضافة صورة متكررة
  بسهولة من خلال هذا الدليل خطوة بخطوة. كيفية إنشاء ملفات XPS بسرعة.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: إضافة صورة متكررة في Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: كيفية إنشاء مستند XPS بصورة متكررة في Java
url: /ar/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء مستند XPS بصورة مكررة في Java

## مقدمة
إنشاء مستندات XPS برمجيًا هو مهارة أساسية لمطوري Java الذين يحتاجون إلى مخرجات قابلة للطباعة ومستقلة عن الجهاز. **كيفية إنشاء ملفات XPS** بكفاءة يتم الإجابة عليها بواسطة Aspose.Page for Java، الذي يج abstracts تفاصيل XML Paper Specification منخفضة المستوى ويسمح لك بالتركيز على التصميم البصري. في هذا الدليل ستتعرف على كيفية إنشاء مستند XPS، إضافة صورة مكررة كخلفية أو نمط، وحفظ النتيجة — كل ذلك باستخدام كود مختصر وجاهز للإنتاج.

## إجابات سريعة
- **ما الذي يفعله Aspose.Page؟** يوفر API عالي المستوى لإنشاء ومعالجة مستندات XPS في Java.  
- **هل يمكنني تكرار صورة؟** نعم – استخدم `XpsImageBrush` مع `XpsTileMode.Tile`.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت أو تجاري للاستخدام في الإنتاج.  
- **ما نسخة Java المدعومة؟** أي JDK 8+ متوافق.  
- **كم يستغرق التنفيذ؟** تقريبًا 10–15 دقيقة لسيناريو الصورة المكررة الأساسي.

## ما هو “إنشاء مستند XPS”؟
`XpsDocument` هو الكائن الأعلى مستوى في Aspose.Page الذي يمثل ملف XPS واحد في الذاكرة. يضم الصفحات والموارد والبيانات الوصفية، مما يتيح لك بناء المستند برمجيًا. يعني إنشاء مستند XPS إنشاء مثيل لهذه الفئة، إضافة عناصر بصرية، وأخيرًا استدعاء `save` لكتابة ملف التخطيط الثابت إلى القرص. يزيل هذا النهج الحاجة إلى التعامل اليدوي مع XML ويضمن الالتزام بمواصفات XML Paper Specification.

## لماذا إضافة صورة مكررة؟
التكرار يعيد رسم الرسمة عبر مساحة محددة، وهو مثالي للخلفيات أو العلامات المائية أو تعبئة الأنماط. باستخدام `XpsTileMode.Tile` تتكرر الصورة تلقائيًا دون تكرار يدوي، مما يوفر وقت التطوير ويضمن عرضًا متسقًا على أي جهاز. كما أن الصور المكررة تحافظ على حجم الملف منخفضًا لأن نفس مورد البت ماب يُعاد استخدامه بدلاً من تضمينه عدة مرات.

## المتطلبات المسبقة
قبل الغوص في التفاصيل، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – JDK 8 أو أحدث مثبت.  
2. **Aspose.Page for Java** – قم بتنزيله من [الموقع الإلكتروني](https://releases.aspose.com/page/java/).  
3. **دليل قابل للكتابة** – حيث سيتم حفظ ملف XPS المُولد.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الفئات الضرورية:

`XpsDocument` هو الكائن الرئيسي الذي يمثل ملف XPS.  
`XpsImageBrush` يرسم الأشكال باستخدام مصدر صورة.  
`XpsTileMode` يحدد طريقة تكرار الصورة.  
`Rectangle2D` يصف منطقة مستطيلة لتحديد الموضع.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد مشروعك
أضف ملفات JAR الخاصة بـ Aspose.Page إلى مسار الفئة (classpath) لمشروعك وتأكد من أن عبارات الاستيراد تُجمع بدون أخطاء.

### الخطوة 2: إنشاء مستند XPS
`XpsDocument` هو الحاوية الأساسية التي تحتفظ بالصفحات والمسارات والموارد. أنشئ مثيلًا لها بحجم الصفحة المطلوب، ثم يمكنك البدء في إضافة العناصر الرسومية.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### الخطوة 3: تحديد مسار الصورة المكررة
ضع الصورة التي تريد تكرارها (مثلاً `R08LN_NN.jpg`) داخل الدليل المشار إليه بـ `dataDir`. ستُستخدم الصورة كنمط للفرشاة.

### الخطوة 4: إضافة صورة مكررة
أنشئ مسارًا مستطيليًا واملأه بـ `XpsImageBrush`. من خلال ضبط وضع التكرار إلى `Tile`، تتكرر الصورة عبر المستطيل. عدّل مستطيلات المصدر والوجهة للتحكم في حجم التكرار والموضع.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### الخطوة 5: حفظ المستند
احفظ ملف XPS إلى القرص. سيحتوي ملف الإخراج على الصورة المكررة التي عرّفتها ويمكن فتحه بأي عارض XPS.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

كرر هذه الخطوات كلما احتجت إلى **إضافة صورة مكررة** إلى صفحات أو أشكال أخرى داخل نفس مستند XPS.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| الصورة لا تظهر | تحقق من صحة مسار الملف (`dataDir + "R08LN_NN.jpg"`) وأن الصورة قابلة للوصول. |
| نمط البلاط يبدو مشوّهًا | عدّل قيم `Rectangle2D` للمصدر والوجهة للتحكم في حجم البلاط. |
| الشفافية لا تؤثر | تأكد من ضبط شفافية الفرشاة **بعد** تكوين وضع التكرار. |

## الأسئلة المتكررة

**س:** هل Aspose.Page متوافق مع جميع إصدارات Java؟  
**ج:** يدعم Aspose.Page Java 8 حتى Java 21؛ يمكنك العثور على مصفوفة التوافق الكاملة [هنا](https://reference.aspose.com/page/java/).

**س:** هل يمكنني استخدام Aspose.Page في مشاريع تجارية؟  
**ج:** نعم، يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج. خيارات الشراء مُدرجة [هنا](https://purchase.aspose.com/buy).

**س:** هل هناك نسخة تجريبية مجانية متاحة؟  
**ج:** يمكن تنزيل نسخة تجريبية مجانية كاملة الوظائف من صفحة إصدارات Aspose [هنا](https://releases.aspose.com/).

**س:** أين يمكنني الحصول على دعم المجتمع؟  
**ج:** انضم إلى منتدى مجتمع Aspose.Page على [المنتدى](https://forum.aspose.com/c/page/39) لطرح الأسئلة ومشاركة الأمثلة.

**س:** كيف أحصل على ترخيص مؤقت للتقييم؟  
**ج:** تُوفر التراخيص المؤقتة عند الطلب عبر بوابة Aspose [هنا](https://purchase.aspose.com/temporary-license/).

## الخاتمة
أصبح لديك الآن سير عمل كامل وجاهز للإنتاج **لإنشاء مستندات XPS** مع صور مكررة باستخدام Aspose.Page for Java. من خلال الاستفادة من `XpsImageBrush` و `XpsTileMode.Tile`، يمكنك توليد رسومات غنية ومتكررة دون زيادة حجم الملف. جرّب أحجام بلاط مختلفة، مستويات شفافية، وأشكال لتصميم تخطيطات مستندات متقدمة. للخطوة التالية، استكشف إضافة أشكال متجهة أو نصوص لتزيد من تحسين ملفات XPS الخاصة بك.

---

**آخر تحديث:** 2026-05-30  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إضافة صورة إلى مستندات XPS في Java – دليل بسيط مع Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - إضافة صفحات إلى دليل XPS](/page/java/xps-page-manipulation/add-page/)
- [تحويل XPS إلى PDF في Java باستخدام Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}