---
title: إضافة القطع الناقص التدرج الشعاعي مع Aspose.Page
linktitle: أضف القطع الناقص في Java XPS
second_title: Aspose.Page جافا API
description: استكشف الدليل التفصيلي خطوة بخطوة حول إضافة شكل بيضاوي متدرج نصف قطري محدد في Java XPS باستخدام Aspose.Page لـ Java. تعزيز إنشاء المستندات الخاصة بك دون عناء.
type: docs
weight: 10
url: /ar/java/xps-shapes/add-ellipse/
---
## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول إضافة شكل بيضاوي في Java XPS باستخدام Aspose.Page لـ Java. Aspose.Page هي مكتبة Java قوية تتيح للمطورين العمل مع مستندات XPS دون عناء. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء شكل بيضاوي محدد متدرج نصف قطري وحفظه كمستند XPS.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  تم تنزيل Aspose.Page لمكتبة Java. يمكنك الحصول عليه[هنا](https://releases.aspose.com/page/java/).
- محرر أكواد برمجية من اختيارك (Eclipse، IntelliJ، وما إلى ذلك) لكتابة كود Java وتنفيذه.
## حزم الاستيراد
تأكد من استيراد الحزم اللازمة إلى مشروع Java الخاص بك لاستخدام Aspose.Page. أضف عبارات الاستيراد التالية إلى أعلى ملف Java الخاص بك:
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
## الخطوة 1: إعداد دليل المستندات
حدد المسار إلى دليل المستند الخاص بك حيث سيتم حفظ مستند XPS:
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء مستند XPS
قم بتهيئة مستند XPS جديد باستخدام الكود التالي:
```java
XpsDocument doc = new XpsDocument();
```
## الخطوة 3: تحديد توقفات التدرج الشعاعي
قم بإنشاء قائمة بتوقفات التدرج للقطع الناقص المحدد بالتدرج الشعاعي:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## الخطوة 4: إنشاء هندسة المسار
تحديد شكل بيضاوي متدرج نصف قطري باستخدام هندسة المسار:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## الخطوة 5: إضافة قماش ومسار
أضف لوحة قماشية جديدة إلى المستند وألحق المسار بالهندسة المحددة:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## الخطوة 6: ضبط الحد والتدرج
قم بتكوين حد المسار باستخدام فرشاة متدرجة شعاعية:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## الخطوة 7: ضبط سمك السكتة الدماغية
حدد سمك حد المسار:
```java
path.setStrokeThickness(12f);
```
## الخطوة 8: احفظ المستند
احفظ مستند XPS الناتج:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
تهانينا! لقد نجحت في إضافة شكل بيضاوي متدرج نصف قطري في Java XPS باستخدام Aspose.Page لـ Java.
## خاتمة
في هذا البرنامج التعليمي، استكشفنا خطوات إنشاء مستند XPS باستخدام قطع ناقص متدرج نصف قطري جذاب بصريًا. يعمل Aspose.Page for Java على تبسيط معالجة مستندات XPS، مما يوفر للمطورين مجموعة أدوات قوية.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Page لـ Java مع مكتبات Java الأخرى؟
نعم، يمكن دمج Aspose.Page for Java مع مكتبات Java الأخرى بسهولة.
### هل Aspose.Page مناسب لمعالجة المستندات على نطاق واسع؟
قطعاً! تم تصميم Aspose.Page للتعامل مع معالجة المستندات واسعة النطاق بكفاءة.
### أين يمكنني العثور على المزيد من البرامج التعليمية والأمثلة لـ Aspose.Page لـ Java؟
 قم بزيارة[Aspose.Page لوثائق جافا](https://reference.aspose.com/page/java/)للحصول على دروس وأمثلة شاملة.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل توجد منتديات مجتمعية لمناقشات Aspose.Page؟
 نعم انضم الى[Aspose.Page منتدى المجتمع](https://forum.aspose.com/c/page/39) للتعامل مع المطورين الآخرين والحصول على المساعدة.