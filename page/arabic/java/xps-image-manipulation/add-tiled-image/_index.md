---
title: إضافة صورة متجانبة في Java XPS
linktitle: إضافة صورة متجانبة في Java XPS
second_title: Aspose.Page جافا API
description: اكتشف المعالجة السلسة لمستندات Java XPS باستخدام Aspose.Page. تعرّف على كيفية إضافة صور متجانبة بسهولة باستخدام هذا الدليل المفصّل خطوة بخطوة.
type: docs
weight: 11
url: /ar/java/xps-image-manipulation/add-tiled-image/
---
## مقدمة
في عالم تطوير Java الديناميكي، تتزايد الحاجة إلى معالجة المستندات وإنشاءها بشكل فعال. يظهر Aspose.Page for Java كأداة قوية توفر للمطورين القدرة على العمل مع مستندات XPS بسلاسة. يركز هذا البرنامج التعليمي على مهمة محددة – إضافة صورة متجانبة إلى مستند Java XPS.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Page لـ Java: قم بتنزيل Aspose.Page لـ Java وتثبيته من[موقع إلكتروني](https://releases.aspose.com/page/java/).
3. دليل المستندات الخاص بك: اختر أو قم بإنشاء دليل تريد حفظ مستند XPS الخاص بك فيه.
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة للاستفادة من وظائف Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
الآن، دعنا نقسم عملية إضافة صورة متجانبة إلى مستند Java XPS إلى خطوات واضحة يمكن التحكم فيها.
## الخطوة 1: قم بإعداد مشروعك
ابدأ بإعداد مشروع Java الخاص بك، مع التأكد من دمج Aspose.Page for Java بشكل صحيح.
## الخطوة 2: إنشاء مستند XPS
قم بتهيئة مستند XPS جديد باستخدام الكود التالي:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```
## الخطوة 3: تحديد مسار الصورة المتجانبة
حدد المسار إلى الصورة المتجانبة التي تريد إضافتها إلى مستند XPS.
## الخطوة 4: إضافة صورة متجانبة
استخدم مقتطف الكود أدناه لإضافة صورة متجانبة إلى مستند XPS:
```java
// صورة البلاط
// ملأ ImageBrush المستطيل في الجزء العلوي الأيمن أدناه
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## الخطوة 5: احفظ المستند
وأخيرًا، احفظ مستند XPS الناتج باستخدام الكود أدناه:
```java
// احفظ مستند XPS الناتج
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
كرر هذه الخطوات لدمج صورة متجانبة بسهولة في مستند Java XPS الخاص بك باستخدام Aspose.Page.
## خاتمة
يعمل Aspose.Page for Java على تبسيط عملية العمل مع مستندات XPS، مما يوفر للمطورين حلاً فعالاً لمعالجة المستندات. باتباع هذا الدليل خطوة بخطوة، يمكنك بسهولة إضافة صورة متجانبة إلى مستند Java XPS الخاص بك.

## الأسئلة الشائعة
### هل Aspose.Page متوافق مع جميع إصدارات Java؟
 تم تصميم Aspose.Page للعمل مع إصدارات Java المختلفة. ضمان التوافق عن طريق التحقق من الوثائق[هنا](https://reference.aspose.com/page/java/).
### هل يمكنني استخدام Aspose.Page للمشاريع التجارية؟
نعم، Aspose.Page يقدم تراخيص تجارية. شرائها[هنا](https://purchase.aspose.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، استكشف ميزات Aspose.Page مع الإصدار التجريبي المجاني[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على دعم المجتمع والمناقشات؟
 تفاعل مع مجتمع Aspose.Page على[المنتدى](https://forum.aspose.com/c/page/39).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟
 الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).