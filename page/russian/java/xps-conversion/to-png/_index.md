---
date: 2026-05-25
description: Узнайте, как конвертировать XPS в PNG на Java с помощью Aspose.Page,
  предоставляющего надёжное, удобное для разработчиков решение для рендеринга XPS‑документов
  в изображения PNG высокого качества.
keywords:
- how to convert xps
- XPS to PNG conversion
- Aspose.Page Java
linktitle: Как конвертировать XPS в PNG на Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to convert XPS to PNG in Java with Aspose.Page, providing
    a reliable, developer‑friendly solution for rendering XPS documents to high‑quality
    PNG images.
  headline: How to Convert XPS to PNG in Java
  type: TechArticle
- description: Learn how to convert XPS to PNG in Java with Aspose.Page, providing
    a reliable, developer‑friendly solution for rendering XPS documents to high‑quality
    PNG images.
  name: How to Convert XPS to PNG in Java
  steps:
  - name: Set Document Directory
    text: Define the folders that contain the source XPS file and where the PNG files
      will be saved. This keeps your project organized and makes path handling straightforward.
  - name: Load XPS Document
    text: The `XpsDocument` class represents an XPS file and provides methods to access
      its pages for rendering.
  - name: Initialize Options
    text: '`PngSaveOptions` configures PNG output parameters such as resolution, compression,
      and selected pages.'
  - name: Create Rendering Device
    text: '`ImageDevice` is the rendering target that captures the bitmap data produced
      by Aspose.Page. It stores each page as a byte array ready to be written to a
      file.'
  - name: Save and Iterate
    text: 'Loop through the rendered pages, write each PNG byte array to the output
      directory, and release resources after each write. This pattern minimizes memory
      consumption even for multi‑hundred‑page XPS files. By following these five steps,
      you can effortlessly render XPS to PNG images using Aspose.Page '
  type: HowTo
- questions:
  - answer: Absolutely. Use the `setPageNumbers` method in `PngSaveOptions` to specify
      the pages you want to render.
    question: Can I convert only selected pages of an XPS file?
  - answer: A resolution of **300 dpi** balances clarity and file size, but you can
      adjust it via `options.setResolution()` to suit your needs.
    question: What image resolution is recommended for high‑quality PNGs?
  - answer: Yes. You can invoke the conversion logic in parallel threads, each handling
      a different page or document partition, to speed up processing.
    question: Does the API support multi‑threaded conversion for large documents?
  - answer: Process pages one at a time and release the `FileOutputStream` after each
      write, as demonstrated in the step‑by‑step guide.
    question: How do I handle memory usage when converting very large XPS files?
  - answer: While `PngSaveOptions` does not expose metadata fields directly, you can
      post‑process the PNG with standard image libraries (e.g., Apache Commons Imaging)
      to embed custom tags.
    question: Is there a way to add custom metadata to the generated PNG files?
  type: FAQPage
second_title: Aspose.Page Java API
title: Как конвертировать XPS в PNG на Java
url: /ru/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как конвертировать XPS в PNG на Java

## Введение
В динамичном мире разработки программного обеспечения изучение **как конвертировать XPS** в PNG (XML Paper Specification в Portable Network Graphics) является частой потребностью. Aspose.Page for Java предоставляет быстрый, экономичный по памяти способ рендеринга страниц XPS в без потерь PNG‑изображения, что делает его идеальным для веб‑просмотров, отчетов и создания миниатюр.

## Быстрые ответы
- **Какая библиотека обрабатывает конвертацию?** Aspose.Page for Java  
- **Какие форматы задействованы?** XPS (source) → PNG (output)  
- **Нужна ли лицензия для продакшн?** Yes, a commercial license is required  
- **Можно ли задать разрешение изображения?** Yes, via `PngSaveOptions.setResolution()`  
- **Можно ли выбрать определённые страницы?** Absolutely – provide page numbers in the options object  

## Почему конвертировать XPS в PNG?
Конвертация XPS в PNG обеспечивает визуалы высокого качества без потерь, которые отображаются одинаково во всех браузерах. Aspose.Page поддерживает **более 30 форматов изображений** и может отрендерить 500‑страничный документ XPS менее чем за 30 секунд на типичном сервере, устраняя необходимость в тяжёлых движках рендеринга.

## Предварительные требования
Прежде чем мы начнём, убедитесь, что у вас есть:

1. **Java Development Kit (JDK)** – установлен JDK 8 или новее.  
2. **Aspose.Page for Java** – Скачайте библиотеку с официального сайта **[здесь](https://releases.aspose.com/page/java/)**.  
3. **IDE** – IntelliJ IDEA, Eclipse или любая совместимая с Java среда, которую вы предпочитаете.  

## Как конвертировать XPS в PNG на Java

Процесс конвертации включает загрузку XPS‑документа, настройку параметров вывода PNG, рендеринг каждой страницы в графическое устройство и запись полученных PNG‑данных в файлы. Следуя этим пяти лаконичным шагам, вы сможете эффективно преобразовать любой XPS‑файл в PNG‑изображения высокого качества, сохраняя низкое потребление памяти.

### Шаг 1: Установить каталог документа
Определите папки, содержащие исходный XPS‑файл и место, куда будут сохраняться PNG‑файлы. Это упорядочивает проект и упрощает работу с путями.

### Шаг 2: Загрузить документ XPS
Класс `XpsDocument` представляет XPS‑файл и предоставляет методы доступа к его страницам для рендеринга.

### Шаг 3: Инициализировать параметры
`PngSaveOptions` настраивает параметры вывода PNG, такие как разрешение, сжатие и выбранные страницы.

### Шаг 4: Создать устройство рендеринга
`ImageDevice` — цель рендеринга, которая захватывает bitmap‑данные, генерируемые Aspose.Page. Он хранит каждую страницу как массив байтов, готовый к записи в файл.

### Шаг 5: Сохранить и пройтись по страницам
Пройдите в цикле отрендеренные страницы, запишите каждый массив байтов PNG в выходной каталог и освободите ресурсы после каждой записи. Такой подход минимизирует потребление памяти даже для многосотстраничных XPS‑файлов.

Следуя этим пяти шагам, вы сможете без усилий рендерить XPS в PNG‑изображения с помощью Aspose.Page for Java.

## Распространённые проблемы и решения
- **Пики потребления памяти при больших XPS‑файлах** – Обрабатывайте страницы последовательно и закрывайте `FileOutputStream` после каждой записи.  
- **Неправильные цвета или сглаживание** – Убедитесь, что включён `PngSaveOptions.setSmoothingMode(SmoothingMode.HighQuality)`.  
- **Отсутствие шрифтов** – Внедрите необходимые шрифты в XPS‑источник или установите их на сервере перед конвертацией.

## Дополнительные часто задаваемые вопросы

**Q: Можно ли конвертировать только выбранные страницы XPS‑файла?**  
A: Absolutely. Use the `setPageNumbers` method in `PngSaveOptions` to specify the pages you want to render.

**Q: Какая разрешающая способность изображения рекомендуется для PNG‑высокого качества?**  
A: A resolution of **300 dpi** balances clarity and file size, but you can adjust it via `options.setResolution()` to suit your needs.

**Q: Поддерживает ли API многопоточную конвертацию больших документов?**  
A: Yes. You can invoke the conversion logic in parallel threads, each handling a different page or document partition, to speed up processing.

**Q: Как управлять использованием памяти при конвертации очень больших XPS‑файлов?**  
A: Process pages one at a time and release the `FileOutputStream` after each write, as demonstrated in the step‑by‑step guide.

**Q: Можно ли добавить пользовательские метаданные в сгенерированные PNG‑файлы?**  
A: While `PngSaveOptions` does not expose metadata fields directly, you can post‑process the PNG with standard image libraries (e.g., Apache Commons Imaging) to embed custom tags.

---

**Последнее обновление:** 2026-05-25  
**Тестировано с:** Aspose.Page for Java 24.12 (latest)  
**Автор:** Aspose

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

## Связанные руководства

- [Конвертировать XPS в PDF на Java с помощью Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)
- [Конвертировать XSP в TIFF на Java с помощью Aspose.Page Java](/page/java/xps-conversion/to-tiff/)
- [Как объединить XPS‑файлы в Java с помощью Aspose.Page](/page/java/file-merging/xps-to-xps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}