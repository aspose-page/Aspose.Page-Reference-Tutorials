---
date: 2026-05-20
description: Узнайте, как добавить XMP‑метаданные в файлы EPS с помощью Aspose.Page
  for Java. Пошаговое руководство по программному внедрению простых XMP‑свойств.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Добавить простые свойства в XMP с использованием Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Добавить XMP‑метаданные в файлы EPS с помощью Java
url: /ru/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить XMP Metadata в файлы EPS с помощью Java

## Введение
В современных графических конвейерах возможность **add XMP metadata** в файлы EPS программно дает вам полный контроль над тем, как ваши иллюстрации описываются, ищутся и архивируются. С помощью Aspose.Page for Java вы можете читать, изменять и записывать XMP‑пакеты внутри EPS‑документов, не покидая экосистему Java. В этом руководстве мы пошагово покажем, как добавить простые XMP‑свойства в файл EPS, чтобы быстро и надёжно обогатить графику пользовательскими метаданными.

## Быстрые ответы
- **Что означает “add XMP metadata to EPS”?** Встраивание XMP‑пакета (метаданных на основе XML) в файл EPS.  
- **Какая библиотека требуется?** Aspose.Page for Java (доступна для загрузки на сайте Aspose).  
- **Нужна ли лицензия для тестирования?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Сколько строк кода?** Менее 30 строк Java плюс несколько операторов import.  
- **Можно ли добавить другие типы данных?** Да — поддерживаются даты, целые числа, числа с плавающей точкой, строки и даже массивы.

## Как добавить XMP metadata в файлы EPS с помощью Java?
Загрузите файл EPS с помощью `new PsDocument("input.eps")`, получите или создайте его XMP‑пакет, вставьте нужные свойства и затем сохраните документ обратно на диск — всё это менее чем в десяти строках кода Java. Такой подход позволяет встраивать поисковые, соответствующие стандартам метаданные без ручного редактирования исходного EPS.

## Что такое XMP metadata в EPS?
XMP metadata в EPS — это XML‑пакет, находящийся внутри файла EPS и хранящий информацию, такую как автор, дата создания и пользовательские теги. Встраивание этого пакета позволяет downstream‑инструментам читать и использовать данные без необходимости в отдельных side‑car файлах.

## Зачем добавлять XMP metadata в файлы EPS?
Встраивание XMP metadata делает ресурсы EPS мгновенно доступными для поиска, обеспечивает соответствие требованиям, сохраняя информацию о лицензировании внутри файла, позволяет автоматизированным конвейерам принимать решения на основе встроенных тегов и гарантирует, что метаданные перемещаются вместе с графикой на всех платформах. Aspose.Page может обрабатывать файлы до 500 МБ без загрузки всего документа в память, обеспечивая высокую производительность для крупномасштабных задач.

## Требования
- Базовые знания программирования на Java.  
- Установленная библиотека Aspose.Page for Java. Вы можете скачать её **[здесь](https://releases.aspose.com/page/java/)**.  
- Пример файла EPS, содержащего метаданные. Если у вас его нет, смело используйте предоставленный файл **`xmp3.eps`**.

## Импорт пакетов
Сначала импортируйте необходимые классы. Импорты остаются точно такими же, как в оригинальном примере:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Шаг 1: Загрузить документ EPS и получить XMP metadata
Класс `PsDocument` представляет файл EPS и предоставляет методы для доступа к его содержимому и метаданным.  
Объект `XmpMetadata` хранит XMP‑пакет, связанный с документом.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Шаг 2: Добавить свойство Date
Класс `Date` представляет конкретный момент времени с точностью до миллисекунд.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Шаг 3: Добавить свойство Integer
Класс `Integer` оборачивает примитивное значение `int` в объект.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Шаг 4: Добавить свойство Double
Класс `Double` оборачивает примитивное значение `double` в объект.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Шаг 5: Добавить свойство String
Класс `String` представляет последовательность символов.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Шаг 6: Сохранить обновлённый файл EPS
Метод `save` записывает изменённый документ обратно на диск, сохраняя структуру EPS.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Шаг 7: Очистить ресурсы
Всегда закрывайте потоки, чтобы избежать утечек дескрипторов файлов и гарантировать сброс всех буферов.

```java
// Close input EPS stream
psStream.close();
```

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| **Null XMP metadata** | Файл EPS не содержал XMP‑пакет, и библиотека не смогла вывести PS‑комментарии. | Убедитесь, что исходный EPS содержит хотя бы один PS‑комментарий (например, `%%Creator`). Библиотека автоматически сгенерирует минимальный XMP‑пакет. |
| **Несоответствие часового пояса** | Даты смещаются при открытии в другом приложении. | Установите `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` перед созданием объекта `Date`, как показано в Шаге 2. |
| **License exception** | Во время выполнения бросается `LicenseException`. | Примените действующую лицензию Aspose.Page перед использованием API, либо запустите в режиме пробной версии для оценки. |

## Часто задаваемые вопросы
**В: Можно ли использовать Aspose.Page for Java с другими языками программирования?**  
О: Aspose.Page в основном поддерживает Java, но эквивалентные библиотеки доступны для .NET, C++ и Python.

**В: Доступна ли бесплатная пробная версия Aspose.Page for Java?**  
О: Да, вы можете ознакомиться с возможностями Aspose.Page, получив бесплатную пробную версию **[здесь](https://releases.aspose.com/)**.

**В: Где можно найти подробную документацию по Aspose.Page for Java?**  
О: Документация доступна **[здесь](https://reference.aspose.com/page/java/)**.

**В: Как получить временную лицензию для Aspose.Page for Java?**  
О: Временную лицензию можно получить **[здесь](https://purchase.aspose.com/temporary-license/)**.

**В: Где можно приобрести Aspose.Page for Java?**  
О: Продукт можно купить **[здесь](https://purchase.aspose.com/buy)**.

---

**Последнее обновление:** 2026-05-20  
**Тестировано с:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как прочитать XMP Metadata с помощью Java — руководство Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp tutorial — Добавить пространство имён в XMP с помощью Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Добавить элементы массива в XMP Metadata с помощью Java](/page/java/xmp-metadata-manipulation/add-array-items/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}