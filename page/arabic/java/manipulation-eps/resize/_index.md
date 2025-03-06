---
title: قم بتغيير حجم ملفات EPS في Java باستخدام Aspose.Page
linktitle: تغيير حجم ملف EPS في جافا
second_title: Aspose.Page جافا API
description: تعرف على كيفية تغيير حجم ملفات EPS في Java بسهولة باستخدام Aspose.Page لـ Java. اتبع دليلنا الشامل للحصول على تعليمات خطوة بخطوة.
weight: 11
url: /ar/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتغيير حجم ملفات EPS في Java باستخدام Aspose.Page

## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول تغيير حجم ملفات EPS في Java باستخدام مكتبة Aspose.Page القوية. إذا كنت في حاجة إلى ضبط أبعاد صور EPS الخاصة بك برمجيًا، فأنت في المكان الصحيح. في هذا البرنامج التعليمي، سنستكشف خيارات تغيير الحجم المتنوعة، بما في ذلك النقاط والبوصات والمليمترات والنسب المئوية، مما يوفر لك المرونة التي تحتاجها لمتطلباتك المحددة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  Aspose.Page لمكتبة جافا. يمكنك تنزيله[هنا](https://releases.aspose.com/page/java/).
- الفهم الأساسي لبرمجة جافا.
## حزم الاستيراد
في مشروع Java الخاص بك، تأكد من حصولك على الواردات اللازمة لاستخدام وظائف Aspose.Page. هنا مثال:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
الآن، دعونا نقسم البرنامج التعليمي إلى خطوات متعددة لكل خيار تغيير الحجم:
## تغيير حجم EPS باستخدام النقاط
### الخطوة 1: إعداد دفق الإدخال
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### الخطوة 2: تهيئة كائن PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### الخطوة 3: استخراج الحجم الحالي لصورة EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### الخطوة 4: إنشاء دفق الإخراج
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### الخطوة 5: تغيير الحجم وحفظه بالنقاط
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## تغيير حجم EPS باستخدام بوصة
اتبع الخطوات المشابهة للمثال 1، مع استبدال "النقاط" بـ "البوصات" وضبط الحجم الجديد وفقًا لذلك.
## تغيير حجم EPS باستخدام ملليمتر
اتبع الخطوات المشابهة للمثال 1، مع استبدال "النقاط" بـ "المليمترات" وضبط الحجم الجديد وفقًا لذلك.
## تغيير حجم EPS باستخدام النسب المئوية
اتبع الخطوات المشابهة للمثال 1، مع استبدال "النقاط" بـ "النسب المئوية" وضبط الحجم الجديد وفقًا لذلك.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تغيير حجم ملفات EPS في Java باستخدام Aspose.Page. يوفر لك هذا الدليل خيارات متعددة الاستخدامات، مما يضمن أنه يمكنك تخصيص عملية تغيير الحجم لتلبية احتياجاتك المحددة.

## الأسئلة الشائعة
### هل يمكنني استخدام هذه المكتبة لتنسيقات الصور الأخرى؟
لا، Aspose.Page مصمم خصيصًا للتعامل مع ملفات PostScript وEPS.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ Java؟
نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على مساعدة ومناقشات إضافية؟
 قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع.
### كيف يمكنني الحصول على ترخيص مؤقت؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل هناك أي مشاريع نموذجية متاحة؟
 نعم، تحقق من الوثائق[هنا](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
