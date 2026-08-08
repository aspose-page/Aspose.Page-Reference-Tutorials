---
date: 2026-06-20
description: Узнайте, как установить размер страницы A4, создать файлы PostScript
  в Java и добавить пользовательские шрифты с помощью Aspose.Page. Попробуйте бесплатную
  пробную версию сегодня!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Создать документ в Java с PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Как установить размер страницы A4 и создать PostScript в Java с Aspose.Page
url: /ru/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить размер страницы A4 и создать PostScript в Java с помощью Aspose.Page

## Введение
Если вам нужно **set a4 page size** при генерации файлов PostScript из Java, Aspose.Page предоставляет быстрый, надёжный API, скрывающий детали низкого уровня. В этом руководстве мы пройдем весь процесс — создание документа PostScript, настройку размеров страницы A4 и **adding custom fonts**, если это необходимо. К концу вы получите готовый фрагмент кода, который можно вставить в любой проект Java.

## Быстрые ответы
- **Какая библиотека создает PostScript в Java?** Aspose.Page for Java.  
- **Какой размер страницы рассматривается в этом руководстве?** A4 (210 mm × 297 mm).  
- **Могу ли я встроить свои собственные шрифты?** Yes – set the additional fonts folder in the save options.  
- **Нужна ли лицензия для продакшна?** A commercial license is required; a free trial is available.  
- **Какие версии Java поддерживаются?** Java 8 and later.

## Как установить размер страницы a4 и создать postscript в Java
Загрузите библиотеку Aspose.Page, настройте `PsSaveOptions` с константами A4 и запишите документ в файл — всё это менее чем в десяти строках кода. Такой прямой подход гарантирует правильные размеры страницы и позволяет добавлять пользовательские шрифты без дополнительной конфигурации.

## Что такое размер postscript a4?
Размер PostScript A4 — это стандарт ISO 216 (210 mm × 297 mm), выраженный в языке описания страниц PostScript. Он определяет печатную область, которую интерпретируют принтеры и просмотрщики, обеспечивая согласованную разметку на разных платформах. Поскольку PostScript описывает содержимое страницы независимо от устройства, использование размера A4 гарантирует одинаковый вид документа на любом принтере или просмотрщике, поддерживающем формат A4, по всему миру.

## Почему использовать Aspose.Page для установки размера страницы postscript?
Aspose.Page поддерживает **30+ PostScript operators** и может генерировать файлы до **500 MB** без загрузки всего документа в память. Это даёт точный контроль над размерами страниц при работе с большими нагрузками. Библиотека также абстрагирует сложный синтаксис PostScript, автоматически управляет ресурсами и обеспечивает высокопроизводительный стриминг, что делает её идеальной как для простых одностраничных листовок, так и для сложных многостраничных отчётов.

## Как добавить пользовательские шрифты java
Встраивание собственных шрифтов гарантирует, что сгенерированный документ будет выглядеть точно так же на любом принтере или просмотрщике, а Aspose.Page автоматически обнаруживает шрифты, помещённые в указанную папку. Зарегистрировав дополнительную папку со шрифтами, вы можете использовать любые TrueType или OpenType шрифты, избегать замен по умолчанию и поддерживать единый брендовый стиль на всех устройствах вывода.

## Требования
Перед началом убедитесь, что у вас есть:

- Знание программирования на Java.  
- Aspose.Page for Java установлен. Вы можете скачать его [here](https://releases.aspose.com/page/java/).  
- Папка с именем `necessary_fonts` (или любое другое название), содержащая любые пользовательские шрифты, которые вы хотите встроить.

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые классы Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Now let’s break the example into clear, numbered steps.

### Шаг 1: Установить каталог документа
Константа `OUTPUT_DIR` указывает библиотеке, куда записывать сгенерированный файл.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Шаг 2: Определить папку шрифтов
`FONTS_FOLDER` указывает каталог, в котором находятся ваши пользовательские TrueType или OpenType шрифты.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Шаг 3: Создать поток вывода для документа PostScript
`FileOutputStream` открывает поток, который получит окончательный вывод PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Шаг 4: Создать параметры сохранения с размером A4
`PsSaveOptions` позволяет указать целевой размер страницы.  
**Definition:** `PsPageSize` — это перечисление, содержащее стандартные константы размеров страниц, такие как A4, Letter и Legal.  
Установка `options.setPageSize(PsPageSize.A4)` конфигурирует документ для стандартных размеров A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Шаг 5: Установить поля страницы и добавить папку пользовательских шрифтов
`options.setMargins(0, 0, 0, 0)` убирает все поля для полноформатной печати, а `options.setAdditionalFontsFolder(FONTS_FOLDER)` регистрирует ваши пользовательские шрифты.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Шаг 6: Создать многостраничный или одностраничный PS документ
`PsDocument document = new PsDocument(outputStream, options)` создаёт документ. `PsDocument` представляет документ PostScript, который может содержать одну или несколько страниц. Установите `multiPaged` в `true` для многостраничного вывода.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Шаг 7: Закрыть текущую страницу и сохранить документ
Вызов `document.close()` завершает файл и записывает **PostScript A4 size** вывод на диск.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Распространённые проблемы и советы
- **Font not appearing?** Проверьте, что файл шрифта поддерживается в формате TrueType или OpenType и что `FONTS_FOLDER` заканчивается слешем (`/`).  
- **Margins still showing?** Вызовите `options.setMargins(...)` **до** создания `PsDocument`.  
- **Multi‑page output looks blank?** Не забудьте вызвать `document.newPage()` для каждой дополнительной страницы, которую хотите добавить.

## Часто задаваемые вопросы

**Q: Могу ли я использовать пользовательские шрифты в моём PostScript документе?**  
A: Yes, set the additional fonts folder in the save options (see Step 5) and Aspose.Page will embed the fonts automatically.

**Q: Есть ли доступна пробная версия Aspose.Page for Java?**  
A: Yes, you can get a free trial [here](https://releases.aspose.com/).

**Q: Как получить доступ к полной справке API?**  
A: Refer to the documentation [here](https://reference.aspose.com/page/java/).

**Q: Где купить лицензию на Aspose.Page for Java?**  
A: You can buy a license [here](https://purchase.aspose.com/buy).

**Q: Где можно задать вопросы сообществу?**  
A: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).

**Q: Могу ли я генерировать многостраничные PostScript файлы?**  
A: Absolutely—set `multiPaged` to `true` in Step 6 and call `document.newPage()` for each extra page.

## Заключение
Следуя этим шагам, вы теперь знаете **how to set a4 page size** и создавать **PostScript** файлы в Java с Aspose.Page, а также **add custom fonts java** и управлять параметрами размера страницы. Aspose.Page берёт на себя сложную часть, позволяя вам сосредоточиться на содержимом ваших документов.

---

**Последнее обновление:** 2026-06-20  
**Тестировано с:** Aspose.Page for Java 24.11  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Aspose.Page Java Tutorial – установить пользовательский размер страницы при добавлении страниц в PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Как добавить текст в PostScript с помощью Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial - Конвертировать PostScript в PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```