---
date: 2025-12-25
description: تعلم كيفية إضافة تدرج عمودي في Java XPS باستخدام Aspose.Page. اتبع هذا
  الدليل خطوة بخطوة لتعزيز الجاذبية البصرية لمستندك.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: كيفية إضافة تدرج عمودي في Java XPS
url: /ar/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تدرج عمودي في Java XPS

## المقدمة
في هذا الدرس ستكتشف **كيفية إضافة تدرج عمودي** إلى مستندات XPS عند العمل مع Java. يمكن أن يُحسّن تطبيق التدرج العمودي بشكل كبير من التأثير البصري لتقاريرك، فواتيرك، أو أي محتوى قابل للطباعة. سنستعرض كل خطوة، من إعداد المشروع إلى حفظ ملف XPS النهائي، باستخدام مكتبة Aspose.Page for Java القوية.

## إجابات سريعة
- **ماذا يفعل التدرج العمودي؟** يخلق انتقالًا سلسًا للألوان من أعلى إلى أسفل الشكل.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (قابلة للتنزيل من الموقع الرسمي).  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل هذا متوافق مع Java 8+؟** نعم، تدعم الـ API Java 8 والإصدارات اللاحقة.  
- **كم من الوقت تستغرق عملية التنفيذ؟** عادةً أقل من 10 دقائق بمجرد إعداد البيئة.

## المتطلبات المسبقة
قبل أن نغوص في الكود، تأكد من أن لديك ما يلي:

- بيئة تطوير Java تعمل (JDK 8 أو أحدث).  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها من [هنا](https://releases.aspose.com/page/java/).  
- فهم أساسي لمفاهيم برمجة Java.  

## استيراد الحزم
ابدأ باستيراد الحزم اللازمة لمشروع Java الخاص بك. تأكد من إضافة مكتبة Aspose.Page for Java إلى مسار الفئة (classpath) الخاص بمشروعك.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## الخطوة 1: تهيئة المستند
ابدأ بإنشاء مستند XPS جديد. سيحتوي هذا الكائن على جميع عناصر الرسم التي ستضيفها لاحقًا.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## الخطوة 2: إنشاء مسار بتدرج عمودي
بعد ذلك، عرّف مسارًا مستطيلًا وطبق تدرجًا خطيًا عموديًا. تحدد نقاط التوقف في التدرج الألوان ومواقعها على المحور العمودي.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## الخطوة 3: حفظ المستند
أخيرًا، اكتب ملف XPS إلى القرص. سيحتوي الملف الناتج على المستطيل المملوء بالتدرج العمودي الذي عرّفته.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

تهانينا! لقد تعلمت بنجاح **كيفية إضافة تدرج عمودي** إلى مستند XPS باستخدام Java وAspose.Page.

## لماذا تستخدم تدرجًا عموديًا؟
- **تحسين الجمالية:** التدرجات تضيف عمقًا ومظهرًا حديثًا للأشكال الثابتة.  
- **اتساق العلامة التجارية:** مطابقة ألوان الشركة بسلاسة عبر الصفحات.  
- **تخصيص سهل:** تغيير الألوان أو مواضع التوقف دون إعادة تصميم الرسومات.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها
- **التدرج غير مرئي:** تحقق من أن نقطتي البداية والنهاية لـ `LinearGradientBrush` تم تعيينهما بشكل صحيح لتوجيه عمودي.  
- **الملف غير محفوظ:** تأكد من أن `dataDir` يشير إلى مجلد قابل للكتابة وأن لديك صلاحية كتابة الملفات.  
- **المكتبة غير موجودة:** تحقق مرة أخرى من أن ملف JAR الخاص بـ Aspose.Page مضمّن في مسار بناء مشروعك.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟**  
ج: نعم، Aspose.Page for Java متاح للاستخدام التجاري. يمكنك شراؤه [هنا](https://purchase.aspose.com/buy).

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page for Java؟**  
ج: الوثائق متاحة [هنا](https://reference.aspose.com/page/java/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل تحتاج إلى مساعدة أو لديك أسئلة؟**  
ج: زر منتدى مجتمع Aspose.Page [هنا](https://forum.aspose.com/c/page/39).

---

**آخر تحديث:** 2025-12-25  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (الأحدث وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}