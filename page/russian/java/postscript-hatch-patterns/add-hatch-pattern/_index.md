---
date: 2026-08-18
description: Узнайте, как добавить hatch pattern в файлы Java PostScript с помощью
  Aspose.Page Java. Это пошаговое руководство показывает полный код и советы.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Добавить Hatch Pattern в Java PostScript
og_description: Узнайте, как добавить hatch pattern в Java PostScript с помощью Aspose.Page.
  Следуйте этому пошаговому учебнику, чтобы быстро создавать hatch‑filled graphics.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Как добавить hatch pattern в Java PostScript – руководство Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Как добавить hatch pattern в Java PostScript
url: /ru/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить штриховой узор в Java PostScript

## Введение
Если вы работаете с **Aspose.Page Java** и задаётесь вопросом **как добавить штриховой узор** в ваш вывод PostScript, штриховые узоры — это быстрый и гибкий способ. В этом руководстве мы пройдемся по **как добавить штрих** дизайнам в документ PostScript, объясним, почему они полезны, и предоставим полностью готовый пример кода. К концу вы сможете создавать визуально привлекательные фигуры и текст, заполненные штриховкой, всего несколькими строками Java.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.Page for Java (the “aspose page java” SDK).  
- **Какой визуальный эффект мы добавляем?** Hatch patterns (e.g., diagonal lines, crosshatch).  
- **Нужна ли лицензия для запуска примера?** A free trial works for development; a license is required for production.  
- **Сколько строк кода?** About 70 lines, split into clear steps.  
- **Могу ли я использовать тот же подход для PDF?** Yes—Aspose.Page supports multiple output formats, including PDF.

## Что такое штриховой узор?
Штриховой узор — это векторное заполнение, состоящее из повторяющихся линий или фигур, создающих текстурный эффект. Поскольку он определяется математически, узор масштабируется без потери качества, что делает его идеальным для печати высокого разрешения и монохромного вывода.

## Почему использовать штриховые узоры с Aspose.Page Java?
Aspose.Page поддерживает **10+ форматов вывода** (включая PostScript, PDF, EPS, SVG и XPS) и может отрисовывать штриховые заливки в документах до **500 страниц** без загрузки всего файла в память. Это обеспечивает быструю работу, небольшое потребление памяти и одинаковый визуальный результат во всех поддерживаемых форматах.

## Как добавить штриховой узор — обзор
Штриховые узоры — это векторные текстуры, которые отображаются чисто при любом разрешении и хорошо работают на монохромных принтерах. С помощью Aspose.Page Java вы можете применять эти узоры к фигурам, путям и даже тексту, не работая с низкоуровневыми командами PostScript.

## Требования
- **Java Development Environment** – JDK 8 или выше и IDE по вашему выбору.  
- **Aspose.Page for Java library** – Download the latest JAR from the official **Aspose.Page for Java download page** [here](https://releases.aspose.com/page/java/).  
- Вы также можете просмотреть другие релизы Aspose [here](https://releases.aspose.com/).  
- **Write access** to a folder where the generated PostScript file will be saved.

## Импорт пакетов
Ниже приведённые импорты включают стандартные классы Java AWT для графических примитивов, таких как цвета, штрихи и геометрические формы, а также классы Aspose.Page, предоставляющие модель документа, определения штриховых стилей и параметры сохранения, необходимые для создания файла PostScript.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Что такое класс `Document`?
Класс `Document` — это объект верхнего уровня Aspose.Page, представляющий один файл PostScript в памяти. Все операции рисования выполняются через этот объект.

## Как настроить поток вывода?
Чтобы записать вывод, создайте `FileOutputStream`, указывающий на желаемый путь к файлу; этот поток обрабатывает запись байтов низкого уровня. `PsSaveOptions` настраивает способ сохранения документа, включая размер страницы и сжатие. Затем создайте экземпляр `Document` с объектом `PsSaveOptions`, который задаёт размер страницы, сжатие и другие параметры, специфичные для PostScript.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Как сохранить состояние графики и сместить начало координат?
Сохранение состояния графики фиксирует текущую матрицу преобразования, область отсечения и атрибуты рисования, позволяя позже восстановить их. После сохранения вызовите `translate(x, y)` у графического объекта, чтобы сместить начало координат в удобное место для рисования сетки штриховых квадратов.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Как создать переиспользуемый квадрат для каждого узора?
`Rectangle2D` представляет прямоугольную форму, определяемую её позицией и размером. Создав один экземпляр, соответствующий размерам ячейки, вы можете переиспользовать его для каждого квадрата, заполненного штриховкой, уменьшая количество выделений объектов и делая цикл рисования эффективным.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Как настроить перо для контура квадратов узора?
`BasicStroke` описывает толщину контура, шаблон пунктиров и окончания для векторных фигур. Использование `BasicStroke` толщиной 2 пункта обеспечивает чёткую границу вокруг каждой клетки, заполненной штриховкой, гарантируя визуальное отделение заливки от соседних квадратов.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Как перебрать штриховые узоры?
`HatchStyle` — это перечисление, содержащие все предопределённые штриховые узоры, такие как диагональные, перекрёстные и пунктирные стили. Перебор `HatchStyle.values()` позволяет последовательно применять каждый узор, заполнять прямоугольник `HatchBrush` и затем рисовать его контур.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Как восстановить состояние графики после рисования?
Вызов `restore()` у графического объекта возвращает матрицу преобразования и настройки рисования к ранее сохранённому состоянию, предотвращая накопительные трансляции или масштабирование, влияющие на последующие операции рисования. Это гарантирует, что последующее содержимое начинается с исходной системы координат и использует атрибуты по умолчанию.  
```java
document.writeGraphicsRestore();
```

## Как заполнить текст штриховым узором?
`TextFragment` представляет фрагмент текста, который можно позиционировать и стилизовать независимо. Присвоив `HatchBrush` с выбранным `HatchStyle` заполнению фрагмента, символы текста отрисовываются с использованием штриховой текстуры вместо сплошного цвета.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Как обвести текст другим штриховым стилем?
`HatchBrush` также можно использовать для обводки. Чтобы нарисовать контур, задайте обводку фрагмента `HatchBrush` с другим `HatchStyle` (например, 70 % штриховка) и увеличьте толщину обводки через `setStrokeWidth`. Это отрисовывает границу текста своим собственным штриховым узором, сохраняя заполненный внутренний участок.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Как закрыть и сохранить документ?
`document.save()` записывает документ из памяти в указанный поток вывода. После выполнения всех команд рисования вызовите этот метод, а затем закройте `FileOutputStream`, чтобы освободить системные ресурсы и убедиться, что файл корректно сброшен на диск.  
```java
document.closePage();
document.save();
```

Следуйте этим шагам, и у вас будет файл PostScript, демонстрирующий полный набор штриховых узоров, применённых как к фигурам, так и к тексту — всё это реализовано с помощью **aspose page java**.

## Распространённые подводные камни и советы
- **File path errors** – Ensure `dataDir` ends with the appropriate file‑separator (`/` or `\`). Убедитесь, что `dataDir` заканчивается правильным разделителем пути (`/` или `\`).  
- **Unsupported colors** – Some older PostScript interpreters may not handle certain color spaces; stick to basic RGB for maximum compatibility. Некоторые старые интерпретаторы PostScript могут не поддерживать определённые цветовые пространства; используйте базовый RGB для максимальной совместимости.  
- **License warnings** – Running the sample without a valid license will embed a watermark in the output. Запуск примера без действующей лицензии добавит водяной знак в вывод.

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.Page Java с другими Java‑фреймворками?**  
A: Yes, the library is framework‑agnostic and works with Spring, Jakarta EE, Android (limited), and plain Java SE.

**Q: Доступна ли пробная версия Aspose.Page Java?**  
A: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).

**Q: Как получить временную лицензию для разработки?**  
A: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/). It removes evaluation watermarks.

**Q: Где можно найти больше руководств и поддержку сообщества?**  
A: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) for additional examples and Q&A.

**Q: Есть ли полная документация по всем классам и методам?**  
A: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Могу ли я отрисовать тот же штриховой узор в PDF вместо PostScript?**  
A: Absolutely. Change the `PsSaveOptions` to `PdfSaveOptions` (or the equivalent) and the rest of the code remains unchanged.

**Q: Что делать, если сгенерированный файл пустой?**  
A: Verify that the output stream points to a writable directory and that `document.save()` is called after all drawing operations.

---

**Последнее обновление:** 2026-08-18  
**Тестировано с:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Автор:** Aspose

## Связанные руководства

- [Создать текстурный узор в PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Как добавить градиент: Диагональный градиент в Java PostScript с использованием Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Как конвертировать PostScript в PDF с помощью Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}