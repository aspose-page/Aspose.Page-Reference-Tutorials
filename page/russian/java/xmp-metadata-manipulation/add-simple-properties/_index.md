---
date: 2025-12-20
description: Узнайте, как создавать XMP‑метаданные EPS в файлах EPS с помощью Aspose.Page
  для Java. Пошаговое руководство по программному добавлению простых свойств XMP.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Как создать XMP‑метаданные EPS с помощью Java
url: /ru/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавление простых свойств в XMP с помощью Java

## Введение
В современных рабочих процессах с документами возможность **программно создавать XMP‑metadata EPS** файлы дает полный контроль над тем, как ваши графические объекты описываются, ищутся и архивируются. С помощью Aspose.Page for Java вы можете читать, изменять и записывать XMP‑пакеты внутри EPS‑документов, не выходя из экосистемы Java. В этом руководстве мы пошагово покажем, как добавить простые XMP‑свойства в EPS‑файл, чтобы быстро и надёжно обогатить графику пользовательскими метаданными.

## Быстрые ответы
- **Что значит «create xmp metadata eps»?** Добавление XMP‑пакета (XML‑метаданных) в EPS‑файл.  
- **Какая библиотека требуется?** Aspose.Page for Java (скачивается с сайта Aspose).  
- **Нужна ли лицензия для тестирования?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Сколько строк кода?** Менее 30 строк Java плюс несколько операторов import.  
- **Можно ли добавить другие типы данных?** Да — поддерживаются даты, целые числа, числа с плавающей точкой, строки и даже массивы.

## Что такое create xmp metadata eps?
XMP (Extensible Metadata Platform) — стандарт для внедрения богатых метаданных внутрь файлов. Когда вы **создаёте XMP‑metadata EPS**, вы встраиваете XML‑пакет в документ EPS (Encapsulated PostScript), позволяя downstream‑приложениям считывать автора, дату создания, пользовательские теги и многое другое.

## Почему стоит добавлять XMP‑metadata в EPS‑файлы?
- **Поисковость:** Позволяет системам DAM автоматически индексировать файлы.  
- **Соответствие требованиям:** Хранит юридическую или лицензионную информацию непосредственно в файле.  
- **Автоматизация:** Позволяет downstream‑конвейерам принимать решения на основе встроенных данных.  
- **Переносимость:** Метаданные перемещаются вместе с EPS, обеспечивая согласованность на разных платформах.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Установленная библиотека Aspose.Page for Java. Скачать её можно **[здесь](https://releases.aspose.com/page/java/)**.  
- Пример EPS‑файла, содержащего метаданные. Если у вас его нет, используйте предоставленный файл **`xmp3.eps`**.

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

## Шаг 1: Загрузка EPS‑документа и получение XMP‑metadata
Открываем EPS‑файл, создаём экземпляр `PsDocument` и получаем (или создаём) XMP‑пакет.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Шаг 2: Добавление свойства Date
Добавление даты сводится к созданию объекта `Date` и помещению его в XMP‑карту.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Шаг 3: Добавление свойства Integer
Можно хранить числовые идентификаторы или номера версий, используя целочисленное значение.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Шаг 4: Добавление свойства Double
Числа с плавающей точкой полезны для измерений или оценок.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Шаг 5: Добавление свойства String
Пользовательские текстовые теги (например, коды проектов) хранятся как строки.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Шаг 6: Сохранение обновлённого EPS‑файла
После добавления всех свойств записываем документ обратно на диск.

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

## Шаг 7: Очистка ресурсов
Всегда закрывайте входной поток, чтобы избежать утечек дескрипторов файлов.

```java
// Close input EPS stream
psStream.close();
```

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| **Null XMP metadata** | В EPS‑файле отсутствовал XMP‑пакет, и библиотека не смогла вывести PS‑комментарии. | Убедитесь, что исходный EPS содержит хотя бы один PS‑комментарий (например, `%%Creator`). Библиотека автоматически сгенерирует минимальный XMP‑пакет. |
| **Несоответствие часовых поясов** | Даты смещаются при открытии в другом приложении. | Установите `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` перед созданием объекта `Date`, как показано в Шаге 2. |
| **Исключение лицензии** | Во время выполнения выбрасывается `LicenseException`. | Примените действующую лицензию Aspose.Page перед использованием API, либо запустите в режиме пробной версии для оценки. |

## Заключение
Следуя этим шагам, вы теперь знаете, как **создавать XMP‑metadata EPS** файлы с помощью Aspose.Page for Java. Добавление простых свойств, таких как даты, целые числа, числа с плавающей точкой и строки, происходит без труда, а полученные EPS‑файлы содержат богатые, поисковые метаданные, полезные для любого downstream‑процесса.

## Часто задаваемые вопросы
### Можно ли использовать Aspose.Page for Java с другими языками программирования?
Aspose.Page в основном поддерживает Java, но существуют версии для других языков, например .NET.

### Доступна ли бесплатная пробная версия Aspose.Page for Java?
Да, вы можете изучить возможности Aspose.Page, получив бесплатную пробную версию [здесь](https://releases.aspose.com/).

### Где найти подробную документацию по Aspose.Page for Java?
Документация доступна [здесь](https://reference.aspose.com/page/java/).

### Как получить временную лицензию для Aspose.Page for Java?
Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### Где можно приобрести Aspose.Page for Java?
Продукт можно приобрести [здесь](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2025-12-20  
**Тестировано с:** Aspose.Page for Java 24.11 (на момент написания)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}