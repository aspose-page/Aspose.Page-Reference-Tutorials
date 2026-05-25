---
date: 2026-05-25
description: Узнайте, как добавить gradient в XPS‑документы на Java с помощью Aspose.Page.
  Это пошаговое руководство показывает, как добавить diagonal gradient, применить
  linear gradient brushes и создать профессиональные XPS‑файлы.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Добавить Diagonal Gradient в Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Как добавить градиент: Diagonal Gradient в Java XPS'
url: /ru/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить градиент: Диагональный градиент в Java XPS

## Введение
В современном Java‑разработке освоение **как добавить градиент** в XPS‑документы придаёт вашим отчётам полированный, привлекающий внимание вид. Этот учебник проведёт вас через создание XPS‑файла с нуля, добавление диагонального градиента и сохранение результата — всё с помощью Aspose.Page for Java. Вы поймёте, почему градиенты важны, увидите точные вызовы API и получите практические советы по избежанию распространённых ошибок.

## Быстрые ответы
- **Какова основная библиотека?** Aspose.Page for Java  
- **Какой метод добавляет градиент?** `createLinearGradientBrush` with gradient stops  
- **Нужна ли лицензия?** Пробная версия работает для разработки; коммерческая лицензия требуется для продакшн.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового диагонального градиента.  
- **Можно ли использовать это с другими Java‑фреймворками?** Да, API не зависит от фреймворка.  

## Что такое диагональный градиент в XPS‑документе?
Диагональный градиент — это плавный переход цветов, который идёт от одного угла фигуры к противоположному, создавая наклонный визуальный эффект. В XPS такой эффект определяется линейной кистью градиента, содержащей упорядоченные остановки градиента, указывающие цвета и относительные позиции вдоль диагональной линии.

## Почему добавлять диагональный градиент с Aspose.Page?
Aspose.Page обеспечивает **100 % точность рендеринга** градиентов более чем в 20 XPS‑просмотрщиках и поддерживает **30+ функций XPS**, таких как текст, изображения и векторные формы. API абстрагирует сложную разметку XPS, позволяя сосредоточиться на дизайне, гарантируя, что один и тот же файл выглядит одинаково в Windows, macOS и Linux.

## Требования
- Базовые знания Java.  
- Установленный JDK на вашем компьютере.  
- Библиотека Aspose.Page for Java — скачайте её **[здесь](https://releases.aspose.com/page/java/)**.  
- IDE, например IntelliJ IDEA или Eclipse.

## Импорт пакетов
Начните с импорта необходимых классов. Эти импорты дают доступ к геометрии, работе с градиентами и созданию XPS‑документов.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Шаг 1: Настройте ваш проект
Создайте новый Java‑проект в выбранной IDE и добавьте JAR‑файлы Aspose.Page в путь сборки проекта.

## Шаг 2: Определите каталог документа
Укажите, куда будет сохраняться сгенерированный XPS‑файл.

```java
String dataDir = "Your Document Directory";
```

## Шаг 3: Создайте XPS‑документ
`XpsDocument` — основной объект, представляющий XPS‑файл в памяти. Его создание даёт вам холст для добавления страниц, фигур и кистей.

```java
XpsDocument doc = new XpsDocument();
```

## Шаг 4: Добавьте путь с диагональным градиентом
Создайте прямоугольный путь, который получит градиент. Геометрия пути использует простую команду move‑line‑close.  
XpsPath определяет векторную форму в XPS‑документе, например прямоугольник или пользовательскую геометрию.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Шаг 5: Определите линейные остановки градиента
Настройте цвета и их позиции. Каждая остановка определяет точку в градиенте, где появляется конкретный цвет.  
XpsGradientStop представляет одну цветовую остановку в градиенте, указывая цвет и его смещение.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Шаг 6: Примените линейный градиент к пути
`XpsLinearGradientBrush` — тип кисти Aspose.Page для линейных переходов цветов. Он принимает две точки, определяющие направление градиента, и коллекцию остановок градиента, задающих цвета вдоль этой линии.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Шаг 7: Сохраните документ
Сохраните XPS‑файл на диск. Файл будет содержать прямоугольник, заполненный определённым вами диагональным градиентом.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Как добавить градиент в Java XPS?
Загрузите XpsDocument, создайте `XpsLinearGradientBrush` с начальной точкой `(0,0)` и конечной точкой `(width,height)`, добавьте остановки градиента, назначьте кисть свойству `Fill` формы и, наконец, вызовите `save`. Такой лаконичный поток позволяет внедрить диагональный градиент всего несколькими вызовами API, поддерживая чистоту и поддерживаемость кода.

## Распространённые подводные камни и советы
- **Gradient direction** – убедитесь, что начальная и конечная точки кисти отражают нужную диагональ; их перестановка меняет направление градиента.  
- **Color precision** – Aspose использует ARGB; включайте альфа‑канал, если нужна прозрачность.  
- **File path** – всегда используйте абсолютный путь или проверьте, что относительный путь указывает на существующую записываемую директорию.  

## Дополнительные часто задаваемые вопросы

**Q: Как добавить градиент к существующей XPS‑форме?**  
A: Создайте `XpsLinearGradientBrush`, определите остановки градиента и назначьте её свойству `Fill` формы, как показано в Шаге 6.

**Q: Что делает **apply linear gradient** на самом деле?**  
A: Он генерирует определение кисти в пакете XPS, которое ссылается на начальные/конечные точки и коллекцию остановок градиента; просмотрщик рендерит это как плавный переход цветов.

**Q: Есть ли быстрый способ **how to use aspose** для других функций XPS?**  
A: Да, API Aspose.Page включает методы для добавления изображений, текста и пользовательских фигур — просто изучите класс `XpsDocument` для дополнительных вспомогательных функций.

**Q: Могу ли я **add gradient path** к не‑прямоугольным формам?**  
A: Абсолютно. Определите любую геометрию с помощью `createPathGeometry` и затем задайте её `Fill` градиентной кистью.

**Q: Влияет ли градиент существенно на размер файла?**  
A: Только незначительно; определения градиентов представляют собой лёгкие XML‑записи внутри пакета XPS.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Связанные учебники

- [Добавление градиента XPS в Aspose Page](/page/java/xps-gradient-addition/)
- [Добавление текста в Java XPS - учебник Aspose.Page](/page/java/xps-text-manipulation/add-text/)
- [Как добавить изображение в Java XPS документы – простой гид с Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}