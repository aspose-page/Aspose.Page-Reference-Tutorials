---
date: 2026-08-23
description: Узнайте, как использовать aspose.page image manipulation java для встраивания
  и вращения изображений в файлах PostScript с понятными примерами на Java.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Добавить изображение в Java PostScript
og_description: Узнайте, как использовать aspose.page image manipulation java для
  встраивания и вращения изображений в файлах PostScript, с пошаговыми примерами кода
  на Java.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Как использовать aspose.page image manipulation java для добавления изображения
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Как использовать aspose.page image manipulation java для добавления изображения
url: /ru/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать aspose.page image manipulation java для добавления изображения

## Введение
В этом руководстве вы узнаете, как **использовать aspose.page image manipulation java** для создания файлов PostScript, встраивания растровых изображений и применения трансляций и вращений. К концу руководства вы сможете генерировать пиксельно‑точный вывод PostScript из Java — идеально для автоматизированных отчетов, печатных конвейеров или любого рабочего процесса, требующего точного размещения изображений внутри документа PostScript.

## Быстрые ответы
- **Какая библиотека требуется?** Aspose.Page for Java  
- **Можно ли добавить несколько изображений?** Да — повторяйте шаги трансформации и рисования для каждого изображения  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; лицензия требуется для продакшна  
- **Какая версия Java поддерживается?** Java 8 и новее  
- **Поддерживается ли вращение изображения?** Абсолютно — используйте `AffineTransform.rotate()`  

## Что такое aspose.page image manipulation java?
`aspose.page image manipulation java` — это API Aspose.Page, позволяющее программно создавать, редактировать и рендерить документы PostScript из кода Java, включая полный контроль над размещением, масштабированием и вращением изображений. С помощью этого API вы избегаете низкоуровневого синтаксиса PostScript, позволяя библиотеке самостоятельно обрабатывать конвертацию форматов и встраивание.

## Почему использовать aspose.page для манипуляций с изображениями?
Aspose.Page предоставляет **более 50 форматов изображений** (включая JPEG, PNG, BMP, TIFF) и может встраивать их в PostScript без загрузки всего документа в память, позволяя обрабатывать файлы со сотнями страниц, удерживая использование памяти ниже 100 МБ на типичном сервере. Высокоуровневый API абстрагирует сложные команды PostScript, поэтому вы пишете лаконичный код Java вместо сырых операторов PS.

## Требования
- Установлен Java Development Kit (JDK) версии 8 или новее.  
- Библиотека Aspose.Page for Java — скачайте её **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Базовое знакомство с синтаксисом Java и объектно‑ориентированным программированием.

## Что такое create postscript java?
Создание файла PostScript из Java означает программную генерацию документа `.ps`, описывающего макет страницы, векторную графику и растровые изображения с использованием языка PostScript. Aspose.Page переводит ваши вызовы Java в корректные инструкции PostScript, позволяя создавать готовые к печати файлы без отдельного интерпретатора PostScript.

## Как добавить изображение с трансляцией и вращением пошагово

Загрузите изображение, примените `AffineTransform` и нарисуйте его на странице. Ниже приведены шаги, описывающие точную последовательность, которой следует следовать.

### Шаг 1: сохранить графическое состояние
Сохранение графического состояния изолирует ваши трансформации, чтобы позже их можно было отменить. Это эквивалентно оператору `gsave` в чистом PostScript.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Шаг 2: трансляция и трансформация (трансляция и вращение изображения)
Сначала создайте `BufferedImage` из исходного файла, затем сформируйте `AffineTransform`, который перемещает изображение к нужным координатам и вращает его вокруг центра. `AffineTransform.rotate` ожидает угол в радианах, поэтому преобразуйте градусы с помощью `Math.toRadians(degrees)`.

**AffineTransform** — это класс Java, представляющий 2‑D аффинную трансформацию, такую как трансляция, вращение, масштабирование или сдвиг.  
**BufferedImage** — это класс Java, который хранит изображение в памяти в виде растра пикселей.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Шаг 3: добавить изображение в документ
После настройки трансформации нарисуйте изображение на текущей странице. Библиотека автоматически преобразует `BufferedImage` в соответствующий поток изображения PostScript.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Шаг 4: восстановить графическое состояние
Вызов восстановления (`grestore`) возвращает графическое состояние к тому, каким оно было до сохранения, гарантируя, что последующие команды рисования не будут затронуты предыдущей трансформацией.

```java
document.drawImage(image, transform, null);
```

### Шаг 5: закрыть текущую страницу и сохранить
Завершите страницу, закройте документ и запишите выходной файл на диск.

```java
document.writeGraphicsRestore();
```

Вы можете повторять вышеуказанную последовательность для встраивания дополнительных изображений, каждый раз корректируя координаты трансляции и угол вращения.

## Распространённые проблемы и решения
- **FileNotFoundException:** Убедитесь, что `dataDir` заканчивается разделителем файлов (`/` или `\\`) и имя файла изображения точно совпадает.  
- **ImageIO.read returns null:** Убедитесь, что формат изображения входит в поддерживаемый список (JPEG, PNG, BMP, GIF, TIFF).  
- **Incorrect rotation angle:** `AffineTransform.rotate` работает с радианами; используйте `Math.toRadians(degrees)` для преобразования из градусов.  
- **Memory spikes on large pages:** Используйте `Document.save` с `saveOptions.setCompress(true)`, чтобы уменьшить потребление памяти.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Page for Java с другими языками программирования?**  
A: Основная библиотека доступна только для Java, но Aspose предоставляет эквивалентные API для .NET, C++ и Python, каждый из которых адаптирован под свою платформу.

**Q: Доступна ли бесплатная пробная версия Aspose.Page for Java?**  
A: Да, вы можете получить доступ к бесплатной пробной версии **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**Q: Как получить временную лицензию для Aspose.Page for Java?**  
A: Вы можете получить временную лицензию **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q: Где можно найти поддержку сообщества и обсуждения, связанные с Aspose.Page for Java?**  
A: Посетите **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** для получения помощи от сообщества.

**Q: Есть ли дополнительные ресурсы для покупки Aspose.Page for Java?**  
A: Вы можете приобрести библиотеку **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## Заключение
Теперь у вас есть полный, сквозной пример **aspose.page image manipulation java**, который создает файл PostScript, трансформирует и вращает изображение, а затем сохраняет результат. Изучите полную **[documentation](https://reference.aspose.com/page/java/)**, чтобы узнать о продвинутых возможностях, таких как векторная графика, пользовательские размеры страниц и рендеринг текста.

---

**Последнее обновление:** 2026-08-23  
**Тестировано с:** Aspose.Page for Java 23.11  
**Автор:** Aspose  

```java
document.closePage();
document.save();
```

## Связанные руководства

- [Как конвертировать PostScript в PDF с помощью Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Как добавить градиент: Диагональный градиент в Java PostScript с использованием Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Как добавить штриховку в Java PostScript с Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}