---
date: 2026-05-25
description: Узнайте, как читать XMP с помощью aspose.page на Java. Это пошаговое
  руководство показывает, как извлекать XMP metadata, creator info, timestamps, thumbnails
  и многое другое.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Как читать XMP Metadata с помощью Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Чтение XMP с помощью Aspose.Page – руководство по Java
url: /ru/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить метаданные из XMP с помощью Java

## Как читать XMP с помощью Aspose.Page (Java)?

Load the EPS file with `new Document("file.eps")`—the `Document` class represents a loaded file. Call `getXmpMetadata()`, which extracts the XMP packet, and then query the returned `XmpMetadata` object—a map‑like interface for XMP properties—to retrieve the keys you need. This is all required to read XMP using Aspose.Page. The API abstracts the low‑level parsing, so you get a ready‑to‑use map of properties in just two lines of code.

Загрузите EPS‑файл с помощью `new Document("file.eps")` — класс `Document` представляет загруженный файл. Вызовите `getXmpMetadata()`, который извлекает пакет XMP, а затем запросите возвращённый объект `XmpMetadata` — интерфейс, похожий на карту, для свойств XMP, чтобы получить необходимые ключи. Это всё, что требуется для чтения XMP с помощью Aspose.Page. API абстрагирует низкоуровневый разбор, поэтому вы получаете готовую к использованию карту свойств всего в две строки кода.

Welcome to our step‑by‑step tutorial that shows **how to read XMP** metadata with Java and the Aspose.Page library. XMP (Extensible Metadata Platform) is a widely adopted standard for embedding rich metadata inside documents. By the end of this guide you’ll be able to read document format XMP, pull out creator information, timestamps, thumbnails, and more—empowering you to build smarter document‑analysis solutions.

Добро пожаловать в наш пошаговый учебник, который показывает **как читать XMP** метаданные с помощью Java и библиотеки Aspose.Page. XMP (Extensible Metadata Platform) — широко принятый стандарт для встраивания богатых метаданных в документы. К концу этого руководства вы сможете читать XMP формата документа, извлекать информацию о создателе, временные метки, миниатюры и многое другое — что позволит вам создавать более интеллектуальные решения для анализа документов.

## Быстрые ответы
- **Что означает «читать XMP»?** Это означает программное извлечение пакета XMP, который хранит метаданные внутри файла.  
- **Какая библиотека требуется?** Aspose.Page for Java (скачайте с официальной страницы [здесь](https://releases.aspose.com/page/java/)).  
- **Нужна ли лицензия?** Для продакшн требуется временная или полная лицензия; бесплатная пробная версия подходит для оценки.  
- **Какая версия Java поддерживается?** Java 8 или выше.  
- **Можно ли читать XMP из других форматов?** Да — Aspose.Page извлекает XMP из EPS, PDF, JPEG, PNG и более чем 20 других форматов.

## Требования
Before diving into the code, make sure you have:

Прежде чем погрузиться в код, убедитесь, что у вас есть:

- **Java Development Kit (JDK)** — установленный и настроенный Java 8+ на вашем компьютере.  
- **Aspose.Page for Java** — скачайте библиотеку с официального сайта [здесь](https://releases.aspose.com/page/java/).  
- EPS‑файл, содержащий XMP‑метаданные (например, `xmp1.eps`).  

## Импорт пакетов
The `XmpMetadata` class lives in the `com.aspose.page.xmp` namespace, while the `Document` class is in `com.aspose.page`. Import both so you can work with the EPS file and its metadata.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Шаг 1: Инициализировать поток входного EPS‑файла
Begin by setting the path to your document directory and initializing the input EPS file stream.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Шаг 2: Получить XMP‑метаданные
`XmpMetadata` — объект Aspose.Page, который хранит пакет XMP, извлечённый из документа. Получите его с помощью `document.getXmpMetadata()`. Если файл не содержит XMP, API синтезирует минимальный пакет из существующих комментариев PostScript.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Шаг 3: Извлечь информацию CreatorTool
The `CreatorTool` key lives under the `xmp` namespace and records the application that generated the file. Check for its presence and print the value.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Шаг 4: Извлечь информацию CreateDate
`CreateDate` хранит временную метку, когда документ был первоначально создан. Используйте тот же шаблон `containsKey`/`get` для чтения.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Шаг 5: Получить ширину миниатюры
If thumbnails exist, the `xmp:Thumbnails` array holds one or more entries. Each entry contains `width`, `height`, and binary data. The example extracts the width of the first thumbnail.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Шаг 6: Извлечь информацию о формате
The `format` key tells you the original file format (e.g., “application/postscript”). This is useful when you need to log or validate source types.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Шаг 7: Получить DocumentID
`DocumentID` — уникальный идентификатор, присвоенный приложением‑создателем. Его можно использовать для дедупликации в больших библиотеках ресурсов.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Почему это важно
Aspose.Page может читать XMP из **более 20** форматов файлов и обрабатывает документы до **500 МБ** без загрузки всего файла в память, предоставляя быстрый и малозатратный доступ к важным метаданным. Эта возможность критична для конвейеров пакетной обработки, систем управления цифровыми активами и любых решений, которые опираются на поисковые, машинно‑читаемые атрибуты документов.

## Распространённые ошибки и советы
- **Отсутствие XMP:** Некоторые EPS‑файлы могут не содержать XMP. Вызов `getXmpMetadata()` синтезирует минимальный набор на основе существующих PS‑комментариев, но вы не получите полные метаданные, если они не встроены.  
- **Массивы миниатюр:** Ключ `xmp:Thumbnails` может содержать несколько записей. Пример извлекает только первую; переберите массив, если нужны все миниатюры.  
- **Осведомлённость о пространствах имён:** Ключи XMP используют пространства имён (например, `xmp:`, `dc:`). Убедитесь, что вы указываете точное имя ключа; иначе `containsKey` вернёт false.  

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java с другими языками программирования?
Да, Aspose.Page поддерживает Java, .NET и несколько других языков. Полный список см. в [документации](https://reference.aspose.com/page/java/).

### Доступна ли бесплатная пробная версия Aspose.Page для Java?
Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

### Где я могу найти поддержку Aspose.Page для Java?
Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для помощи сообщества и официальной поддержки.

### Как получить временную лицензию для Aspose.Page для Java?
Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### Есть ли дополнительные ресурсы для Aspose.Page для Java?
Изучите полную [документацию](https://reference.aspose.com/page/java/) и скачайте библиотеку [здесь](https://releases.aspose.com/page/java/).

## Дополнительные вопросы
**В: Работает ли этот подход с PDF‑файлами, содержащими XMP?**  
О: Да, Aspose.Page может читать XMP из PDF, EPS и нескольких форматов изображений.

**В: Можно ли изменить XMP‑метаданные после их чтения?**  
О: Абсолютно. Объект `XmpMetadata` изменяемый; вы можете добавлять, обновлять или удалять ключи, а затем сохранять документ.

**В: Есть ли способ извлечь все изображения миниатюр, а не только их размеры?**  
О: Вы можете получить бинарные данные из свойства `xmpGImg:data` каждой записи миниатюры и записать их в файл.

## Заключение
Теперь вы освоили **как читать XMP** метаданные с помощью Java и Aspose.Page. Следуя этим шагам, вы можете извлекать инструменты создателя, временные метки, миниатюры, информацию о формате и идентификаторы документов — получая полное представление о встроенных метаданных ваших EPS‑файлов. Не стесняйтесь экспериментировать с дополнительными пространствами имён XMP, чтобы получать ещё более богатые данные для ваших приложений.

---

**Последнее обновление:** 2026-05-25  
**Тестировано с:** Aspose.Page for Java 24.12 (latest)  
**Автор:** Aspose

## Связанные учебники

- [Учебник Aspose Page Java — Добавить XMP‑метаданные в EPS‑файлы](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Учебник aspose.page xmp — Добавить пространство имён в XMP с помощью Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Учебник aspose page xmp — Изменить именованное значение в XMP с помощью Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}