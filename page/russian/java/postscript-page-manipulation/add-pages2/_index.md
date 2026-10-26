---
date: 2026-10-25
description: Узнайте, как установить пользовательский размер страницы и добавлять
  страницы в документы Java PostScript с помощью Aspose.Page. Следуйте нашему пошаговому
  руководству для беспроблемного управления документами.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: Добавление страниц в PostScript
og_description: Узнайте, как установить пользовательский размер страницы в PostScript
  с помощью Aspose.Page для Java. Следуйте пошаговым инструкциям, чтобы добавить страницы,
  задать размеры и эффективно сохранить документ.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Установка пользовательского размера страницы в PostScript с Aspose.Page
  Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Aspose.Page Java Tutorial – установка пользовательского размера страницы при
  добавлении страниц в PostScript
url: /ru/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – установка пользовательского размера страницы при добавлении страниц в PostScript

## Введение
В современных Java‑приложениях часто требуется **set custom page size** для вывода в PostScript — будь то генерация счетов, билетов или пользовательской графики. В этом руководстве показано, как установить пользовательский размер страницы для каждой страницы, добавить несколько страниц и создать файл PostScript, полностью соответствующий вашим требованиям к разметке. Вы получите полностью готовый пример, который можно добавить в любой проект на Java 8+.

## Быстрые ответы
- **Могу ли я установить разные размеры страниц для каждой страницы?** Да—you can open pages with custom dimensions using `document.openPage(width, height)`.  
- **Нужна ли лицензия для использования в продакшн?** A valid Aspose.Page license is required for non‑evaluation deployments.  
- **Какие версии Java поддерживаются?** The library works with Java 8 and newer.  
- **Является ли API потокобезопасным?** Document instances are not thread‑safe; create a separate `PsDocument` per thread.  
- **Насколько большим может быть файл PostScript?** Aspose.Page handles multi‑megabyte files efficiently; memory usage scales with content, not page count.  
- **Могу ли я использовать перегрузку open page width/height?** Конечно—`openPage(double width, double height)` lets you specify any dimensions in points.  

## Требования
- Базовое понимание программирования на Java.  
- Aspose.Page for Java, добавленный в ваш проект (Maven/Gradle или вручную JAR).  
- Среда разработки Java (IDE, JDK 8+).  

## Импорт пакетов
Для этого требуются следующие классы: `FileOutputStream` для записи файлов, `PsDocument` для создания документов PostScript и `PsSaveOptions` для настройки параметров вывода.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Шаг 1: создать многостраничный документ postscript
`PsDocument` — основной класс, представляющий документ PostScript, который может содержать несколько страниц.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Шаг 2: добавить содержимое на первую страницу
После подготовки документа вы можете добавить любое необходимое содержимое на первую страницу. По завершении закройте страницу, чтобы зафиксировать её содержимое.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Как установить пользовательский размер страницы
Пользовательский размер страницы задаётся вызовом `document.openPage(width, height)` с нужными размерами в пунктах до начала рисования любого содержимого. `openPage(width, height)` открывает новую страницу с указанной шириной и высотой, предоставляя полный контроль над холстом страницы. Если размер страницы по умолчанию не подходит, вы можете **set custom page size** при открытии новой страницы. Это полезно для чеков, этикеток или любой нестандартной разметки.

## Шаг 3: добавить вторую страницу с другим размером
Ниже мы открываем вторую страницу и явно указываем пользовательскую ширину и высоту (в пунктах). Это демонстрирует, как установить пользовательский размер страницы для отдельных страниц, позволяя работать с **different page sizes** в одном документе.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Шаг 4: сохранить документ
Наконец, сохраните изменения, сохранив документ. Все страницы, включая те, что имеют пользовательские размеры, записываются в выходной файл.

```java
// Save the document
document.save();
```

Следуя этим шагам, вы сможете без проблем добавлять страницы и **set custom page size** в Java‑документе PostScript с помощью Aspose.Page, получая полный контроль над разметкой каждой страницы.

## Почему стоит использовать Aspose.Page для установки пользовательского размера страницы?
Aspose.Page предоставляет точный контроль над размерами страниц, позволяя задавать любую ширину и высоту в пунктах, комбинировать несколько размеров страниц в одном документе и эффективно передавать содержимое для высокопроизводительной генерации PostScript. Это делает его идеальным для счетов, билетов и крупномасштабной пакетной обработки, где необходимо минимальное использование памяти.

Aspose.Page позволяет задавать точные размеры страниц в пунктах, комбинировать несколько размеров в одном файле и эффективно передавать содержимое, что обеспечивает точный контроль и высокую производительность при генерации PostScript.  
- **Точность:** Размеры задаются в пунктах, что даёт точный контроль над шириной и высотой страницы.  
- **Гибкость:** Сочетайте **different page sizes** в одном файле PostScript.  
- **Производительность:** Библиотека передаёт содержимое напрямую в выходной файл, обрабатывая файлы до 500 МБ при использовании кучи менее 100 МБ, что подходит для крупномасштабных сценариев **generate PostScript file**.  
- **Богатый API:** Поддерживает более 30 графических примитивов, 10 форматов изображений и неограниченное количество текстовых объектов на страницу — всё это учитывает заданные вами пользовательские размеры.

## Распространённые проблемы и решения
| Проблема | Решение |
|-------|----------|
| **Размеры страницы отображаются поменянными местами** | Помните, что `openPage(width, height)` ожидает сначала ширину, затем высоту (обе в пунктах). |
| **Содержимое выходит за пределы страницы** | Используйте систему координат `PsGraphics` для размещения элементов внутри пользовательских границ или масштабируйте рисунок. |
| **Ошибки нехватки памяти при работе с большими документами** | Включите потоковую запись, записывая напрямую в `FileOutputStream`, как показано, и избегайте загрузки больших изображений в память сразу. |

## Часто задаваемые вопросы
### Могу ли я добавить страницы разных размеров в один документ PostScript?
Да, как показано в этом руководстве, вы можете добавлять страницы с разными размерами в многостраничный документ PostScript.

### Есть ли ограничения на количество страниц, которые я могу добавить?
Aspose.Page поддерживает добавление практически неограниченного количества страниц в документ.

### Могу ли я добавить пользовательский контент, такой как изображения или графику, на страницы?
Конечно! Aspose.Page позволяет добавлять широкий спектр контента, включая текст, изображения и другие графические элементы.

### Подходит ли Aspose.Page для работы с большими документами?
Да, Aspose.Page разработан для эффективной работы как с небольшими, так и с большими документами.

### Где я могу найти дополнительные ресурсы и поддержку для Aspose.Page?
Изучите [документацию Aspose.Page](https://reference.aspose.com/page/java/), или посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для получения поддержки от сообщества.

**Дополнительные вопросы и ответы**

**Q:** *Какие форматы изображений поддерживаются при рисовании на странице PostScript?*  
**A:** Вы можете напрямую встраивать изображения PNG, JPEG, BMP и GIF, используя API рисования.

**Q:** *Как изменить DPI по умолчанию для документа?*  
**A:** Установите `PsSaveOptions.setResolution(int dpi)` перед созданием `PsDocument`.

**Q:** *Могу ли я зашифровать файл PostScript паролем?*  
**A:** Сам PostScript не поддерживает шифрование, но вы можете обернуть вывод в PDF и применить настройки безопасности при необходимости.

---

**Последнее обновление:** 2026-10-25  
**Тестировано с:** Aspose.Page for Java 24.10  
**Автор:** Aspose  

## Связанные руководства

- [Как установить размер страницы A4 и создать PostScript в Java с Aspose.Page](/page/java/document-creation/postscript/)
- [Как конвертировать PostScript в PDF с помощью Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Как нарисовать прямоугольник в Java PostScript с Aspose.Page](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}