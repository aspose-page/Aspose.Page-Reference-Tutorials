---
date: 2026-11-19
description: Узнайте, как создавать файлы PostScript в Java, задавать размер страницы
  A4 и добавлять пользовательские шрифты с помощью Aspose.Page. Попробуйте бесплатную
  пробную версию уже сегодня!
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: Создать документ в Java с PostScript
og_description: Узнайте, как создать файл PostScript в Java, задать размер страницы
  A4 и добавить пользовательские шрифты с Aspose.Page. Краткое руководство для разработчиков.
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: Создать файл PostScript в Java с размером A4 с использованием Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: Как создать файл PostScript в Java с размером A4
url: /ru/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать файл PostScript в Java с размером A4

## Введение
Если вам нужно **create PostScript file Java** при установке стандартных размеров страницы A4, Aspose.Page for Java предоставляет лаконичное, высокопроизводительное API, которое абстрагирует низкоуровневый синтаксис PostScript. В этом руководстве мы пройдем каждый шаг — от загрузки библиотеки и настройки `PsSaveOptions` до внедрения ваших собственных шрифтов TrueType или OpenType. К концу вы получите готовый фрагмент кода, который можно вставить в любой проект Java.

## Быстрые ответы
- **Какая библиотека создает PostScript в Java?** Aspose.Page for Java.  
- **Какой размер страницы рассматривается в этом руководстве?** A4 (210 mm × 297 mm).  
- **Можно ли внедрить свои шрифты?** Да — укажите дополнительную папку со шрифтами в параметрах сохранения.  
- **Нужна ли лицензия для продакшн?** Требуется коммерческая лицензия; доступна бесплатная пробная версия.  
- **Какие версии Java поддерживаются?** Java 8, 11 и 17 полностью поддерживаются.

## Как установить размер A4 и создать PostScript в Java?
Загрузите библиотеку Aspose.Page, настройте `PsSaveOptions` с константами A4 и запишите документ в файл — всё это менее чем в десяти строках кода. Такой подход гарантирует правильные размеры страницы и позволяет добавить пользовательские шрифты без дополнительной конфигурации.

## Что такое размер PostScript A4?
Размер PostScript A4 — это стандарт ISO 216 (210 mm × 297 mm), представленный в языке описания страниц PostScript. Он определяет печатную область, которую интерпретируют принтеры и просмотрщики, обеспечивая согласованную разметку на разных платформах. Поскольку PostScript описывает содержимое страницы независимо от устройства, использование размера A4 гарантирует, что документ будет выглядеть одинаково на любом принтере или просмотрщике, поддерживающем формат A4, по всему миру.

## Почему использовать Aspose.Page для установки размера страницы PostScript?
Aspose.Page поддерживает более 30 операторов PostScript и может генерировать файлы размером до 500 МБ без загрузки всего документа в память. Он обрабатывает документ из 200 страниц менее чем за 2 секунды, обеспечивая точный контроль над размерами страниц при эффективной работе с большими нагрузками. Библиотека также абстрагирует сложный синтаксис PostScript и автоматически управляет ресурсами, что делает её идеальной как для простых листовок, так и для сложных многостраничных отчётов.

## Как добавить пользовательские шрифты в Java
Встраивание собственных шрифтов гарантирует, что сгенерированный документ будет выглядеть точно так же, как задумано, на любом принтере или просмотрщике, а Aspose.Page автоматически обнаруживает шрифты, размещённые в указанной папке. Зарегистрировав дополнительную папку со шрифтами, вы можете использовать любой шрифт TrueType или OpenType, избегать замен по умолчанию и поддерживать согласованность бренда на всех устройствах вывода.

## Предварительные требования
Перед началом убедитесь, что у вас есть:

- Практические знания программирования на Java.  
- Установленный Aspose.Page for Java. Вы можете скачать его со страницы [Aspose.Page Java download page](https://releases.aspose.com/page/java/).  
- Папка с именем `necessary_fonts` (или любое другое название), содержащая пользовательские шрифты, которые вы хотите встроить.

## Импорт пакетов
В вашем проекте Java импортируйте необходимые классы Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Теперь разобьем пример на четкие, пронумерованные шаги.

### Шаг 1: установить каталог документа
Константа `OUTPUT_DIR` указывает библиотеке, куда записывать сгенерированный файл.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Шаг 2: определить папку шрифтов
`FONTS_FOLDER` указывает на каталог, содержащий ваши пользовательские шрифты TrueType или OpenType.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Шаг 3: создать поток вывода для документа PostScript
`FileOutputStream` открывает поток, который получит окончательный вывод PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Шаг 4: создать параметры сохранения с размером A4
`PsSaveOptions` определяет, как сохраняется документ PostScript, включая размер страницы, поля и сжатие.  
**Определение:** `PsPageSize` — это перечисление, содержащее стандартные константы размеров страниц, такие как A4, Letter и Legal.  
Установка `options.setPageSize(PsPageSize.A4)` настраивает документ на стандартные размеры A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Шаг 5: установить поля страницы и добавить папку пользовательских шрифтов
`options.setMargins(0, 0, 0, 0)` удаляет все поля для полноформатной страницы, а `options.setAdditionalFontsFolder(FONTS_FOLDER)` регистрирует ваши пользовательские шрифты.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Шаг 6: создать многостраничный или одностраничный документ PS
`PsDocument` представляет документ PostScript, который может содержать одну или несколько страниц. Создание его с помощью `new PsDocument(outputStream, options)` создает объект документа. Установите `multiPaged` в `true` для многостраничного вывода, затем вызывайте `document.newPage()` для каждой дополнительной страницы, которую требуется добавить.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Шаг 7: закрыть текущую страницу и сохранить документ
Вызов `document.close()` завершает файл и записывает вывод **PostScript A4 size** на диск.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Распространённые проблемы и советы
- **Шрифт не отображается?** Убедитесь, что файл шрифта поддерживается в формате TrueType или OpenType и что `FONTS_FOLDER` заканчивается слешем (`/`).  
- **Поля всё ещё видны?** Вызовите `options.setMargins(...)` **до** создания `PsDocument`.  
- **Многостраничный вывод пустой?** Не забудьте вызвать `document.newPage()` для каждой дополнительной страницы.  
- **Большие файлы вызывают ошибки out‑of‑memory?** Aspose.Page передаёт данные потоками, поэтому вы можете безопасно генерировать файлы до 500 МБ; просто убедитесь, что размер кучи JVM составляет минимум 1 ГБ для очень больших нагрузок.

## Часто задаваемые вопросы

**Q: Можно ли использовать пользовательские шрифты в моём документе PostScript?**  
A: Да, укажите дополнительную папку со шрифтами в параметрах сохранения (см. Шаг 5), и Aspose.Page автоматически внедрит шрифты.

**Q: Доступна ли пробная версия Aspose.Page for Java?**  
A: Да, вы можете получить бесплатную пробную версию [Aspose.Page free trial page](https://releases.aspose.com/).

**Q: Как получить доступ к полной справке API?**  
A: Обратитесь к документации [API reference documentation](https://reference.aspose.com/page/java/).

**Q: Где купить лицензию на Aspose.Page for Java?**  
A: Вы можете приобрести лицензию на странице [license purchase page](https://purchase.aspose.com/buy).

**Q: Где я могу задать вопрос сообществу?**  
A: Посетите форум сообщества Aspose.Page [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

**Q: Можно ли генерировать многостраничные файлы PostScript?**  
A: Конечно — установите `multiPaged` в `true` в Шаге 6 и вызывайте `document.newPage()` для каждой дополнительной страницы.

## Заключение
Следуя этим шагам, вы теперь знаете **how to create PostScript file Java** и как установить **A4 page size** с помощью Aspose.Page, а также можете **add custom fonts java** и управлять параметрами размера страниц. Aspose.Page берёт на себя сложную работу, позволяя вам сосредоточиться на содержимом документов, а не на тонкостях языка PostScript.

---

**Последнее обновление:** 2026-11-19  
**Тестировано с:** Aspose.Page for Java 24.11  
**Автор:** Aspose  

## Связанные руководства

- [Aspose.Page Java Tutorial – установить пользовательский размер страницы при добавлении страниц в PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Как добавить текст в PostScript с помощью Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial - Конвертировать PostScript в PDF](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}