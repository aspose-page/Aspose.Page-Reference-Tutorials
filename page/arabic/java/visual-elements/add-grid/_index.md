---
date: 2025-12-18
description: تعلم كيفية إضافة شبكة وإضافة مستطيل شفاف في مستندات XPS باستخدام Java
  مع Aspose.Page. دليل خطوة بخطوة لحفظ مستند XPS بكفاءة.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: كيفية إضافة شبكة باستخدام فرشاة بصرية في جافا
url: /ar/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة شبكة باستخدام فرشاة بصرية في Java

## المقدمة
إذا كنت تبحث عن **كيفية إضافة شبكة** إلى مستندات XPS التي تُنشئها Java، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنرشدك إلى إضافة شبكة باستخدام فرشاة بصرية، وضع مستطيل شفاف فوقها، وأخيرًا **حفظ مستند XPS** باستخدام Aspose.Page Java API. في النهاية ستحصل على مظهر بصري مصقول يمكن إعادة استخدامه في التقارير، الفواتير، أو أي تطبيق يعتمد على المستندات.

## إجابات سريعة
- **ماذا تفعل الفرشاة البصرية؟** تقوم بطلاء مساحة محددة بمحتوى بصري قابل لإعادة الاستخدام، مثالي للأنماط المتكررة مثل الشبكات.  
- **هل يمكنني تغيير لون الشبكة؟** نعم – عدل إعدادات فرشاة اللون الصلب.  
- **كيف أضيف مستطيل شفاف فوق الشبكة؟** استخدم `setOpacity` على مسار مملوء بلون صلب.  
- **ما الطريقة التي تحفظ الملف؟** `doc.save(...)` تكتب ملف XPS إلى القرص.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت أو كامل للاستخدام في الإنتاج.

## ما هي شبكة الفرشاة البصرية؟
تتيح لك الفرشاة البصرية تعريف عنصر بصري صغير (نمط الشبكة) ثم تكراره عبر مساحة أكبر. هذه الطريقة أكثر كفاءة في الذاكرة مقارنة برسم كل خط على حدة وتمنحك تكرارًا مثاليًا على مستوى البكسل.

## لماذا نستخدم Aspose.Page لهذه المهمة؟
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **عروض عالية الدقة** – تحكم دقيق في الألوان، الشفافية، والتكرار.  
- **بدون تبعيات خارجية** – كل شيء يُدار عبر مكتبة Aspose.Page.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page مثبتة – يمكنك تحميلها من [توثيق Aspose.Page للـ Java](https://reference.aspose.com/page/java/).  
- JDK 8 أو أحدث مُثبت على جهاز التطوير الخاص بك.

## استيراد الحزم
أولاً، استورد الفئات المطلوبة حتى يعرف المترجم أين يجد الأنواع التي سنستخدمها:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد المشروع
أنشئ كائن `XpsDocument` جديد وحدد المجلد الذي تريد حفظ الملف الناتج فيه.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### الخطوة 2: إنشاء فرشاة بصرية لشبكة باللون الأرجواني
نعرّف شكلًا صغيرًا باللون الأرجواني سيتم تكراره عبر مساحة الشبكة.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### الخطوة 3: تعريف الهندسة لفرشاة الشبكة
قم بإعداد المنطقة المستطيلة التي ستستقبل العنصر البصري المتكرر.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### الخطوة 4: إنشاء لوحة رسم جديدة للمستند
أضف لوحة رسم إلى المستند وضعها في الموضع الذي ستظهر فيه الشبكة.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### الخطوة 5: إضافة الشبكة إلى لوحة الرسم
طبق الفرشاة البصرية على الهندسة، مفعلاً التكرار.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### الخطوة 6: إضافة مستطيل أحمر شفاف (ميزة ثانوية)
هنا نوضح **إضافة مستطيل شفاف** فوق الشبكة للتأكيد.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### الخطوة 7: حفظ مستند XPS الناتج
أخيرًا، اكتب المستند إلى القرص—هذه هي خطوة **حفظ مستند XPS**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

اتبع هذه الخطوات، وستحصل على شبكة بمظهر احترافي مع طبقة شفافة، كلها مُولدة برمجيًا.

## المشكلات الشائعة والنصائح

- **حجم البلاط غير صحيح:** تأكد من أن `Rectangle2D` المستخدم للفرشاة يطابق حجم التكرار المقصود؛ وإلا قد يتم تمديد النمط.  
- **الشفافية غير مطبقة:** تذكر استدعاء `setOpacity` على المسار الذي تريد جعله شفافًا؛ لن تؤثر على الفرشاة نفسها.  
- **الملف غير محفوظ:** تحقق من أن `dataDir` يشير إلى مجلد موجود وأن تطبيقك يمتلك صلاحيات الكتابة.

## الأسئلة المتكررة

**س: هل Aspose.Page مناسب لإنشاء مستندات احترافية؟**  
ج: نعم، Aspose.Page مكتبة قوية صُممت لإنشاء XPS وPDF عالية الجودة في Java.

**س: هل يمكنني تخصيص ألوان الشبكة باستخدام الفرشاة البصرية؟**  
ج: بالتأكيد! غيّر معلمات `createColor` في استدعاء `setFill` للفرشاة إلى أي قيم RGBA تحتاجها.

**س: أين يمكنني العثور على دعم إضافي لـ Aspose.Page؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على مساعدة المجتمع والإجابات الرسمية.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page؟**  
ج: نعم، يمكنك الوصول إلى [الإصدار التجريبي المجاني](https://releases.aspose.com/) لاستكشاف جميع الميزات قبل الشراء.

**س: كيف يمكنني الحصول على ترخيص مؤقت للاختبار؟**  
ج: احصل على [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) يعمل للتطوير والتقييم.

---

**آخر تحديث:** 2025-12-18  
**تم الاختبار مع:** Aspose.Page for Java 23.12 (الأحدث)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}