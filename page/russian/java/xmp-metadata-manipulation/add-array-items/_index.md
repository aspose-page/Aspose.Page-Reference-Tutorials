---
date: 2025-12-18
description: Узнайте, как добавить метаданные, вставляя элементы массива в XMP‑метаданные
  EPS‑файлов с помощью Aspose.Page для Java. Следуйте нашему пошаговому руководству.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Как добавить метаданные – добавить элементы массива в XMP (Java)
url: /ru/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавление элементов массива в XMP Metadata с помощью Java

## Как добавить метаданные
Добро пожаловать в наше пошаговое руководство по **добавлению метаданных** в EPS‑файлы с помощью Aspose.Page for Java. В этом учебнике мы покажем, как добавить элементы массива в XMP‑metadata — это распространённая задача, когда нужно обогатить информацию о документе, такой как заголовки или создатели. К концу вы поймёте, почему XMP ценен, как манипулировать им программно и как сохранить обновлённый EPS‑файл.

## Быстрые ответы
- **Какая библиотека используется?** Aspose.Page for Java  
- **Какой формат файла используется?** EPS (Encapsulated PostScript)  
- **Можно ли добавить несколько заголовков?** Да, используйте `xmp.addArrayItem("dc:title", ...)` многократно  
- **Нужна ли лицензия для продакшн?** Да, требуется действующая лицензия Aspose.Page  
- **Совместим ли код с Java 8+?** Абсолютно, он работает со всеми современными версиями Java  

## Предварительные требования
Прежде чем погрузиться в руководство, убедитесь, что у вас есть следующие требования:
- Установлена библиотека Aspose.Page for Java.  
- Базовое понимание программирования на Java.  
- Действительный EPS‑файл с существующими XMP‑метаданными или комментариями PS‑метаданных.

## Импорт пакетов
Чтобы начать, необходимо импортировать требуемые пакеты для работы с Aspose.Page. Добавьте следующие строки в начало вашего Java‑файла:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Шаг 1: Получить XMP‑метаданные
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
На этом шаге мы получаем существующие XMP‑метаданные из EPS‑файла. Если EPS‑файл ещё не содержит XMP‑метаданных, Aspose.Page создаёт новые и заполняет их значениями из комментариев PS‑метаданных.

## Шаг 2: Добавить элемент массива "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Теперь мы добавляем новый элемент массива в свойство **dc:title** XMP‑метаданных. Замените `"NewTitle"` на нужный заголовок.

## Шаг 3: Добавить элемент массива "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Аналогично, мы добавляем новый элемент массива в свойство **dc:creator** XMP‑метаданных. Замените `"NewCreator"` на нужную информацию о создателе.

## Шаг 4: Инициализировать поток вывода EPS‑файла
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Подготовьте поток вывода EPS‑файла, в который будет сохранён изменённый документ с обновлёнными XMP‑метаданными.

## Шаг 5: Сохранить документ с изменёнными XMP‑метаданными
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Сохраните документ с обновлёнными XMP‑метаданными в выходной EPS‑файл.

## Заключение
Поздравляем! Вы успешно изучили **как добавить метаданные** путём вставки элементов массива в XMP‑метаданные с помощью Aspose.Page for Java. Эта мощная библиотека упрощает процесс работы с EPS‑файлами и предоставляет обширный функционал для обработки документов.

## Часто задаваемые вопросы

### Можно ли использовать Aspose.Page for Java с другими форматами документов?
Да, Aspose.Page поддерживает различные форматы документов, включая EPS, PDF и XPS.

### Есть ли бесплатная пробная версия Aspose.Page for Java?
Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

### Где можно найти документацию по Aspose.Page for Java?
Документация доступна [здесь](https://reference.aspose.com/page/java/).

### Как приобрести Aspose.Page for Java?
Продукт можно купить [здесь](https://purchase.aspose.com/buy).

### Доступны ли временные лицензии для Aspose.Page for Java?
Да, временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

## Additional Frequently Asked Questions

**Q: Можно ли добавить более одного элемента массива к одному свойству?**  
**A:** Абсолютно. Вызовите `xmp.addArrayItem` несколько раз для того же свойства, чтобы сформировать список значений.

**Q: Работает ли этот подход с существующими схемами XMP, отличными от Dublin Core?**  
**A:** Да, вы можете добавлять элементы массива в любое свойство XMP, при условии, что пространство имён указано корректно.

**Q: Как проверить, что метаданные были добавлены корректно?**  
**A:** Откройте полученный EPS‑файл в просмотрщике, поддерживающем XMP (например, Adobe Bridge), либо извлеките метаданные программно с помощью методов `XmpMetadata`.

---

**Последнее обновление:** 2025-12-18  
**Тестировано с:** Aspose.Page for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}