---
title: إضافة التدرج القطري في Java XPS
linktitle: إضافة التدرج القطري في Java XPS
second_title: Aspose.Page جافا API
description: تعرف على كيفية إضافة تدرج قطري مذهل إلى مستندات XPS الخاصة بك في Java باستخدام Aspose.Page. ارفع مستوى العرض المرئي الخاص بك دون عناء.
weight: 10
url: /ar/java/xps-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة التدرج القطري في Java XPS

## مقدمة
في عالم تطوير Java الذي يتطور باستمرار، يعد تحسين المظهر المرئي لمستندات XPS الخاصة بك أمرًا بالغ الأهمية. إحدى الطرق الفعالة لتحقيق ذلك هي دمج التدرجات القطرية. سيرشدك هذا البرنامج التعليمي خلال العملية باستخدام Aspose.Page لـ Java، مع توفير إرشادات خطوة بخطوة ومقتطفات التعليمات البرمجية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي لبرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Page لمكتبة جافا. يمكنك تنزيله[هنا](https://releases.aspose.com/page/java/).
- محرر أكواد برمجية مثل IntelliJ IDEA أو Eclipse.
## حزم الاستيراد
ابدأ باستيراد الحزم اللازمة لمشروع Java الخاص بك. في التعليمات البرمجية الخاصة بك، يمكنك إضافة الواردات التالية:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع Java جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وقم بتضمين مكتبة Aspose.Page في تبعيات مشروعك.
## الخطوة 2: تحديد دليل المستندات
قم بتعيين المسار إلى دليل المستند الخاص بك حيث سيتم حفظ ملف XPS:
```java
String dataDir = "Your Document Directory";
```
## الخطوة 3: إنشاء مستند XPS
تهيئة كائن XpsDocument جديد:
```java
XpsDocument doc = new XpsDocument();
```
## الخطوة 4: إضافة مسار التدرج القطري
أضف مسارًا إلى مستند XPS بتدرج قطري:
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```
## الخطوة 5: تحديد توقفات التدرج الخطي
قم بإعداد توقفات متدرجة خطية بألوان ومواضع محددة:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... كرر للألوان والمواضع الأخرى
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```
## الخطوة 6: تطبيق التدرج الخطي على المسار
قم بتطبيق التدرج الخطي على المسار المحدد مسبقًا:
```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## الخطوة 7: احفظ المستند
احفظ مستند XPS بالتدرج القطري المضاف:
```java
doc.save(dataDir + "LinearGradient.xps");
```
## خاتمة
تهانينا! لقد نجحت في إضافة تدرج قطري إلى مستند XPS الخاص بك باستخدام Aspose.Page لـ Java. يمكن لهذه الميزة الجذابة بصريًا تحسين العرض العام لمستنداتك.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.Page لـ Java مع أطر عمل Java الأخرى؟
تم تصميم Aspose.Page للتكامل بسلاسة مع أطر عمل Java المختلفة، مما يجعله خيارًا متعدد الاستخدامات لمشاريعك.
### س: هل هناك أي اعتبارات ترخيص لـ Aspose.Page؟
 نعم، تأكد من مراجعة تفاصيل الترخيص الموجودة على[Aspose.Page صفحة الشراء](https://purchase.aspose.com/buy).
### س: هل يمكنني تجربة Aspose.Page لـ Java قبل الشراء؟
 قطعاً! يمكنك استكشاف أ[نسخة تجريبية مجانية هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم أو التواصل مع مجتمع Aspose؟
 قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع وطلب المساعدة.
### س: هل هناك نص على التراخيص المؤقتة؟
 نعم يمكنك الحصول على[الترخيص المؤقت هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
