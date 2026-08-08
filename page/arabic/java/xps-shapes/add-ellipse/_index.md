---
date: 2026-04-24
description: تعلم كيفية إنشاء مستند XPS بلغة Java باستخدام إهليلج بتدرج دائري. يوضح
  هذا الدليل خطوة بخطوة كيفية ضبط سمك الخط وتعريف هندسة المسار باستخدام Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: إضافة إهليلج في Java XPS
second_title: Aspose.Page Java API
title: إنشاء مستند XPS بلغة Java – إضافة إهليلج بتدرج شعاعي
url: /ar/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إهليلج متدرج شعاعي باستخدام Aspose.Page

## المقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية **create XPS document Java** باستخدام إهليلج متدرج شعاعي جميل باستخدام Aspose.Page for Java. Aspose.Page هي مكتبة قوية تُجرد تفاصيل XPS منخفضة المستوى، مما يتيح لك التركيز على التصميم بدلاً من تعقيدات تنسيق الملف. في نهاية هذا الدليل ستحصل على ملف XPS جاهز للاستخدام يمكنك تضمينه في التقارير، الفواتير، أو أي سير عمل لإنشاء المستندات.

## إجابات سريعة
- **ما الذي ينتجه هذا الكود؟** ملف XPS من صفحة واحدة يحتوي على إهليلج مَحدَّد بمتدرج شعاعي متعدد الألوان.  
- **ما هو الـ API الأساسي المستخدم؟** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, إلخ).  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** ترخيص مؤقت يعمل للتقييم؛ ترخيص كامل مطلوب للإنتاج.  
- **ما هي الخصائص الرئيسية التي نحددها؟** فرشاة الحد (متدرج شعاعي)، طريقة الانتشار، نقاط التدرج، وسمك الحد.  
- **هل يمكنني تغيير حجم الإهليلج؟** نعم – عدل سلسلة هندسة المسار أو إحداثيات فرشاة التدرج.

## ما هو “create XPS document Java”؟
إنشاء مستند XPS في Java يعني توليد ملف XML Paper Specification (XPS) برمجيًا — وهو تنسيق مستند ثابت التخطيط مشابه لـ PDF — مباشرةً من كود Java. توفر Aspose.Page نموذج كائنات عالي المستوى (`XpsDocument`, `XpsCanvas`, إلخ) يُجرد ترميز XML، مما يجعل العملية بسيطة كالتعامل مع كائنات Java القياسية.

## لماذا نستخدم إهليلجًا متدرجًا شعاعيًا؟
يمنح المتدرج الشعاعي إحساسًا ثلاثي الأبعاد، وهو مثالي لتسليط الضوء البصري، الشعارات، أو العناصر الزخرفية في التقارير. مقارنةً بحدّ بلون ثابت، يضيف المتدرج عمقًا دون زيادة حجم الملف بشكل كبير، ويحافظ تنسيق XPS على جودة المتجهات لأي تكبير أو تصغير.

## المتطلبات المسبقة
- مجموعة تطوير جافا (JDK) مثبتة على جهازك.
- مكتبة Aspose.Page for Java تم تنزيلها. يمكنك الحصول عليها [هنا](https://releases.aspose.com/page/java/).
- محرر كود من اختيارك (Eclipse، IntelliJ، إلخ) لكتابة وتنفيذ كود Java.

## استيراد الحزم
تأكد من استيراد الحزم اللازمة في مشروع Java الخاص بك لاستخدام Aspose.Page. أضف عبارات الاستيراد التالية إلى أعلى ملف Java الخاص بك:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## الخطوة 1: إعداد دليل المستند
حدد المسار إلى دليل المستند حيث سيتم حفظ ملف XPS:

```java
String dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء مستند XPS
ابدأ مستند XPS جديد باستخدام الكود التالي:

```java
XpsDocument doc = new XpsDocument();
```

## الخطوة 3: تعريف نقاط التدرج الشعاعي
أنشئ قائمة بنقاط التدرج للمتدرج الشعاعي المحدد بالإهليلج:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## الخطوة 4: إنشاء هندسة المسار
عرّف إهليلجًا متدرجًا شعاعيًا باستخدام هندسة المسار:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## الخطوة 5: إضافة لوحة رسم (Canvas) والمسار
أضف لوحة رسم جديدة إلى المستند وأرفق المسار بالهندسة المحددة:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## الخطوة 6: تعيين الحد والمتدرج
قم بتكوين حد المسار باستخدام فرشاة متدرج شعاعي:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## الخطوة 7: تعيين سمك الحد
حدد **set stroke thickness** للمسار:

```java
path.setStrokeThickness(12f);
```

## الخطوة 8: حفظ المستند
احفظ ملف XPS الناتج:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

تهانينا! لقد أضفت بنجاح إهليلجًا مَحدَّدًا بمتدرج شعاعي أثناء **creating an XPS document Java** باستخدام Aspose.Page.

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| **الإهليلج يبدو مسطحًا** | استخدام `XpsSpreadMethod.Pad` بدلاً من `Reflect` | غيّر طريقة الانتشار إلى `XpsSpreadMethod.Reflect` كما هو موضح في الخطوة 6. |
| **لا يوجد ملف إخراج** | `dataDir` يشير إلى مجلد غير موجود | تأكد من وجود المجلد أو استخدم مسارًا مطلقًا. |
| **ألوان المتدرج غير صحيحة** | ترتيب نقاط التدرج غير صحيح | تحقق من أن قيم `offset` (0 → 1) تزداد بشكل متسلسل. |
| **أخطاء تجميع** | عدم وجود ملفات JAR الخاصة بـ Aspose.Page في مسار الفئة | أضف `aspose-page-xx.jar` إلى تبعيات مشروعك. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java مع مكتبات Java أخرى؟**  
**ج:** نعم، يمكن دمج Aspose.Page for Java مع مكتبات Java الأخرى بسلاسة.

**س: هل Aspose.Page مناسب لمعالجة المستندات على نطاق واسع؟**  
**ج:** بالتأكيد! تم تصميم Aspose.Page للتعامل مع معالجة المستندات على نطاق واسع بكفاءة.

**س: أين يمكنني العثور على المزيد من البرامج التعليمية والأمثلة لـ Aspose.Page for Java؟**  
**ج:** قم بزيارة [توثيق Aspose.Page for Java](https://reference.aspose.com/page/java/) للحصول على برامج تعليمية شاملة وأمثلة.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
**ج:** يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل هناك منتديات مجتمع لمناقشات Aspose.Page؟**  
**ج:** نعم، انضم إلى [منتدى مجتمع Aspose.Page](https://forum.aspose.com/c/page/39) للتفاعل مع المطورين الآخرين والحصول على المساعدة.

---

**آخر تحديث:** 2026-04-24  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}