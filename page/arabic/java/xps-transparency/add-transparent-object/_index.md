---
date: 2026-01-02
description: تعلم كيفية إضافة الشفافية إلى مستندات XPS في Java باستخدام Aspose.Page.
  اتبع دليلنا خطوة بخطوة لإضافة كائنات شفافة مع تأثيرات بصرية مذهلة.
linktitle: Add Transparent Object in Java XPS
second_title: Aspose.Page Java API
title: كيفية إضافة الشفافية إلى مستندات Java XPS
url: /ar/java/xps-transparency/add-transparent-object/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة الشفافية إلى مستندات Java XPS

## المقدمة
إذا كنت تبحث عن **كيفية إضافة الشفافية** إلى مستندات Java XPS الخاصة بك ومنحها مظهرًا عصريًا ومتعدد الطبقات، فإن Aspose.Page for Java يجعل ذلك بسيطًا. في هذا البرنامج التعليمي سنستعرض كل ما تحتاجه — من إعداد البيئة إلى إنشاء مسارات شفافة، ومعالجة التعتيم، وأخيرًا حفظ النتيجة. في النهاية، ستكون قادرًا على إضافة الشفافية إلى أي كائن XPS بثقة.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكن التحكم في التعتيم برمجيًا؟** نعم، عبر طريقة `setOpacity` على الفرشاة.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم الحصول على ترخيص تجاري للاستخدام غير التجريبي.  
- **ما نسخة Java المدعومة؟** Java 8 وما بعدها.  
- **هل الناتج متوافق مع عارضات XPS القياسية؟** بالتأكيد — العارضات القياسية تعرض الشفافية بشكل صحيح.

## ما هي الشفافية في XPS؟
تسمح الشفافية لك بعرض الكائنات بدرجات متفاوتة من التعتيم، مما يتيح للعنصر الخلفي الظهور من خلاله. هذا التأثير مفيد للعلامات المائية، الرسومات المتراكبة، أو أي تصميم حيث تعزز الطبقات البصرية القابلية للقراءة.

## لماذا نستخدم Aspose.Page لإضافة الشفافية؟
- **تحكم كامل** في الهندسة، الفرش، والتحويلات.  
- **بدون تبعيات خارجية** — كل شيء يتم داخل الـ API.  
- **دعم متعدد المنصات**، لذا يعمل نفس الكود على Windows وLinux وmacOS.  

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود:

- بيئة تطوير Java (JDK 8+).  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها من الموقع الرسمي [هنا](https://releases.aspose.com/page/java/).  

## استيراد الحزم
في مشروع Java الخاص بك، استورد حزم Aspose.Page اللازمة للبدء في إضافة كائنات شفافة. أضف السطور التالية في بداية ملف Java الخاص بك:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.Color;
```

الآن، لنقسم مثال الكود إلى عدة خطوات.

## الخطوة 1: تهيئة المستند
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize document
XpsDocument doc = new XpsDocument();
```
ابدأ بإعداد المستند وتحديد الدليل الذي سيُحفظ فيه مستند XPS الخاص بك.

## الخطوة 2: إنشاء كائنات شفافة
```java
// Just to demonstrate transparency
doc.addPath(doc.createPathGeometry("M120,0 H400 v1000 H120")).setFill(doc.createSolidColorBrush(Color.GRAY));
doc.addPath(doc.createPathGeometry("M300,120 h600 V420 h-600")).setFill(doc.createSolidColorBrush(Color.GRAY));
```
هنا، ننشئ مسارين رماديين سيعملان كخلفية للأشكال الشفافة التي سنضيفها لاحقًا.

## الخطوة 3: إضافة مسارات مملوءة
```java
// Create path with closed rectangle geometry
XpsPath path1 = doc.createPath(doc.createPathGeometry("M20,20 h200 v200 h-200 z"));
// Set blue solid brush to fill path1
path1.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add it to the current page
XpsPath path2 = doc.add(path1);
```
في هذه الخطوة ننشئ مستطيلًا أزرقًا صلبًا ونضعه على الصفحة. سيتراكب هذا المستطيل لاحقًا بأشكال شفافة لتوضيح التأثير.

## الخطوة 4: معالجة الشفافية
```java
// path1 and path2 are the same as long as path1 hasn't been placed inside any other element
path2.setFill(doc.createSolidColorBrush(Color.GREEN));
// Now add path2 once again. Now path2 has a parent, so path3 won't be the same as path2.
XpsPath path3 = doc.add(path2);
path3.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 0, 300));
path3.setFill(doc.createSolidColorBrush(Color.RED));
```
هنا نغيّر لون تعبئة المسار المكرر ونطبق تحويل ترجمة. يوضح هذا كيف تتفاعل الشفافية عندما تشترك الكائنات في عنصر أب مشترك.

## الخطوة 5: استنساخ وتعديل المسارات
```java
// Create new path4 with path2's geometry
XpsPath path4 = doc.addPath(path2.getData());
path4.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 300, 0));
path4.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add path4 once again.
XpsPath path5 = doc.add(path4);
path5.setRenderTransform(path5.getRenderTransform().deepClone());
path5.getRenderTransform().translate(0, 300);
path5.getFill().setOpacity(0.8f);
```
نستنسخ مسارًا موجودًا، ننقله، ونضبط التعتيم إلى 0.8 (80 % معتم). تُظهر هذه الخطوة كيف يمكنك إعادة استخدام الهندسة مع تخصيص الشفافية لكل نسخة.

## الخطوة 6: حفظ المستند
```java
// Save the modified document
doc.save(dataDir + "WorkingWithTransparency_out.xps");
```
أخيرًا، نقوم بحفظ ملف XPS. افتح الملف الناتج في أي عارض XPS لتشاهد الشفافية المتعددة الطبقات تعمل.

## المشكلات الشائعة والنصائح
- **التعتيم غير مرئي؟** تأكد من أنك تستخدم فرشاة تدعم التعتيم (مثل `createSolidColorBrush`).  
- **التحويل غير مطبق؟** تحقق من أنك تستدعي `setRenderTransform` **قبل** إضافة المسار إلى المستند.  
- **نصيحة الأداء:** أعد استخدام كائنات الهندسة عند إنشاء أشكال مشابهة كثيرة لتقليل استهلاك الذاكرة.

## الأسئلة المتكررة
### س: هل يمكنني تطبيق الشفافية على أشكال أخرى غير المستطيلات؟
ج: نعم، يمكنك تطبيق الشفافية على أشكال مختلفة باستخدام الهندسات المتوفرة.  
### س: كيف يمكنني التحكم في مستوى الشفافية لكائن؟
ج: اضبط خاصية `opacity` للتعبئة للتحكم في مستوى الشفافية.  
### س: هل Aspose.Page مناسب لإنشاء مستندات احترافية؟
ج: بالتأكيد! يوفر Aspose.Page ميزات قوية لمعالجة المستندات بشكل احترافي.  
### س: هل يمكن دمج Aspose.Page مع مكتبات Java أخرى؟
ج: نعم، يمكن دمج Aspose.Page بسلاسة مع مكتبات Java أخرى لتوسيع الوظائف.  
### س: أين يمكنني العثور على أمثلة إضافية ودعم لـ Aspose.Page؟
ج: زر [منتدى Aspose.Page Java](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع واستكشف الوثائق [هنا](https://reference.aspose.com/page/java/).

---

**آخر تحديث:** 2026-01-02  
**تم الاختبار مع:** Aspose.Page for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}