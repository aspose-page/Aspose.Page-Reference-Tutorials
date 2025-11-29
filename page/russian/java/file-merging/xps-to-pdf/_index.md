---
date: 2025-11-29
description: Узнайте, как сохранять XPS в PDF на Java с помощью Aspose.Page Java.
  Следуйте нашему пошаговому руководству для эффективного преобразования XPS в PDF
  и настройки сжатия PDF.
language: ru
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Конвертировать XPS в PDF в Java с использованием Aspose.Page Java
url: /java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование XPS в PDF на Java с использованием Aspose.Page Java

## Введение
В этом руководстве вы узнаете **как преобразовать XPS в PDF на Java с помощью Aspose.Page Java**, мощную библиотеку, предназначенную для конвертации документов Java. Независимо от того, нужно ли вам пакетно обрабатывать счета, генерировать печатные отчёты или просто мигрировать устаревшие файлы XPS, Aspose.Page Java делает задачу быстрой, надёжной и полностью настраиваемой.

## Быстрые ответы
- **Какая библиотека обрабатывает конвертацию XPS в PDF?** Aspose.Page Java  
- **Сколько времени занимает базовая конвертация?** Обычно менее секунды для одностраничного XPS‑файла.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для оценки; лицензия требуется для продакшн.  
- **Можно ли управлять сжатием PDF?** Да — используйте `PdfSaveOptions` для настройки сжатия изображений и текста.  
- **Какая версия Java требуется?** Java 8 или новее (рекомендуется JDK 11+).  

## Что такое Aspose.Page Java?
Aspose.Page Java — это **высокопроизводительный API**, позволяющий разработчикам программно создавать, редактировать и конвертировать XPS‑документы. Он поддерживает рендеринг XPS в PDF, PNG, JPEG и другие форматы, предоставляя детальный контроль над настройками вывода, такими как **set PDF compression**.

## Почему стоит использовать Aspose.Page Java для конвертации XPS‑в‑PDF?
- **Рендеринг без зависимостей** – без нативных библиотек или внешних инструментов.  
- **Точное сохранение макета** – PDF‑вывод точно повторяет оригинальный вид XPS.  
- **Полный контроль над выводом PDF** – вы можете регулировать качество изображений, выбирать алгоритмы сжатия и выбирать конкретные страницы для рендеринга.  
- **Кроссплатформенность** – работает на Windows, Linux и macOS с любой стандартной JDK.  

## Предварительные требования
Перед началом убедитесь, что у вас есть:

1. **Java Development Kit (JDK) 8+** – рекомендуется использовать последнюю JDK для повышения производительности и безопасности.  
2. **Библиотека Aspose.Page for Java** – скачайте JAR с официальной [документации Aspose.Page Java](https://reference.aspose.com/page/java/).  
3. **IDE** (IntelliJ IDEA, Eclipse, VS Code) или простой текстовый редактор плюс инструменты сборки командной строки (Maven/Gradle).  

## Импорт пакетов
Add the required imports to your Java class so you can work with XPS documents and PDF output.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Пошаговое руководство

### Шаг 1: Установите путь к каталогу документов
Define the folder that contains your source XPS file and where the PDF will be saved.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Шаг 2: Инициализируйте поток вывода PDF
Create a `FileOutputStream` that points to the destination PDF file.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Совет:** Используйте `try‑with‑resources` для автоматического закрытия потока и предотвращения утечек ресурсов.

### Шаг 3: Загрузите XPS‑документ
Instantiate an `XpsDocument` object by loading the source XPS file.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Шаг 4: Инициализируйте параметры сохранения PDF (Set PDF Compression)
Configure how the PDF should be compressed. This step lets you **set PDF compression** for images and text, which reduces file size without sacrificing quality.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Почему это важно:** Регулировка качества JPEG и типов сжатия может уменьшить PDF размером 10 МБ до менее 2 МБ, сохраняя необходимую визуальную точность.

### Шаг 5: Создайте устройство рендеринга для формата PDF
The `PdfDevice` streams the rendered pages into the PDF output stream.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Шаг 6: Сохраните документ
Finally, render the XPS content to PDF using the configured options.

```java
document.save(device, options);
```

> **Результат:** После выполнения файл `XPStoPDF.pdf` появится в папке `dataDir`, содержащий конвертированные страницы с указанными настройками сжатия.

## Распространённые проблемы и решения

| Issue | Cause | Solution |
|-------|-------|----------|
| **`FileNotFoundException`** | Неправильный путь `dataDir` | Убедитесь, что каталог существует и приложение имеет права чтения/записи. |
| **Blank PDF pages** | Отсутствует инициализация `PdfDevice` | Убедитесь, что `PdfDevice` создан с тем же `FileOutputStream`, который используется для вывода. |
| **Large PDF size** | Сжатие по умолчанию низкое | Увеличьте `setJpegQualityLevel` или переключитесь на `PdfImageCompression.Jpeg` с более низким уровнем качества. |
| **Only some pages appear** | Фильтр `setPageNumbers` исключает страницы | Отрегулируйте массив, чтобы включить все необходимые номера страниц, или удалите вызов, чтобы экспортировать все страницы. |

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Page Java с разными версиями Java?**  
A: Да, Aspose.Page Java поддерживает Java 8 до Java 21, включая дистрибутивы Oracle и OpenJDK.

**Q: Можно ли настроить параметры сжатия для конвертированного PDF?**  
A: Конечно. Используйте `PdfSaveOptions` для установки качества JPEG, типа сжатия изображений и сжатия текста, как показано в Шаге 4.

**Q: Где можно найти дополнительную поддержку или обсуждения сообщества?**  
A: Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для помощи сообщества, примеров кода и советов по устранению неполадок.

**Q: Доступна ли бесплатная пробная версия.Page?**  
A: Да, вы можете скачать полностью функциональную пробную версию со [страницы загрузки Aspose](https://releases.aspose.com/).

**Q: Как получить временную лицензию для Aspose.Page?**  
A: Временную лицензию можно запросить [здесь](https://purchase.aspose.com/temporary-license/).

## Заключение
Используя **Aspose.Page Java**, вы можете без усилий **сохранять XPS как PDF** и контролировать каждый аспект вывода, от выбора страниц до сжатия. Это руководство охватывает всё, что необходимо для интеграции конвертации XPS‑в‑PDF в ваши Java‑приложения, будь то однократная утилита или масштабный конвейер обработки документов.

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}