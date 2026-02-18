---
date: 2026-02-18
description: تعلم كيفية تعيين لون الطلاء وإنشاء إهليلج PostScript في Java باستخدام
  Aspose.Page. يوضح هذا الدليل كيفية تعبئة الإهليلج في Java، ورسم حدود الإهليلج، وتعيين
  سمك الخط.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: تعيين لون الطلاء لرسم إهليلج PostScript في جافا
url: /ar/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين لون الطلاء لرسم إهليلج PostScript في Java

## المقدمة
إذا كنت بحاجة إلى **تعيين لون الطلاء** أثناء رسم الرسومات المتجهية، فإن مكتبة Aspose.Page for Java تمنحك تحكمًا كاملاً في كل خط وتعبئة. في هذا الدرس ستكتشف كيفية **تعيين لون الطلاء**، **ملء إهليلج في Java**، و**رسم حدود الإهليلج** باستخدام نهج بسيط خطوة بخطوة. في النهاية، ستكون قادرًا على إضافة إهليلجات PostScript عالية الجودة إلى الفواتير، التقارير، أو أي مستند قابل للطباعة.

## إجابات سريعة
- **ما هي المكتبة الأفضل لرسم رسومات PostScript في Java؟** Aspose.Page for Java.  
- **هل يمكنني ملء إهليلج بلون صلب؟** نعم – استخدم `document.setPaint(Color.YOUR_COLOR)` قبل `fill`.  
- **كيف أرسم فقط حدود إهليلج؟** قم بتعيين اللون والحد، ثم استدعِ `document.draw(...)`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم ترخيص تجاري؛ يتوفر ترخيص مؤقت للاختبار.  
- **ما نسخة Java المدعومة؟** أي بيئة تشغيل Java 8+ تعمل مع إصدار Aspose.Page الحالي.

## ما هو إهليلج PostScript؟
إهليلج PostScript هو شكل متجهي يُحدد بواسطة مستطيل محيط. على عكس الصور النقطية، يمكن تكبيره دون فقدان الجودة، مما يجعله مثاليًا للطباعة عالية الدقة وتحويل PDF.

## لماذا تستخدم Aspose.Page لإنشاء إهليلج PostScript؟
- **تحكم كامل** في الرسومات الأولية (خطوط، منحنيات، إهليلجات).  
- **متعدد المنصات** – يعمل على Windows وLinux وmacOS.  
- **بدون تبعيات خارجية** – API جافا نقي، بدون كود أصلي.  
- **تكامل سهل** مع تطبيقات Java الحالية وأدوات البناء.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أن لديك:

1. بيئة تطوير Java فعّالة (JDK 8 أو أحدث).  
2. مكتبة Aspose.Page for Java مضافة إلى مشروعك. يمكنك تنزيلها **[هنا](https://releases.aspose.com/page/java/)**.  

## استيراد الحزم
في ملف مصدر Java الخاص بك، استورد الفئات المطلوبة للرسم وحفظ محتوى PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## كيفية تعيين لون الطلاء لإهليلج
تعيين لون الطلاء هو الخطوة الأولى قبل أي عملية تعبئة أو حد. تحدد طريقة `setPaint` اللون الذي سيُستخدم للأمر الرسم التالي.

### الخطوة 1: إعداد مستند PostScript
أنشئ تدفق إخراج، اضبط حجم الصفحة، وأنشئ كائن `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### الخطوة 2: كيفية ملء إهليلج – استخدم تعيين لون الطلاء
لـ **ملء إهليلج**، يجب أولاً استدعاء `setPaint` باللون المطلوب للتعبئة، ثم استدعاء `fill` مع كائن `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### الخطوة 3: رسم حدود الإهليلج وتعيين سمك الحد
بعد التعبئة، يمكنك تغيير اللون إلى لون مختلف، تعريف `BasicStroke` للتحكم في عرض الخط، ورسم حدود الإهليلج.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### الخطوة 4: إغلاق وحفظ المستند
أكمل الصفحة واكتب ملف PostScript إلى القرص.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

الآن لديك ملف PostScript يحتوي على إهليلجين—أحدهما مملوء بالبرتقالي والآخر بحد أحمر. لا تتردد في تجربة إحداثيات، أحجام، وألوان مختلفة لتتناسب مع احتياجات التصميم الخاصة بك.

## المشكلات الشائعة واستكشاف الأخطاء
- **مسار ملف غير صحيح** – تأكد من أن `dataDir` ينتهي بفاصل (`/` أو `\\`) المناسب لنظام التشغيل الخاص بك.  
- **ترخيص مفقود** – بدون ترخيص صالح، تعمل المكتبة في وضع التقييم وقد تضيف علامات مائية.  
- **اللون غير مطبق** – تذكر تعيين `document.setPaint(...)` *قبل* كل استدعاء `fill` أو `draw`؛ إعداد اللون لا يستمر عبر عمليات منفصلة تلقائيًا.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java مع مكتبات Java أخرى؟**  
ج: نعم، تم تصميم Aspose.Page for Java لتتكامل بسلاسة مع مكتبات Java الأخرى.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: احصل على ترخيص مؤقت **[هنا](https://purchase.aspose.com/temporary-license/)** لأغراض الاختبار.

**س: هل Aspose.Page مناسب للمشروعات التجارية؟**  
ج: بالتأكيد! زر **[هنا](https://purchase.aspose.com/buy)** لاستكشاف خيارات الترخيص للاستخدام التجاري.

**س: أين يمكنني طلب المساعدة أو مناقشة استفسارات متعلقة بـ Aspose.Page؟**  
ج: انضم إلى المجتمع في **[منتدى Aspose.Page](https://forum.aspose.com/c/page/39)** للمناقشات والمساعدة.

**س: هل هناك موارد مجانية لتعلم المزيد عن Aspose.Page for Java؟**  
ج: استخدم **[الإصدار التجريبي المجاني](https://releases.aspose.com/)** واستكشف الأمثلة في الوثائق.

## الخلاصة
Aspose.Page for Java يجعل من السهل **تعيين لون الطلاء**، **ملء إهليلج**، و**رسم حدود الإهليلج**—سواء كنت تحتاج إلى شكل مملوء بسيط أو رسم معقد بحدود. باستخدام الخطوات أعلاه يمكنك بسرعة إضافة رسومات متجهة ذات جودة احترافية إلى أي مستند قابل للطباعة. للمزيد من الاستكشاف—مثل دمج أشكال متعددة، تطبيق التدرجات، أو التحويل إلى PDF—ارجع إلى **[الوثائق الرسمية](https://reference.aspose.com/page/java/)**.

---

**آخر تحديث:** 2026-02-18  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}