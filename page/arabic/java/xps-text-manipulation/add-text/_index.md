---
date: 2026-04-24
description: تعلم كيفية إضافة نص XPS في جافا باستخدام Aspose.Page – دليل خطوة بخطوة
  لإنشاء مستندات XPS، وإضافة النص، وحفظ ملفات XPS بسهولة.
keywords:
- how to add xps
- create xps document
- aspose.page add text
linktitle: إضافة نص في Java XPS
second_title: Aspose.Page Java API
title: كيفية إضافة نص XPS في جافا – دليل Aspose.Page
url: /ar/java/xps-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة نص XPS في Java – دليل Aspose.Page

## مقدمة
إذا كنت بحاجة إلى **how to add XPS** نص برمجيًا، فإن Aspose.Page for Java يزودك بواجهة برمجة تطبيقات نظيفة وعالية الأداء للعمل مع ملفات XPS (XML Paper Specification). في هذا الدليل سنستعرض إنشاء مستند XPS، وإدراج نص منسق، وحفظ النتيجة — كل ذلك باستخدام كود مختصر وسهل المتابعة. سواءً كنت تبني محرك تقارير، أو تولد فواتير، أو تحتاج ببساطة إلى وضع نص فوق صفحة، فإن هذه الخطوات ستمكنك من البدء بسرعة.

## إجابات سريعة
- **ما هي المكتبة الأفضل للتعامل مع XPS في Java؟** Aspose.Page for Java.
- **هل يمكنني إنشاء وحفظ ملفات XPS بدون ترخيص؟** تجربة مجانية تعمل للتقييم؛ يلزم وجود ترخيص للإنتاج.
- **ما هي بيئات التطوير المتكاملة المدعومة؟** IntelliJ IDEA, Eclipse, NetBeans, أو أي بيئة تدعم Java.
- **كم عدد أسطر الكود المطلوبة لإضافة نص بسيط؟** حوالي 10 أسطر بالإضافة إلى الإعداد.
- **هل يمكن تنسيق الخط؟** نعم – يمكنك ضبط عائلة الخط، الحجم، النمط، واللون.

## ما هو XPS ولماذا إضافة نص؟
XPS (XML Paper Specification) هو تنسيق مستند ثابت من مايكروسوفت، مشابه لـ PDF لكنه مبني على XML. إضافة نص إلى ملف XPS شائعة عندما تحتاج إلى وضع دقيق، مثل الملصقات، العلامات المائية، أو البيانات الديناميكية في التقارير. باستخدام Aspose.Page يمكنك التعامل مع XPS دون الحاجة إلى التعامل مع هياكل XML منخفضة المستوى.

## لماذا تستخدم Aspose.Page لإضافة نص XPS؟
- **تحكم كامل** في تموضع الحروف، أنماط الخط، والفرش.
- **بدون تبعيات خارجية** – API جافا نقي.
- **دقة عالية** في العرض تحافظ على التخطيط عبر المنصات.
- **توثيق شامل** وكود أمثلة لتسهيل البدء السريع.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك:

- **Java Development Kit (JDK)** – نسخة حديثة (8 أو أعلى) مثبتة.
- **Aspose.Page for Java** – قم بتنزيل المكتبة من الموقع الرسمي [هنا](https://releases.aspose.com/page/java/).
- **بيئة تطوير Java** – IntelliJ IDEA، Eclipse، أو أي محرر تفضله.

## استيراد الحزم
ابدأ باستيراد الفئات التي ستحتاجها للتعامل مع XPS:

```java
import java.awt.Color;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
```

## الخطوة 1: تعيين دليل المستند (إنشاء ملف xps)
حدد المكان الذي سيُحفظ فيه ملف XPS المُولد:

```java
String dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء مستند XPS (إنشاء مستند xps)
إنشاء نسخة جديدة من مستند XPS فارغ:

```java
XpsDocument doc = new XpsDocument();
```

## الخطوة 3: إنشاء فرشاة لتنسيق النص
تحدد الفرشاة ذات اللون الصلب لون النص. هنا نستخدم اللون الأسود:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
```

## الخطوة 4: إضافة الحروف – النص الفعلي (aspose.page add text)
أضف النص الذي تريد ظهوره في المستند. طريقة `addGlyphs` تسمح لك بتحديد الخط، الحجم، النمط، والإحداثيات الدقيقة:

```java
XpsGlyphs glyphs = doc.addGlyphs("Arial", 12, XpsFontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.setFill(textFill);
```

## الخطوة 5: حفظ مستند XPS الناتج (حفظ ملف xps)
أخيرًا، احفظ المستند على القرص:

```java
doc.save(dataDir + "AddText_out.xps");
```

كرر خطوة **Add Glyphs** حسب الحاجة لإدراج أسطر إضافية، تغيير الخطوط، أو تعديل المواقع.

## المشكلات الشائعة ونصائح احترافية
- **إحداثيات غير صحيحة:** يستخدم XPS نظام إحداثيات يُقاس بالنقاط (1/72 بوصة). عدّل قيم `x` و `y` لتحديد موقع النص بدقة.
- **الخط غير موجود:** تأكد من تثبيت اسم الخط (مثال: “Arial”) على الجهاز الذي يشغل الكود.
- **استثناء الترخيص:** بدون ترخيص صالح، قد يحتوي XPS المُولد على علامة مائية. قم بتطبيق الترخيص مبكرًا في التطبيق لتجنب ذلك.

## الأسئلة المتكررة

### هل Aspose.Page متوافق مع جميع بيئات تطوير Java؟
نعم، Aspose.Page يعمل مع بيئات تطوير Java الشائعة، بما في ذلك IntelliJ IDEA و Eclipse.

### هل يمكنني تطبيق أنماط خط مختلفة على النص المضاف؟
بالطبع! استخدم `XpsFontStyle.Bold`، `Italic`، أو اجمع بين الأنماط عند استدعاء `addGlyphs`.

### أين يمكنني العثور على أمثلة إضافية وتوثيق لـ Aspose.Page؟
استكشف التوثيق الشامل [هنا](https://reference.aspose.com/page/java/).

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### كيف أحصل على ترخيص مؤقت لـ Aspose.Page؟
احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل يمكنني تضمين صور مع النص؟**  
ج: نعم – استخدم كائنات `XpsImage` جنبًا إلى جنب مع الحروف لإنشاء تخطيطات غنية.

**س: هل يدعم Aspose.Page الأحرف Unicode؟**  
ج: يدعم Unicode بالكامل، مما يتيح لك إضافة نص بأي لغة.

**س: ما هو إصدار Aspose.Page المستخدم في الاختبار؟**  
ج: تم اختبار الكود باستخدام Aspose.Page 23.12 for Java.

---

**آخر تحديث:** 2026-04-24  
**تم الاختبار مع:** Aspose.Page 23.12 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}