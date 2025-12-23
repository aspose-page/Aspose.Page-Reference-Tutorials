---
date: 2025-12-23
description: Легко **конвертировать XPS в PNG** в Java с помощью Aspose.Page. Это
  руководство показывает, как преобразовать XPS в файлы изображений с надёжным, удобным
  для разработчиков решением.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Конвертировать XPS в PNG в Java
url: /ru/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конвертация XPS в PNG на Java

## Введение
В динамичном мире разработки программного обеспечения часто возникает необходимость **конвертировать XPS в PNG** (XML Paper Specification в Portable Network Graphics). Чтобы выполнить эту задачу без проблем в Java, Aspose.Page предоставляет мощное решение. В этом руководстве мы пройдем процесс конвертации XPS в PNG с использованием Aspose.Page для Java.

## Краткие ответы
- **Какая библиотека обрабатывает конвертацию?** Aspose.Page for Java  
- **Какие форматы задействованы?** XPS (исходный) → PNG (выходной)  
- **Нужна ли лицензия для продакшн?** Да, требуется коммерческая лицензия  
- **Можно ли задать разрешение изображения?** Да, используя `PngSaveOptions.setResolution()`  
- **Можно ли выбрать конкретные страницы?** Абсолютно — укажите номера страниц в объекте параметров  

## Зачем конвертировать XPS в PNG?
Отображение XPS в файлы изображений полезно, когда необходимо показывать документы в вебе, встраивать их в отчёты или генерировать миниатюры для предварительного просмотра. PNG предлагает без потерь сжатие и широкую поддержку браузерами, что делает его идеальным выбором для высококачественного визуального представления содержимого XPS.

## Требования
Прежде чем приступить к руководству, убедитесь, что у вас настроены следующие требования:
1. Java Development Kit (JDK): Убедитесь, что JDK установлен в вашей системе.  
2. Aspose.Page for Java: Скачайте и установите библиотеку Aspose.Page. Ссылка для загрузки доступна [здесь](https://releases.aspose.com/page/java/).  
3. Интегрированная среда разработки (IDE): Выберите совместимую с Java IDE, например IntelliJ IDEA или Eclipse.  

## Как конвертировать XPS в PNG на Java
Ниже представлено пошаговое руководство, объясняющее **как конвертировать XPS** документы в PNG‑изображения, включая фрагменты кода, которые можно скопировать непосредственно в ваш проект.

### Импорт пакетов
В вашем Java‑проекте импортируйте необходимые пакеты для использования возможностей Aspose.Page. Добавьте следующие инструкции импорта в начало вашего Java‑файла:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Шаг 1: Установить каталог документа
Определите папку, содержащую ваш исходный XPS‑файл, и место, куда будут сохраняться PNG‑файлы.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Шаг 2: Загрузить XPS‑документ
Создайте экземпляр `XpsDocument`, который загружает исходный XPS‑файл.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Шаг 3: Инициализировать параметры
Настройте параметры вывода PNG. Здесь вы можете задать сглаживание, разрешение и указать, какие страницы рендерить.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Шаг 4: Создать устройство рендеринга
Создайте `ImageDevice`, который будет хранить данные отрендеренного изображения.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Шаг 5: Сохранить и перебрать
Отрендерите XPS‑документ, затем запишите каждый сгенерированный массив байтов PNG в файл на диске.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Следуя этим шагам, вы сможете без усилий **рендерить XPS в изображения** в формате PNG с помощью Aspose.Page для Java.

## Заключение
В заключение, Aspose.Page для Java упрощает процесс конвертации XPS в PNG, предоставляя разработчикам надёжный и эффективный инструмент. Интегрируйте эту библиотеку в ваши Java‑проекты, чтобы упростить задачи манипуляции документами.

## Часто задаваемые вопросы

### Могу ли я использовать Aspose.Page для Java в коммерческих проектах?
Да, Aspose.Page — коммерческий продукт. Информацию о лицензировании можно найти [здесь](https://purchase.aspose.com/buy).

### Доступна ли бесплатная пробная версия?
Да, вы можете ознакомиться с бесплатной пробной версией [здесь](https://releases.aspose.com/).

### Где я могу найти документацию по Aspose.Page для Java?
Полная документация доступна [здесь](https://reference.aspose.com/page/java/).

### Как получить временную лицензию для тестирования?
Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### Есть ли форумы сообщества для обсуждения Aspose.Page?
Да, посетите форумы сообщества [здесь](https://forum.aspose.com/c/page/39).

## Дополнительные часто задаваемые вопросы

**Q: Можно ли конвертировать только выбранные страницы XPS‑файла?**  
A: Абсолютно. Используйте метод `setPageNumbers` в `PngSaveOptions`, чтобы указать страницы, которые вы хотите отрендерить.

**Q: Какое разрешение изображения рекомендуется для высококачественных PNG?**  
A: Разрешение 300 dpi является хорошим компромиссом между качеством и размером файла, но вы можете изменить его через `options.setResolution()`.

**Q: Поддерживает ли API многопоточную конвертацию больших документов?**  
A: Да, вы можете вызывать логику конвертации в параллельных потоках, каждый из которых обрабатывает отдельную страницу или часть документа.

**Q: Как управлять использованием памяти при конвертации очень больших XPS‑файлов?**  
A: Обрабатывайте страницы последовательно и освобождайте `FileOutputStream` после каждой записи, как показано в примере кода.

**Q: Есть ли способ добавить пользовательские метаданные в сгенерированные PNG‑файлы?**  
A: Хотя `PngSaveOptions` не предоставляет прямого доступа к полям метаданных, вы можете после обработки PNG с помощью стандартных библиотек изображений для встраивания метаданных.

---

**Последнее обновление:** 2025-12-23  
**Тестировано с:** Aspose.Page for Java 24.12 (latest)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}