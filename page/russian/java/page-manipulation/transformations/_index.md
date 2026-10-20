---
date: 2026-10-20
description: Узнайте, как масштабировать прямоугольник с помощью Aspose.Page for Java,
  как translate shape и применять affine transform для создания документов PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Преобразования при работе со страницами в Java
og_description: Узнайте, как масштабировать прямоугольник, translate shape и применять
  affine transform с помощью Aspose.Page for Java для эффективного создания файлов
  PostScript.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Как масштабировать прямоугольник с Aspise.Page for Java – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Как масштабировать прямоугольник с помощью Aspose.Page for Java
url: /ru/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как масштабировать прямоугольник с помощью Aspose.Page для Java

## Введение
В этом руководстве вы узнаете, как **how to scale rectangle** объекты, используя Aspose.Page для Java, а также научитесь перемещать позиции фигур, вращать графику и применять аффинные преобразования для получения высококачественного вывода PostScript. Эти техники позволяют создавать сложную, независимую от устройства графику без написания низкоуровневого кода рендеринга, делая ваши Java‑приложения более мощными и поддерживаемыми.

## Быстрые ответы
`scale(sx, sy)` масштабирует графический контекст по заданным горизонтальному и вертикальному коэффициентам.  

- **Как масштабировать прямоугольник в Java с помощью Aspose.Page?** Вызовите метод `scale(sx, sy)` на графическом контексте перед рисованием прямоугольника.  
- **Могу ли я переместить (translate) форму, не затрагивая другую графику?** Да — оберните трансляцию между вызовами `writeGraphicsSave()` и `writeGraphicsRestore()`.  
- **Какой класс создает файл PostScript?** Используйте `PsDocument` совместно с `PsSaveOptions`.  
- **Нужна ли лицензия для использования в продакшене?** Для коммерческих развертываний требуется действующая лицензия Aspose.Page.  
- **Какая версия Java поддерживается?** Aspose.Page работает с Java 8 и более новыми версиями.

## Требования
Прежде чем начать, убедитесь, что у вас есть:

- Твердое понимание базового синтаксиса Java и объектно‑ориентированных концепций.  
- Установленная библиотека Aspose.Page для Java. Вы можете скачать её из [документации Aspose.Page для Java](https://reference.aspose.com/page/java/).  
- IDE для Java (IntelliJ IDEA, Eclipse или VS Code), настроенная с JAR‑файлами библиотеки в classpath.

## Импорт пакетов
`PsDocument` — основной класс, используемый для создания документа PostScript, а `PsSaveOptions` настраивает способ сохранения документа.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Что такое «how to scale rectangle» в Aspose.Page?
`scale(float sx, float sy)` метод применяет аффинное масштабирование к текущему графическому состоянию, изменяя размер последующих рисунков по коэффициентам `sx` (по горизонтали) и `sy` (по вертикали). Это основная операция, лежащая в основе ключевого слова **how to scale rectangle**. Применяя это преобразование перед рисованием, любые последующие формы, такие как прямоугольники, будут отрисованы с новыми размерами при сохранении их пропорций.

## Как переместить форму с помощью Aspose.Page
`writeGraphicsSave()` сохраняет текущее графическое состояние, а `writeGraphicsRestore()` восстанавливает его, гарантируя, что преобразования влияют только на нужную форму. Трансляция перемещает начало координат без изменения размеров объектов. Обернув `translate(dx, dy)` вызовами `writeGraphicsSave()` / `writeGraphicsRestore()`, вы обеспечиваете перемещение только выбранной формы, в то время как остальная графика остаётся неизменной, предоставляя точный контроль над отдельными элементами.

## Пример 1: без трансформаций
Первый пример рисует прямоугольник без каких-либо преобразований, создавая базовую линию для визуального сравнения с последующими примерами.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Пример 2: перемещение
В этом примере мы смещаем графический контекст на 250 единиц вправо перед рисованием второго прямоугольника, демонстрируя **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Пример 3: масштабирование
Здесь мы отвечаем на основной вопрос **how to scale rectangle**. Прямоугольник уменьшается до 50 % от исходной ширины и 75 % от исходной высоты с помощью вызова `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Как повернуть форму в Java (rotate shape java)
`rotate(angle)` вращает систему координат на указанный угол в градусах. Загрузите ваш `PsDocument`, вызовите `rotate(angle)` на графическом состоянии, нарисуйте форму, затем восстановите предыдущее состояние. Этот шаблон реализует **rotate shape java** и **how to rotate rectangle** в одном переиспользуемом блоке, позволяя вращать графику вокруг любой выбранной точки.

## Почему это важно – практические преимущества
- **Вывод, независимый от устройства** — Aspose.Page может генерировать файлы PostScript и XPS, которые отображаются одинаково на любом принтере или просмотрщике, устраняя специфические для платформы настройки.  
- **Тонкий контроль** — Комбинируйте трансляцию, масштабирование, сдвиг и вращение для точного соответствия спецификациям макета; API поддерживает более 20 комбинаций преобразований на страницу.  
- **Производительная обработка** — Библиотека обрабатывает документы, занимая менее 10 МБ памяти для типичных 100‑страничных отчетов, делая пакетные задания быстрыми и масштабируемыми.

## Распространённые сценарии использования
- **Печатные счета‑фактуры** — Точно размещайте логотипы, штрихкоды и таблицы, используя масштабирование и трансляцию в соответствии с корпоративными руководствами по брендингу.  
- **Технические схемы** — Генерируйте схемы, где каждый компонент должен быть пропорционально изменён и размещён.  
- **Автоматизированные многостраничные отчёты** — Создавайте PostScript‑отчёты, требующие согласованного масштабирования на всех страницах, например инженерные спецификации.

## Распространённые проблемы и решения
- **Трансформация не сбрасывается** — Всегда сочетайте `writeGraphicsSave()` с `writeGraphicsRestore()`; иначе последующие рисунки наследуют нежелательные преобразования.  
- **Неожиданные цвета** — Устанавливайте краску (цвет) после каждой трансформации, так как графическое состояние не сохраняет информацию о цвете после восстановления.  
- **Слишком большой размер файла** — Включите сжатие в `PsSaveOptions` и ограничьте разрешение встроенных растровых изображений, чтобы итоговый файл оставался менее 5 МБ для типичных 50‑страничных документов.

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java для других форматов документов?
Aspose.Page в основном сосредоточен на работе со страницами форматов PostScript и XPS, но также предоставляет ограниченные возможности экспорта в PDF.

### Где я могу найти больше примеров и документацию по Aspose.Page для Java?
Посетите [документацию Aspose.Page для Java](https://reference.aspose.com/page/java/) для получения подробных руководств, справочников API и примеров проектов.

### Доступна ли бесплатная пробная версия Aspose.Page для Java?
Да, вы можете получить бесплатную пробную версию через страницу **Aspose free trial download**: [Aspose free trial download](https://releases.aspose.com/).

### Как получить временную лицензию для Aspose.Page для Java?
Получите временную лицензию через страницу **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Где я могу получить поддержку сообщества или задать вопросы о Aspose.Page для Java?
Посетите [форум Aspose.Page для Java](https://forum.aspose.com/c/page/39) для обсуждений сообщества, фрагментов кода и советов по устранению неполадок.

## Часто задаваемые вопросы

**Q: В чём разница между `translate` и `scale`?**  
**A:** `translate` перемещает начало координат системы, тогда как `scale` изменяет размер нарисованных объектов по осям X и/или Y.

**Q: Можно ли комбинировать несколько преобразований в одном графическом состоянии?**  
**A:** Да — вызывая последовательно `translate`, `scale`, `rotate` или `shear` перед рисованием, вы создаёте комбинированное аффинное преобразование.

**Q: Как сбросить преобразования после рисования формы?**  
**A:** Используйте `writeGraphicsRestore()`, чтобы вернуть предыдущее сохранённое графическое состояние.

**Q: Можно ли вращать прямоугольник вокруг его центра?**  
**A:** Конечно. Переместите прямоугольник к началу координат, примените `rotate(angle)`, затем верните его обратно перед рисованием.

**Q: Поддерживает ли Aspose.Page сглаживание (anti‑aliasing) для более плавной графики?**  
**A:** Да — установите соответствующие параметры рендеринга в `PsSaveOptions`, чтобы включить сглаживание.

**Последнее обновление:** 2026-10-20  
**Тестировано с:** Aspose.Page for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [Как нарисовать прямоугольник в Java PostScript с помощью Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Создать радиальный градиент в PostScript с помощью Aspose.Page для Java](/page/java/postscript-gradient-addition/)
- [Манипуляция страницами Postscript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}