---
date: 2026-03-13
description: Узнайте, как выполнить конвертацию Aspose Page из XPS в PDF на Java.
  Это пошаговое руководство показывает, как рендерить PDF из XPS, установить номера
  страниц PDF и оптимизировать вывод.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Aspose Page Conversion – Как конвертировать XPS в PDF на Java
url: /ru/java/xps-conversion/to-pdf/
weight: 12
---

 them.

Now ensure we didn't translate any URLs, file paths, variable names. We kept code placeholders unchanged.

Check for any stray formatting: ensure bold and italic remain.

We used **specify PDF page numbers** unchanged inside bold/italic as original. In some places we kept **specify PDF page numbers** bold, and *specify PDF page numbers* italic. Keep same.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование Aspose Page – Как конвертировать XPS в PDF на Java

Преобразование XPS файлов в PDF является распространенной задачей, когда нужен документ в универсальном формате для просмотра. В этом руководстве вы узнаете **aspose page conversion** в действии, используя Aspose.Page for Java для **render PDF from XPS** всего несколькими строками кода. Независимо от того, создаете ли вы систему управления документами, генерируете печатные отчеты или архивируете файлы, это руководство проведет вас через весь процесс, от предварительных требований до устранения неполадок.

## Быстрые ответы
- **Какой библиотекой выполняется преобразование?** Aspose.Page for Java.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базовой настройки.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; лицензия требуется для продакшн.  
- **Можно ли конвертировать только выбранные страницы?** Да — используйте опцию *specify PDF page numbers*.  
- **Является ли преобразование без потерь?** Библиотека сохраняет векторную графику и точность текста.  

## Что такое преобразование Aspose Page из XPS в PDF?
Преобразование Aspose Page преобразует документы XPS (XML Paper Specification) — фиксированный формат Microsoft — в PDF, де‑факто стандарт для обмена и печати. Преобразование сохраняет макет, шрифты и векторную графику, гарантируя, что полученный PDF выглядит точно так же, как оригинальный XPS.

## Почему стоит использовать Aspose.Page for Java для создания PDF из XPS?
- **Высокая точность** – сохраняет векторную графику, шрифты и макет.  
- **Тонкий контроль** – можно задать качество изображений, сжатие и даже выбрать конкретные страницы.  
- **Без внешних зависимостей** – чистый Java, работает на любой платформе, поддерживающей JDK.  
- **Встроенный выбор страниц** – легко **specify PDF page numbers**, чтобы уменьшить размер файла.

## Требования
Перед началом убедитесь, что у вас есть:

- **Java Development Kit (JDK)** – любая современная версия (рекомендовано 8+).  
- **Aspose.Page for Java** – загрузите библиотеку из официальной [documentation](https://reference.aspose.com/page/java/).  
- XPS‑файл, который вы хотите конвертировать.

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые пакеты для работы с Aspose.Page for Java. Этот шаг важен для доступа к функциям, необходимым для преобразования XPS в PDF.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Пошаговое руководство

### Шаг 1: Установить каталог документа
Укажите путь к папке, содержащей ваш исходный XPS‑файл.

```java
String dataDir = "Your Document Directory";
```

### Шаг 2: Инициализировать поток вывода PDF
Создайте `FileOutputStream`, который будет принимать сгенерированный PDF.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Шаг 3: Загрузить документ XPS
Загрузите XPS‑файл с помощью Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Шаг 4: Инициализировать параметры сохранения PDF  
Создайте параметры для преобразования. Здесь вы можете **specify PDF page numbers**, настроить качество изображений и установить сжатие.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Шаг 5: Создать устройство рендеринга PDF  
Настройте устройство рендеринга, которое будет записывать вывод PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Шаг 6: Сохранить документ  
Наконец, сохраните документ XPS как PDF, используя настроенные параметры и устройство.

```java
document.save(device, options);
```

Повторите эти шаги, корректируя пути к файлам и параметры в соответствии с вашей конкретной ситуацией.

## Как указать номера страниц PDF при конвертации XPS
Если вам нужен только подмножество страниц из оригинального XPS, заполните массив `setPageNumbers` нужными индексами страниц (начиная с 1). Это помогает уменьшить размер файла и время обработки.

## Распространённые проблемы и их устранение
- **FileNotFoundException** – Убедитесь, что `dataDir` указывает на правильную папку и имя XPS‑файла совпадает.  
- **LicenseException** – Для использования в продакшн требуется действительная лицензия Aspose.Page; иначе библиотека работает в режиме оценки с водяным знаком.  
- **Low image quality** – Увеличьте `setJpegQualityLevel` или переключитесь на без потерь сжатие при необходимости.

## Часто задаваемые вопросы
### Могу ли я конвертировать XPS‑файлы с несколькими страницами, используя Aspose.Page for Java?
Да, вы можете **specify PDF page numbers** в `PdfSaveOptions` (см. Шаг 4), чтобы включить любые необходимые страницы.

### Где я могу найти дополнительную поддержку или обсудить вопросы, связанные с Aspose.Page?
Посетите [Aspose.Page forum](https://forum.aspose.com/c/page/39) для поддержки сообщества и обсуждений.

### Есть ли бесплатная пробная версия Aspose.Page for Java?
Да, вы можете изучить возможности с помощью [free trial](https://releases.aspose.com/).

### Как получить временную лицензию для Aspose.Page for Java?
Перейдите по [this link](https://purchase.aspose.com/temporary-license/) для получения информации о временной лицензии.

### Где можно приобрести лицензию Aspose.Page for Java?
Вы можете купить лицензию [here](https://purchase.aspose.com/buy).

**Последнее обновление:** 2026-03-13  
**Тестировано с:** Aspose.Page for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}