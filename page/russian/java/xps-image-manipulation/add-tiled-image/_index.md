---
date: 2026-05-30
description: Узнайте, как создать XPS‑документ в Java с помощью Aspose.Page и легко
  добавить мозаичное изображение с помощью пошагового руководства. Как быстро создавать
  XPS‑файлы.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Добавить мозаичное изображение в Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Как создать XPS‑документ с мозаичным изображением в Java
url: /ru/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать документ XPS с мозаичным изображением в Java

## Введение
Создание XPS‑документов программно — это ключевой навык для Java‑разработчиков, которым нужен печатный, независимый от устройства вывод. **How to create XPS** файлы эффективно решает Aspose.Page for Java, который абстрагирует детали низкоуровневой спецификации XML Paper Specification и позволяет сосредоточиться на визуальном дизайне. В этом руководстве вы увидите, как именно создать документ XPS, добавить мозаичное изображение в качестве фона или узора и сохранить результат — всё с помощью лаконичного, готового к продакшн кода.

## Быстрые ответы
- **Что делает Aspose.Page?** Он предоставляет высокоуровневый API для генерации и манипуляции XPS‑документами в Java.  
- **Можно ли замостить изображение?** Да — используйте `XpsImageBrush` с `XpsTileMode.Tile`.  
- **Нужна ли лицензия?** Для использования в продакшн требуется временная или коммерческая лицензия.  
- **Какая версия Java поддерживается?** Совместима с любой JDK 8+.  
- **Сколько времени занимает реализация?** Около 10–15 минут для базового сценария с мозаичным изображением.

## Что такое «создание XPS‑документа»?
`XpsDocument` — это объект верхнего уровня Aspose.Page, представляющий один XPS‑файл в памяти. Он инкапсулирует страницы, ресурсы и метаданные, позволяя программно собрать документ. Создание XPS‑документа означает создание экземпляра этого класса, добавление визуальных элементов и вызов `save` для записи фиксированного макета на диск. Такой подход устраняет ручную работу с XML и гарантирует соответствие спецификации XML Paper Specification.

## Зачем добавлять мозаичное изображение?
Мозаика повторяет графику по заданной области, что идеально подходит для фонов, водяных знаков или узорных заливок. Используя `XpsTileMode.Tile`, изображение автоматически повторяется без ручного дублирования, экономя время разработки и обеспечивая одинаковый рендеринг на любом устройстве. Мозаичные изображения также снижают размер файла, поскольку один и тот же битмап‑ресурс переиспользуется вместо многократного встраивания.

## Требования
1. **Java Development Kit (JDK)** – установлен JDK 8 или новее.  
2. **Aspose.Page for Java** – скачайте с [website](https://releases.aspose.com/page/java/).  
3. **Записываемый каталог** – куда будет сохранён сгенерированный XPS‑файл.

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые классы:

`XpsDocument` — основной объект, представляющий XPS‑файл.  
`XpsImageBrush` рисует фигуры, используя источник изображения.  
`XpsTileMode` определяет способ замощения изображения.  
`Rectangle2D` описывает прямоугольную область для позиционирования.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Пошаговое руководство

### Шаг 1: Настройте ваш проект
Добавьте JAR‑файлы Aspose.Page в classpath проекта и убедитесь, что операторы импорта компилируются без ошибок.

### Шаг 2: Создайте документ XPS
`XpsDocument` — ядро‑контейнер, содержащий страницы, пути и ресурсы. Создайте его с нужным размером страницы, после чего можно начинать добавлять графические элементы.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Шаг 3: Укажите путь к мозаичному изображению
Поместите изображение, которое хотите замостить (например, `R08LN_NN.jpg`), в каталог, указанный переменной `dataDir`. Это изображение будет использовано в качестве шаблона кисти.

### Шаг 4: Добавьте мозаичное изображение
Создайте прямоугольный путь и заполните его `XpsImageBrush`. Установив режим замощения в `Tile`, изображение будет повторяться по всему прямоугольнику. Настройте исходный и целевой `Rectangle2D`, чтобы контролировать размер и позицию плитки.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Шаг 5: Сохраните документ
Запишите XPS‑файл на диск. Полученный файл будет содержать мозаичное изображение, которое вы только что задали, и его можно открыть в любом XPS‑просмотрщике.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Повторяйте эти шаги каждый раз, когда необходимо **add tiled image** на другие страницы или фигуры внутри того же XPS‑документа.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| Изображение не отображается | Проверьте, что путь к файлу (`dataDir + "R08LN_NN.jpg"`) правильный и изображение доступно. |
| Шаблон плитки выглядит растянутым | Отрегулируйте значения исходного и целевого `Rectangle2D`, чтобы задать размер плитки. |
| Прозрачность не работает | Убедитесь, что непрозрачность кисти задаётся **после** настройки режима плитки. |

## Часто задаваемые вопросы

**Q:** Совместим ли Aspose.Page со всеми версиями Java?  
**A:** Aspose.Page поддерживает Java 8‑21; полную матрицу совместимости можно найти [here](https://reference.aspose.com/page/java/).

**Q:** Можно ли использовать Aspose.Page в коммерческих проектах?  
**A:** Да, для продакшн‑использования требуется коммерческая лицензия. Варианты покупки указаны [here](https://purchase.aspose.com/buy).

**Q:** Доступна ли бесплатная пробная версия?  
**A:** Полнофункциональная бесплатная пробная версия доступна для скачивания со страницы релизов Aspose [here](https://releases.aspose.com/).

**Q:** Где получить поддержку сообщества?  
**A:** Присоединяйтесь к форуму сообщества Aspose.Page по адресу [forum](https://forum.aspose.com/c/page/39), задавайте вопросы и делитесь примерами.

**Q:** Как получить временную лицензию для оценки?  
**A:** Временные лицензии предоставляются по запросу через портал Aspose [here](https://purchase.aspose.com/temporary-license/).

## Заключение
Теперь у вас есть полностью готовый к продакшн процесс **how to create XPS** документов с мозаичными изображениями с использованием Aspose.Page for Java. Благодаря `XpsImageBrush` и `XpsTileMode.Tile` вы можете генерировать богатую повторяющуюся графику без увеличения размера файла. Экспериментируйте с различными размерами плитки, уровнями непрозрачности и формами, чтобы создавать сложные макеты документов. На следующем этапе изучите добавление векторных фигур или текстовых наложений для дальнейшего улучшения ваших XPS‑файлов.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Add Pages to XPS Tutorial](/page/java/xps-page-manipulation/add-page/)
- [Convert XPS to PDF in Java using Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}