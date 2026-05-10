---
date: 2026-03-05
description: Узнайте, как добавить элементы массива dc:title в XMP‑метаданные EPS‑файлов
  с помощью Aspose.Page для Java. Следуйте этому пошаговому руководству для быстрых
  результатов.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Как добавить элементы массива dc:title в XMP‑метаданные с помощью Java
url: /ru/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавление элементов массива в XMP‑метаданные с помощью Java

## Введение
В этом руководстве вы узнаете **как добавить dc:title** (и другие элементы массива) в XMP‑метаданные внутри EPS‑файла с помощью Aspose.Page for Java. Обновление XMP‑метаданных полезно, когда необходимо встроить поисковую информацию — такие как заголовки, авторы или ключевые слова — непосредственно в графические файлы. Мы пройдём каждый шаг, объясним, почему важна каждая строка, и покажем, как проверить внесённые изменения.

## Быстрые ответы
- **Что представляет собой «dc:title»?** Это свойство Dublin Core title, хранящееся как массив XMP.  
- **Зачем изменять XMP‑метаданные?** Это улучшает управление ресурсами, поиск и соответствие стандартам.  
- **Нужен ли уже существующий блок XMP?** Нет — Aspose.Page создаст его из PS‑комментариев, если он отсутствует.  
- **Какая версия библиотеки требуется?** Любая современная версия Aspose.Page for Java (тестировано на последней сборке 2026 года).  
- **Можно ли добавить другие свойства массива?** Да — используйте тот же метод `addArrayItem` для свойств, например `dc:creator`.

## Предварительные требования
Прежде чем приступить, убедитесь, что у вас есть:

- Библиотека Aspose.Page for Java установлена (добавьте JAR в classpath вашего проекта).  
- Базовый опыт разработки на Java (рекомендовано JDK 8+).  
- EPS‑файл, уже содержащий XMP‑метаданные или хотя бы PS‑комментарии (например, `%%Title`, `%%Creator`).  

## Импорт пакетов
Для начала импортируйте классы, необходимые для чтения, изменения и сохранения EPS‑файлов:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Шаг 1: Загрузка EPS‑документа и получение XMP‑метаданных
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Здесь мы открываем EPS‑файл и запрашиваем у Aspose.Page его блок XMP. Если в файле нет XMP, библиотека автоматически создаёт его, используя существующие PS‑комментарии, гарантируя наличие контейнера метаданных для работы.

## Шаг 2: Добавление нового элемента массива **dc:title**  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Эта строка демонстрирует **как добавить dc:title**. Замените `"NewTitle"` на фактический заголовок, который хотите встроить. Метод добавляет значение в существующий массив заголовков, сохраняя любые предыдущие заголовки.

## Шаг 3: Добавление нового элемента массива **dc:creator**  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Аналогично, вы можете обогатить свойство `dc:creator`. Можно хранить несколько авторов; каждый вызов добавляет новую запись.

## Шаг 4: Подготовка выходного потока  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Мы создаём поток для изменённого EPS‑файла. Использование другого имени файла (`xmp3_changed.eps`) сохраняет оригинал нетронутым.

## Шаг 5: Сохранение документа с обновлёнными XMP‑метаданными  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Вызов `save` записывает данные EPS вместе с обновлённым блоком XMP. Блок `finally` гарантирует освобождение файлового дескриптора даже при возникновении исключения.

## Почему это важно
Встраивание точных значений `dc:title` и `dc:creator` улучшает:

- **Поисковую доступность** в системах управления цифровыми активами (DAM).  
- **Соответствие** требованиям публикационных стандартов, требующих метаданные.  
- **Сотрудничество**, так как коллеги могут быстро определить содержимое файла без его открытия.

## Распространённые ошибки и советы
- **Ошибка:** Непреднамеренное перезаписывание существующих элементов массива.  
  **Совет:** Используйте `xmp.getArrayItems("dc:title")`, чтобы просмотреть текущие значения перед добавлением новых.  
- **Ошибка:** Забвение закрыть потоки, что приводит к блокировке файлов.  
  **Совет:** Всегда оборачивайте I/O в `try‑with‑resources` или используйте блок `finally`, как показано.  
- **Совет:** Вы можете цепочкой вызывать несколько `addArrayItem`, чтобы добавить несколько заголовков или авторов за один проход.

## Часто задаваемые вопросы

### Можно ли использовать Aspose.Page for Java с другими форматами документов?
Да, Aspose.Page поддерживает различные форматы, включая EPS, PDF и XPS.

### Есть ли бесплатная пробная версия Aspose.Page for Java?
Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

### Где найти документацию по Aspose.Page for Java?
Документация доступна [здесь](https://reference.aspose.com/page/java/).

### Как приобрести Aspose.Page for Java?
Купить продукт можно [здесь](https://purchase.aspose.com/buy).

### Доступны ли временные лицензии для Aspose.Page for Java?
Да, временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-03-05  
**Тестировано с:** Aspose.Page for Java (последний релиз 2026)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}