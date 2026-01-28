---
date: 2026-01-28
description: Узнайте, как создавать документы PostScript A4 на Java с помощью Aspose.Page,
  добавлять пользовательские шрифты Java и задавать размер страницы PostScript. Попробуйте
  бесплатную пробную версию уже сегодня!
linktitle: Create Document in Java with PostScript
second_title: Aspose.Page Java API
title: Как создать PostScript A4 на Java с помощью Aspose.Page
url: /ru/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать postscript a4 java с помощью Aspose.Page

## Введение
Если вам нужно **create postscript a4 java** файлы напрямую из Java, Aspose.Page делает это быстро и надёжно. В этом руководстве мы пройдём весь процесс — как создать PostScript, установить размер страницы PostScript на A4 и **add custom fonts**, если это требуется. К концу вы получите готовый фрагмент кода, который можно вставить в любой Java‑проект.

## Быстрые ответы
- **What is the primary library?** Aspose.Page for Java.  
- **Which page size does this guide focus on?** A4 (portrait).  
- **Can I use my own fonts?** Yes – add custom fonts via the additional fonts folder.  
- **Do I need a license for production?** A commercial license is required; a free trial is available.  
- **What Java version is supported?** Java 8 and later.

## Как создать postscript a4 java
Этот раздел повторяет основную цель и предоставляет краткое определение, чтобы поисковые системы могли сразу показать ответ.

## Что такое **postscript a4 size**?
Размер PostScript A4 относится к странице, оформленной согласно размерам ISO 216 A4 (210 мм × 297 мм) с использованием языка описания страниц PostScript. Это стандартный размер страницы для многих деловых документов по всему миру.

## Почему использовать Aspose.Page для **set postscript page size**?
Aspose.Page абстрагирует низкоуровневые команды PostScript, позволяя сосредоточиться на макете документа, а не на тонкостях языка. Вы получаете:
- Точный контроль над размерами страницы (включая A4).  
- Лёгкую интеграцию пользовательских шрифтов без необходимости менять системные пути к шрифтам.  
- Поддержку как одностраничных, так и многостраничных выводов.

## Как добавить custom fonts java
Встраивание собственных шрифтов гарантирует, что сгенерированный документ будет выглядеть точно так, как задумано, на любом принтере или вьювере.

## Требования
Перед началом убедитесь, что у вас есть:

- Практические знания программирования на Java.  
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

Теперь разобьём пример на чёткие, пронумерованные шаги.

### Шаг 1: Установить каталог документа
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Замените `"Your Document Directory"` на абсолютный путь, где вы хотите хранить сгенерированные файлы.

### Шаг 2: Определить папку шрифтов
```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```
Поместите любые **custom fonts**, которые вы хотите использовать, в эту папку. Aspose.Page автоматически загрузит их, когда вы позже укажете дополнительную папку шрифтов.

### Шаг 3: Создать поток вывода для документа PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```
Этот поток указывает на файл, который будет содержать окончательный вывод **PostScript A4 size**.

### Шаг 4: Создать параметры сохранения с размером A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```
Здесь мы **set the PostScript page size** на A4 (портрет). Если нужен другой ориентир, просто измените константу.

### Шаг 5: Установить поля страницы и добавить папку пользовательских шрифтов
```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```
Мы убираем все поля (ноль) для полно‑кроватной страницы и указываем Aspose.Page, где искать **custom fonts**, добавленные ранее.

### Шаг 6: Создать многостраничный или одностраничный PS‑документ
```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```
Установите `multiPaged` в `true`, если требуется более одной страницы; иначе будет создан одностраничный документ.

### Шаг 7: Закрыть текущую страницу и сохранить документ
```java
document.closePage();
document.save();
```
Эти вызовы завершают документ, закрывают активную страницу и записывают файл **PostScript A4 size** на диск.

## Распространённые проблемы и советы
- **Font not appearing?** Убедитесь, что файл шрифта поддерживается в формате TrueType или OpenType и что путь в `FONTS_FOLDER` заканчивается слешем (`/`).  
- **Margins still showing?** Убедитесь, что вызываете `options.setMargins(...)` **before** созданием `PsDocument`.  
- **Multi‑page output looks blank?** Не забудьте вызвать `document.newPage()` для каждой дополнительной страницы, которую хотите добавить.

## Часто задаваемые вопросы

**Q: Can I use custom fonts in my PostScript document?**  
A: Да, можете. Убедитесь, что задали дополнительную папку шрифтов в параметрах сохранения (см. Шаг 5).

**Q: Is there a trial version available for Aspose.Page for Java?**  
A: Да, вы можете получить бесплатную пробную версию [here](https://releases.aspose.com/).

**Q: How can I access the full API reference?**  
A: Обратитесь к документации [here](https://reference.aspose.com/page/java/).

**Q: Where do I purchase a license for Aspose.Page for Java?**  
A: Вы можете купить лицензию [here](https://purchase.aspose.com/buy).

**Q: Is there a community forum for Aspose.Page discussions?**  
A: Да, присоединяйтесь к сообществу [forum](https://forum.aspose.com/c/page/39) для поддержки и советов по лучшим практикам.

**Q: Can I generate multi‑page PostScript files?**  
A: Конечно — установите `multiPaged` в `true` в Шаге 6 и вызовите `document.newPage()` для каждой дополнительной страницы.

## Заключение
Следуя этим шагам, вы теперь знаете **how to create postscript a4 java** файлы с помощью Aspose.Page, а также как **add custom fonts java** и управлять параметрами **set postscript page size**. Aspose.Page берёт на себя сложную часть, позволяя вам сосредоточиться на содержимом ваших документов.

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}