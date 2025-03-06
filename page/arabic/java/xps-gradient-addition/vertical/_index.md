---
title: أضف التدرج الرأسي في Java XPS
linktitle: أضف التدرج الرأسي في Java XPS
second_title: Aspose.Page جافا API
description: تعرف على كيفية إضافة تدرج عمودي إلى مستندات Java XPS باستخدام Aspose.Page. تعزيز الجاذبية البصرية دون عناء. دليل خطوة بخطوة في الداخل.
weight: 12
url: /ar/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف التدرج الرأسي في Java XPS

## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية إضافة تدرج عمودي في Java XPS باستخدام Aspose.Page for Java. يمكن أن تؤدي إضافة التدرجات اللونية إلى مستندات XPS الخاصة بك إلى تحسين المظهر المرئي للمحتوى الخاص بك، مما يجعله أكثر جاذبية وإمتاعًا من الناحية الجمالية.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- بيئة تطوير جافا العاملة.
-  Aspose.Page لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/page/java/).
- الفهم الأساسي لبرمجة جافا.
## حزم الاستيراد
ابدأ باستيراد الحزم اللازمة لمشروع Java الخاص بك. تأكد من تضمين مكتبة Aspose.Page for Java في تبعيات مشروعك.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
        
// استيراد Aspose.Page لجافا
```
## الخطوة 1: تهيئة المستند
ابدأ بتهيئة مستند XPS. يؤدي هذا إلى تعيين الأساس لإضافة عناصر مثل المسارات والتدرجات إلى وثيقتك.
```java
// تهيئة المستند
XpsDocument doc = new XpsDocument();
```
## الخطوة 2: إنشاء مسار مع التدرج العمودي
الآن، دعونا ننشئ مسارًا بتدرج عمودي. يتضمن ذلك تحديد هندسة المسار وتحديد توقفات التدرج.
```java
// إنشاء مسار مع الهندسة
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// تحديد توقفات التدرج العمودي
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//قم بتطبيق التدرج الرأسي على المسار
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## الخطوة 3: احفظ المستند
أخيرًا، احفظ مستند XPS مع التدرج الرأسي المضاف إلى الدليل الذي تريده.
```java
// احفظ المستند
doc.save(dataDir + "VerticalGradient.xps");
```
تهانينا! لقد نجحت في إضافة تدرج عمودي إلى مستند Java XPS الخاص بك باستخدام Aspose.Page.
## خاتمة
يمكن أن يؤدي تحسين مستندات XPS الخاصة بك بالتدرجات إلى تحسين جاذبيتها المرئية بشكل كبير. يعمل Aspose.Page for Java على تبسيط هذه العملية، مما يسمح لك بإنشاء مستندات مذهلة بسهولة.

### الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Page لـ Java في المشاريع التجارية؟
 نعم، Aspose.Page for Java متاح للاستخدام التجاري. يمكنك شرائه[هنا](https://purchase.aspose.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ Java؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل تحتاج إلى مساعدة أو لديك أسئلة؟
 قم بزيارة مجتمع Aspose.Page[المنتدى](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
