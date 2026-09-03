---
date: 2026-05-25
description: Узнайте, как изменить xmp в EPS‑документах с помощью Java и Aspose.Page.
  Обновляйте метаданные быстро и надёжно.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Изменение значений в XMP с использованием Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: как изменить xmp с помощью Aspose.Page – изменение значений в XMP с использованием
  Java
url: /ru/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Изменение значений XMP с помощью Java

## Введение
Если вы ищете **как изменить xmp** внутри EPS‑файла с помощью Java, вы попали в нужное место. Этот учебник проведёт вас через каждый шаг — чтение существующего блока XMP, обновление полей, таких как создатель, название и дата изменения, и, наконец, сохранение изменений обратно в документ EPS. К концу вы получите переиспользуемый фрагмент кода, который впишется в любой автоматизированный рабочий процесс, гарантируя, что ваши файлы содержат корректные метаданные для брендинга, соответствия требованиям или индексации поисковыми системами.

## Быстрые ответы
- **Что делает “aspose.page modify xmp”?** Позволяет читать и записывать XMP‑метаданные в EPS‑файлах через Aspose.Page Java API.  
- **Какая версия библиотеки требуется?** Любая современная версия Aspose.Page for Java (API стабилен между версиями).  
- **Нужна ли лицензия для запуска примера?** Бесплатная пробная версия подходит для оценки; коммерческая лицензия требуется для продакшна.  
- **Можно ли изменить несколько полей XMP одновременно?** Да — вызовите `put` для каждого поля перед сохранением документа.  
- **Нужна ли обработка часовых поясов?** Установка часового пояса по умолчанию (например, UTC) обеспечивает согласованные значения дат.

## Что такое XMP и почему его изменять?
XMP (Extensible Metadata Platform) — это стандартизированный, основанный на XML формат для встраивания богатых метаданных непосредственно в файлы, такие как EPS, PDF и изображения. Обновление XMP позволяет контролировать, как документы индексируются, отображаются и ищутся — критически важно для согласованности бренда, соблюдения нормативных требований и автоматических конвейеров контента.

## Почему использовать Aspose.Page для Java?
Aspose.Page предоставляет **полнофункциональный, чисто‑Java API**, который устраняет необходимость во внешних инструментах или нативных библиотеках. Он поддерживает **более 50 форматов ввода и вывода** и может обрабатывать EPS‑файлы размером до **500 МБ**, не загружая весь документ в память, обеспечивая быструю, малопамятную работу с метаданными на любой ОС, где работает Java.

## Предварительные требования
Перед тем как приступить к учебнику, убедитесь, что у вас есть следующее:
1. **Среда разработки Java** – JDK (8 или новее) и IDE или система сборки по вашему выбору.  
2. **Библиотека Aspose.Page for Java** – Скачайте и установите библиотеку Aspose.Page for Java. Необходимый пакет можно найти [здесь](https://releases.aspose.com/page/java/).

## Импорт пакетов
Начните с импорта необходимых пакетов в ваш Java‑проект. Эти пакеты важны для взаимодействия и манипуляции EPS‑документами.

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

## Как изменить XMP в EPS с помощью Java?
`Document` — класс Aspose.Page, представляющий EPS‑файл и предоставляющий доступ к его содержимому и метаданным. `XmpMetadata` представляет блок XMP, прикреплённый к документу, и позволяет читать и записывать поля метаданных. `put` добавляет или обновляет запись метаданных в объекте XmpMetadata. `save` записывает изменённый документ, включая любые обновлённые XMP‑метаданные, в файл.

Загрузите EPS‑файл с помощью `new Document("input.eps")`, получите его объект `XmpMetadata`, обновите нужные ключи с помощью `put` и, наконец, вызовите `save`, чтобы записать изменения в новый файл. Этот лаконичный процесс автоматически обрабатывает отсутствие блока XMP, создаёт его из комментариев PostScript при необходимости и гарантирует согласованные даты с учётом часового пояса.

## Шаг 1: Получить XMP‑метаданные
Класс `XmpMetadata` представляет блок XMP, прикреплённый к EPS‑документу. При вызове `document.getXmpMetadata()` API либо возвращает существующий блок, либо создаёт новый из PS‑комментариев, таких как `%%Creator`, `%%CreateDate` и `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Шаг 2: Изменить значение "ModifyDate"
Обновите запись `"ModifyDate"`, чтобы отразить новую временную метку изменения. Используйте `java.util.Date` в сочетании с `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, чтобы гарантировать, что сохранённое значение не зависит от часового пояса.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Шаг 3: Изменить значение "Creator"
Ключ `"Creator"` хранит имя приложения или человека, создавшего EPS‑файл. Вызовите `xmp.put("dc:creator", "Your Company Name")`, чтобы заменить существующее значение на пользовательский идентификатор.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Шаг 4: Изменить значение "Title"
Поле `"Title"` отображается во многих системах управления активами. Установка его через `xmp.put("dc:title", "New Document Title")` гарантирует корректное отображение документа в каталогах и результатах поиска.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Шаг 5: Сохранить документ с изменёнными XMP‑метаданными
После всех изменений вызовите `document.save("output.eps")`. Библиотека записывает обновлённый блок XMP обратно в поток EPS, сохраняя оригинальное графическое содержание без изменений.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Распространённые проблемы и решения
- **Отсутствует блок XMP** – API автоматически создаёт его из PS‑комментариев, но при необходимости можно вручную создать `XmpMetadata`.  
- **Несоответствия часовых поясов** – Всегда вызывайте `TimeZone.setDefault` перед созданием объекта `Date`, чтобы избежать неожиданных смещений.  
- **Ошибки доступа к файлам** – Убедитесь, что пути ввода и вывода правильные и что приложение имеет права чтения/записи.

## Часто задаваемые вопросы

**Q: Как учитывать часовые пояса при изменении значений XMP?**  
A: Используйте `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, чтобы обеспечить согласованность настроек часового пояса.

**Q: Можно ли изменить несколько значений XMP за одну операцию?**  
A: Да, используя метод `put` для каждого нужного значения, можно одновременно изменить несколько XMP‑значений.

**Q: Где найти дополнительную документацию по Aspose.Page для Java?**  
A: Ознакомьтесь с полной документацией [здесь](https://reference.aspose.com/page/java/).

**Q: Есть ли бесплатная пробная версия Aspose.Page для Java?**  
A: Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

**Q: Как получить временную лицензию для Aspose.Page для Java?**  
A: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Влияет ли изменение XMP на визуальное содержание EPS?**  
A: Нет. Изменения XMP касаются только метаданных и не влияют на графические элементы EPS‑файла.

**Q: Можно ли программно считать обновлённые значения для проверки изменения?**  
A: Конечно — просто вызовите `xmp.get("dc:creator")` (или соответствующий ключ) после сохранения и перед закрытием документа.

## Заключение
Поздравляем! Вы освоили **как изменить xmp** значения в EPS‑документах с помощью Aspose.Page для Java. Встраивая точные метаданные создателя, названия и даты изменения, вы делаете свои ресурсы доступными для поиска, соответствующими требованиям и согласованными с вашими брендовыми стандартами. Смело интегрируйте этот шаблон в конвейеры пакетной обработки, шаги CI/CD или любой автоматизированный процесс генерации документов.

---

**Последнее обновление:** 2026-05-25  
**Тестировано с:** Aspose.Page for Java (latest release)  
**Автор:** Aspose

## Связанные руководства

- [Aspose Page Java Tutorial – Добавить XMP‑метаданные в EPS‑файлы](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Как читать XMP‑метаданные с помощью Java – Руководство Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Изменить элементы массива в XMP с помощью Java](/page/java/xmp-metadata-manipulation/change-array-items/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}