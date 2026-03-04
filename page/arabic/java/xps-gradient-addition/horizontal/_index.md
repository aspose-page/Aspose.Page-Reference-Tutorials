---
date: 2025-12-25
description: تعلم كيفية إضافة تدرج لوني إلى مستندات XPS في جافا باستخدام Aspose.Page
  وكيفية تخصيص نقاط التدرج للحصول على تأثيرات أفقية مذهلة.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: كيفية إضافة تدرج – التدرج الأفقي في Java XPS
url: /ar/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تدرج – تدرج أفقي في Java XPS

## المقدمة
مرحبًا بك في هذا الدليل خطوة بخطوة حول **كيفية إضافة تدرج** إلى مستند XPS باستخدام Java. في هذا البرنامج التعليمي ستتعلم كيفية إضافة تدرج أفقي، ولماذا هو مهم لللمسة البصرية، وكيفية **تخصيص نقاط التدرج** للتحكم الدقيق في الألوان. تجعل Aspose.Page for Java العمل مع مستندات XPS (XML Paper Specification) بسيطًا، مما يتيح لك التركيز على التصميم بدلاً من معالجة الملفات على مستوى منخفض.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **أي نسخة من Java تعمل؟** أي بيئة تشغيل Java 8+  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج  
- **هل يمكنني تغيير اتجاه التدرج؟** نعم – فقط عدل نقاط البداية/النهاية للفرشاة الخطية  
- **هل يمكن إضافة عدة تدرجات؟** بالتأكيد – كرر خطوات إنشاء المسار بفرش مختلفة  

## ما هو التدرج الأفقي في XPS؟
التدرج الأفقي هو انتقال سلس للألوان من اليسار إلى اليمين عبر الشكل. في XPS يتم تمثيله بفرشاة تدرج خطية تقوم بالاستيفاء بين **نقاط التدرج** المحددة. يُستخدم هذا التأثير البصري عادةً للبانرات، الأزرار، وتعبئة الخلفيات.

## لماذا تستخدم Aspose.Page for Java؟
- **دعم كامل لـ XPS** – إنشاء، تعديل، وعرض دون أدوات طرف ثالث.  
- **API بسيط** – كائنات عالية المستوى مثل `XpsDocument`، `XpsPath`، و `XpsGradientBrush` تخفي تعقيد XML.  
- **الأداء** – مُحسّن للمستندات الكبيرة ومعالجة الدُفعات.  

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك:

1. **بيئة تطوير Java** – قم بتثبيت أحدث JDK من [java.com](https://www.java.com).  
2. **مكتبة Aspose.Page for Java** – حمّل ملف JAR من [توثيق Aspose.Page for Java](https://reference.aspose.com/page/java/).  

## استيراد الحزم
ابدأ باستيراد الفئات اللازمة. هذه الاستيرادات تمنحك الوصول إلى إنشاء المستندات، معالجة التدرجات، والهندسة الأساسية.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## الخطوة 1: تهيئة مستند XPS
أنشئ كائن `XpsDocument` جديد وحدد المجلد الذي تريد حفظ النتيجة فيه.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## الخطوة 2: إنشاء تدرج أفقي
عرّف قائمة من **نقاط التدرج** التي تتحكم في اللون وموقع كل نقطة انتقال. المثال أدناه يبني تدرجًا شبيهًا بالقوس قزح نابضًا.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### كيفية تخصيص نقاط التدرج
- **اللون** – استخدم `doc.createColor(alpha, red, green, blue)` لتعيين أي قيمة ARGB.  
- **الموقع** – الوسيط الثاني (`float` بين `0` و `1`) يحدد مكان ظهور النقطة على خط التدرج. عدّل هذه القيم لتحريك الألوان إلى اليسار أو اليمين.

## الخطوة 3: إضافة مسار مع التدرج
أنشئ مسارًا مستطيلًا، طبّق تحويلًا إذا لزم الأمر، واملأه بفرشاة التدرج الخطي. تستخدم الفرشاة نقطتين (`(10,0)` إلى `(228,0)`) لإنتاج تأثير أفقي.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**نصيحة احترافية:** إعادة استخدام نفس قائمة `stops` لعدة مسارات يمكن أن يحسن الأداء، لكن تذكّر أن تقوم بـ `clear()` قبل إضافة نقاط جديدة.

## الخطوة 4: حفظ المستند
احفظ ملف XPS على القرص. يمكنك الآن فتحه بأي عارض XPS لرؤية التدرج الأفقي يعمل.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| التدرج يظهر صلبًا | لم تُضاف نقاط تدرج أو لم تُضبط الفرشاة | تأكد من أن `path.setFill(...)` يستخدم `LinearGradientBrush` وأنه تم إضافة النقاط عبر `getGradientStops().addAll(stops)`. |
| الألوان باهتة | قيمة ألفا غير صحيحة (المعامل الأول) | استخدم `255` للألوان غير شفافة بالكامل ما لم تُرِد الشفافية. |
| حجم المسار غير صحيح | قيم مصفوفة التحويل خاطئة | قم بضبط معلمات المصفوفة (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## الأسئلة المتكررة

**س: هل يمكنني تطبيق عدة تدرجات في مستند XPS واحد؟**  
ج: نعم، يمكنك إضافة مسارات متعددة، كل منها بفرشاة تدرج خاصة، لإنشاء تصاميم طبقية معقدة.

**س: هل Aspose.Page متوافق مع أحدث إصدارات Java؟**  
ج: يتم تحديث Aspose.Page for Java بانتظام ويعمل مع Java 8 والإصدارات الأحدث.

**س: هل هناك أنواع أخرى من التدرجات متاحة في Aspose.Page؟**  
ج: بالإضافة إلى التدرجات الخطية، يدعم Aspose.Page أيضًا التدرجات الشعاعية للانتقالات اللونية الدائرية.

**س: هل يمكنني تخصيص ألوان ومواقع نقاط التدرج؟**  
ج: بالتأكيد! لديك التحكم الكامل في لون ARGB لكل نقطة وموقعها النسبي (نطاق 0‑1).

**س: هل هناك منتدى مجتمع لـ Aspose.Page يمكنني طلب المساعدة منه؟**  
ج: نعم، يمكنك زيارة [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع والحصول على المساعدة.

---

**آخر تحديث:** 2025-12-25  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}