---
date: 2026-03-05
description: تعلم كيفية إضافة شبكة باستخدام Visual Brush في Java مع Aspose.Page. اتبع
  دليلًا خطوة بخطوة لتعزيز مظهر المستند بسهولة.
linktitle: Add Grid using Visual Brush in Java
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
إذا كنت تبحث عن **كيفية إضافة شبكة** إلى المستندات التي تم إنشاؤها باستخدام Java، فإن ميزة الفرشاة البصرية في Aspose.Page تجعل الأمر بسيطًا بشكل مفاجئ. في هذا البرنامج التعليمي سنستعرض كل خطوة، نشرح لماذا تُعد الفرشاة البصرية مثالية لأنماط الشبكة، ونُظهر لك مثالًا كاملاً قابلاً للتنفيذ.

## إجابات سريعة
- **ما هي الفرشاة البصرية؟** عنصر بصري قابل لإعادة الاستخدام يمكن تكراره أو تمديده لملء مساحة.  
- **لماذا تستخدم شبكة؟** تساعد الشبكات في تنظيم التخطيطات، إنشاء أنماط خلفية، أو إبراز أقسام في مستندات XPS.  
- **المتطلبات المسبقة؟** Java JDK، Aspose.Page for Java، وفهم أساسي لرسومات Java.  
- **كم من الوقت تستغرق العملية؟** حوالي 10‑15 دقيقة بمجرد إعداد المكتبة.  
- **هل يمكنني تخصيص الألوان؟** نعم – يمكنك التحكم بألوان التعبئة، الشفافية، وحجم البلاطة مباشرةً في الشيفرة.

## لماذا تستخدم الفرشاة البصرية لإضافة شبكة؟
تتيح لك الفرشاة البصرية تعريف عنصر بصري صغير ("البلاطة") مرة واحدة ثم تكراره عبر أي شكل. هذا النهج فعال من حيث الذاكرة ويحافظ على نظافة الشيفرة، خاصةً عندما تحتاج إلى تطبيق النمط نفسه على عدة قماشات.

## المتطلبات المسبقة
قبل أن نغوص في الشيفرة، تأكد من أن لديك المتطلبات المسبقة التالية:
- فهم أساسي لبرمجة Java.  
- مكتبة Aspose.Page مثبتة. يمكنك تنزيلها من [توثيق Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- مجموعة تطوير Java (JDK) مثبتة على جهازك.

## استيراد الحزم
تأكد من استيراد الحزم اللازمة في مشروع Java الخاص بك:
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

### الخطوة 1: إعداد مشروعك
أولاً، أنشئ كائن `XpsDocument` وحدد المجلد الذي سيتم حفظ الناتج فيه.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### الخطوة 2: إنشاء فرشاة بصرية لشبكة باللون الأرجواني
نقوم بإنشاء بلاطة صغيرة باللون الأرجواني سيتم تكرارها. يحدد شكل المسار هندسة البلاطة.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### الخطوة 3: تعريف الهندسة لفرشاة بصرية شبكة باللون الأرجواني
هنا نصف المنطقة التي ستستقبل الفرشاة المتكررة.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### الخطوة 4: إنشاء قماش جديد
يُضاف قماش جديد إلى المستند، ونطبق تحويل إزاحة حتى تظهر الشبكة في الموضع المطلوب.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### الخطوة 5: إضافة شبكة إلى القماش
الآن نقوم بربط الفرشاة البصرية بالهندسة وتعيين وضع التكرار.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### الخطوة 6: إضافة مستطيل أحمر شفاف
لتوضيح الطبقات، نضع مستطيل أحمر شبه شفاف فوق الشبكة.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### الخطوة 7: حفظ مستند XPS الناتج
أخيرًا، احفظ ملف XPS على القرص.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

اتبع هذه الخطوات، وستتمكن من إضافة شبكة جذابة بصريًا باستخدام الفرشاة البصرية في تطبيق Java الخاص بك مع Aspose.Page.

## حالات الاستخدام الشائعة
- **خلفيات التقارير:** إضافة أنماط شبكة خفيفة إلى التقارير المالية أو الهندسية لتحسين القابلية للقراءة.  
- **قوالب التصميم:** إنشاء قوالب صفحات قابلة لإعادة الاستخدام حيث تتكرر نفس الشبكة عبر صفحات متعددة.  
- **إبراز الأقسام:** وضع شبكات ملونة لتسليط الضوء على مناطق معينة في المستند.

## المشكلات الشائعة والحلول
| Issue | Solution |
|-------|----------|
| **تظهر الشبكة مشوهة** | تحقق من أن `TileMode` مضبوط على `XpsTileMode.Tile` وأن مستطيلات المصدر والوجهة لها نفس الحجم. |
| **الألوان غير صحيحة** | تأكد من استخدام قيم RGBA الصحيحة عند إنشاء فرشاة اللون الصلب (`createColor(alpha, red, green, blue)`). |
| **لم يتم حفظ المستند** | تحقق من أن `dataDir` يشير إلى مجلد قابل للكتابة موجود وأن لديك أذونات نظام الملفات المناسبة. |

## الخاتمة
تهانينا! لقد تعلمت **كيفية إضافة شبكة** باستخدام الفرشاة البصرية في Aspose.Page في Java. تمنحك هذه التقنية تحكمًا دقيقًا في عرض الأنماط مع الحفاظ على نظافة الشيفرة وسهولة صيانتها.

## الأسئلة المتكررة
### هل Aspose.Page مناسبة لإنشاء مستندات احترافية؟
نعم، Aspose.Page مكتبة قوية صُممت لإنشاء مستندات احترافية في Java.

### هل يمكنني تخصيص ألوان الشبكة باستخدام الفرشاة البصرية؟
بالطبع! تتيح لك الفرشاة البصرية الرسم بألوان مختلفة، مما يوفر مرونة في التخصيص.

### أين يمكنني العثور على دعم إضافي لـ Aspose.Page؟
قم بزيارة [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع والنقاشات.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page؟
نعم، يمكنك الوصول إلى [النسخة التجريبية المجانية](https://releases.aspose.com/) لاستكشاف ميزات Aspose.Page.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟
احصل على [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-05  
**تم الاختبار مع:** Aspose.Page for Java (latest release)  
**المؤلف:** Aspose  

---