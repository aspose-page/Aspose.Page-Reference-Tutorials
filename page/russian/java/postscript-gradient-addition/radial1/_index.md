---
date: 2026-09-09
description: Узнайте, как создать radial gradient в Java PostScript с помощью Aspose.Page.
  Это пошаговое руководство покажет, как добавить color stops gradient, установить
  radii и быстро сгенерировать PS file.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Освоение radial gradients в Java
og_description: Узнайте, как создать radial gradient в Java PostScript с помощью Aspose.Page.
  Это руководство объясняет, как добавить color stops gradient, установить radii и
  сгенерировать PS file за несколько минут.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Как создать radial gradient в Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Как создать radial gradient в Java PostScript
url: /ru/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать радиальный градиент в Java PostScript с Aspose.Page

## Введение
Если вам нужно **создать радиальный градиент** внутри файла PostScript, вы попали по адресу. В этом руководстве мы пройдем каждый шаг, необходимый для создания документа PostScript, содержащего плавный радиальный градиент, используя **Aspose.Page for Java**. К концу вы поймёте API, увидите полностью работающий пример и узнаете, как настраивать цвета, позиции и радиусы для любой дизайнерской задачи.

## Быстрые ответы
- **Какая библиотека создает радиальные градиенты в PostScript?** Aspose.Page for Java.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового примера.  
- **Нужна ли лицензия для запуска кода?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Какая версия Java поддерживается?** Java 8 или выше.  
- **Можно ли изменить форму градиента?** Да — измените радиус и центральную точку в конструкторе `RadialGradientPaint`.

## Как создать радиальный градиент в Java
Загрузите ваш Java‑проект, импортируйте необходимые классы и следуйте пошаговому руководству ниже. Суть в том, что вы создаёте экземпляр `RadialGradientPaint` с вашими цветовыми остановками и затем применяете его к прямоугольнику, нарисованному на `PsDocument`. Такой двухобъектный подход обрабатывает все низкоуровневые команды PostScript за вас.

## Что такое радиальный градиент?
`RadialGradientPaint` — это класс Java AWT, определяющий круговой переход цветов от центральной точки наружу. Он создаёт плавное смешивание нескольких цветовых остановок, что делает его идеальным для прожекторов, мягких фонов или любого эффекта, где цвета расходятся от фокусной точки.

## Почему использовать Aspose.Page для радиальных градиентов?
Aspose.Page предоставляет полный программный контроль над выводом PostScript, одновременно беря на себя тяжёлую работу с низкоуровневым синтаксисом PS. Он поддерживает **более 50 форматов ввода и вывода**, может рендерить документы из сотен страниц без загрузки всего файла в память и работает на любой операционной системе, поддерживающей Java 8+. Такая измеримая возможность делает его надёжным выбором для генерации графики корпоративного уровня.

## Требования
- **Java Development Kit (JDK) 8+** – проверьте с помощью `java -version`.  
- **Aspose.Page for Java** – скачайте последнюю JAR‑файл с официальной [страницы загрузки Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE по вашему выбору** – Eclipse, IntelliJ IDEA или VS Code с расширениями Java.  
- **Папка с правом записи** – куда будет сохранён сгенерированный файл `.ps`.

## Импорт пакетов
Сначала импортируйте необходимые классы. Пакет `java.awt` предоставляет объекты градиентной заливки, а `com.aspose.eps` содержит классы для работы с документами PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Пошаговое руководство

### Шаг 1: создать прямоугольник и открыть PS‑документ
`PsDocument` — класс Aspose.Page, представляющий документ PostScript и предоставляющий методы для рисования фигур, текста и изображений. Мы начинаем с создания выходного потока, настройки размера страницы (по умолчанию A4) и определения прямоугольника, который будет содержать градиент.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Совет:** Отрегулируйте координаты прямоугольника (`200, 100, 200, 200`), чтобы разместить градиент в любой точке страницы.

### Шаг 2: определить цвета и доли
Радиальный градиент строится из *цветовых остановок* (цветов) и *долей* (относительных позиций этих остановок). Здесь мы создаём массив из шести цветов и их соответствующих долей.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Почему это важно:** Регулируя `fractions`, вы контролируете скорость перехода цветов, позволяя создавать как тонкие, так и драматические эффекты.

### Шаг 3: создать объект radial gradient paint
`RadialGradientPaint` — основной класс, описывающий радиальный цветовой градиент, включая центральную точку, радиус, точку фокуса, доли, цвета, метод цикличности и цветовое пространство. Теперь мы создаём объект `RadialGradientPaint`, используя массивы, определённые выше.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Примечание:** `transform` может быть `null`, если вам не требуется дополнительное масштабирование или вращение. Не стесняйтесь экспериментировать с `AffineTransform` для наклонных градиентов.

### Шаг 4: установить заливку и заполнить прямоугольник
Когда заливка готова, мы указываем `PsDocument` использовать её, а затем заполняем ранее определённый прямоугольник.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

На этом этапе страница PostScript содержит прямоугольник, плавно заполненный настроенным радиальным градиентом.

### Шаг 5: закрыть и сохранить документ
Наконец, закройте текущую страницу и запишите файл на диск.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Откройте `RadialGradient1_outPS.ps` в любом просмотрщике PostScript (например, Ghostscript), и вы увидите градиент, отрисованный точно так, как задан.

## Распространённые проблемы и решения
| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Градиент выглядит как сплошной цвет | `fractions` массив не начинается с `0.0f` или не заканчивается на `1.0f` | Убедитесь, что первая доля равна `0.0f`, а последняя — `1.0f`. |
| Цвета выглядят вымытыми | Используется неверный `ColorSpaceType` | Переключитесь на `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` для более яркого вывода. |
| Файл вывода не создан | Путь `FileOutputStream` недействителен или недоступен для записи | Проверьте, что `dataDir` существует и приложение имеет права записи. |

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.Page for Java в коммерческих проектах?**  
A: Да. Для продакшн‑использования требуется коммерческая лицензия. Вы можете приобрести её на [странице лицензирования Aspose](https://purchase.aspose.com/buy).

**Q: Где я могу найти официальную справку по API?**  
A: Полная документация доступна в [справке Aspose.Page Java API](https://reference.aspose.com/page/java/).

**Q: Доступна ли бесплатная пробная версия для тестирования?**  
A: Конечно. Скачайте пробную версию со [страницы релизов Aspose.Page](https://releases.aspose.com/).

**Q: Как получить временную лицензию для оценки?**  
A: Временную лицензию можно запросить на [странице запроса временной лицензии](https://purchase.aspose.com/temporary-license/).

**Q: Где я могу получить поддержку сообщества?**  
A: Присоединяйтесь к форуму сообщества Aspose.Page по адресу [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Заключение
Теперь вы знаете **как создать радиальный градиент** в документе Java PostScript с помощью Aspose.Page. Регулируя размер прямоугольника, цветовые остановки и радиус градиента, вы можете создавать бесчисленные визуальные эффекты — от тонких фоновых заливок до ярких графических акцентов. Не стесняйтесь экспериментировать с различными значениями `AffineTransform` для вращения или наклона градиента и комбинировать эту технику с текстом и изображениями для более насыщенных PDF или EPS‑выводов.

---

**Последнее обновление:** 2026-09-09  
**Тестировано с:** Aspose.Page for Java latest (as of writing)  
**Автор:** Aspose

## Связанные руководства

- [Заполнить форму градиентом: пример радиального градиента Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Создать градиент PostScript в Java — добавить вертикальный градиент](/page/java/postscript-gradient-addition/vertical/)
- [Учебник по прозрачности Aspose.Page — добавить прозрачность в Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}