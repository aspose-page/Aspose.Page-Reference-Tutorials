---
title: Конвертировать XPS в PNG в Java
linktitle: Конвертировать XPS в PNG в Java
second_title: API Aspose.Page Java
description: Легко конвертируйте XPS в PNG в Java с помощью Aspose.Page. Оптимизируйте работу с документами с помощью этого надежного и удобного для разработчиков решения.
weight: 13
url: /ru/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конвертировать XPS в PNG в Java

## Введение
В динамичном мире разработки программного обеспечения часто возникает необходимость конвертировать документы XPS (спецификация бумаги XML) в изображения PNG (переносимая сетевая графика). Чтобы легко выполнить эту задачу на Java, Aspose.Page предоставляет мощное решение. В этом уроке мы рассмотрим процесс преобразования XPS в PNG с помощью Aspose.Page для Java.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас настроены следующие предварительные условия:
1. Java Development Kit (JDK): убедитесь, что в вашей системе установлен JDK.
2.  Aspose.Page для Java: Загрузите и установите библиотеку Aspose.Page. Вы можете найти ссылку для скачивания[здесь](https://releases.aspose.com/page/java/).
3. Интегрированная среда разработки (IDE). Выберите Java-совместимую среду разработки, например IntelliJ IDEA или Eclipse.
## Импортировать пакеты
В свой проект Java импортируйте необходимые пакеты для использования функций Aspose.Page. Добавьте следующие операторы импорта в начало вашего Java-файла:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Шаг 1. Установите каталог документов
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
```
## Шаг 2. Загрузите документ XPS
```java
// Загрузить документ XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Шаг 3: Инициализируйте параметры
```java
// Инициализируйте объект параметров с необходимыми параметрами.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Шаг 4. Создайте устройство рендеринга
```java
// Создать устройство рендеринга для формата PDF
ImageDevice device = new ImageDevice();
```
## Шаг 5: Сохраните и повторите
```java
// Сохраните документ XPS в PNG, используя параметры и устройство.
document.save(device, options);
//Перебирать разделы документов (фиксированные документы в терминах XPS).
for (int i = 0; i < device.getResult().length; i++) {
    // Перебирать страницы разделов
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Инициализировать поток вывода изображения
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Написать изображение
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Закрыть поток
        imageStream.close();
    }
}
```
Следуя этим шагам, вы сможете легко конвертировать документы XPS в изображения PNG с помощью Aspose.Page для Java.
## Заключение
В заключение, Aspose.Page для Java упрощает процесс преобразования XPS в PNG, предоставляя разработчикам надежный и эффективный инструмент. Включите эту библиотеку в свои проекты Java, чтобы упростить задачи по манипулированию документами.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java в коммерческих проектах?
 Да, Aspose.Page — коммерческий продукт. Вы можете найти информацию о лицензировании[здесь](https://purchase.aspose.com/buy).
### Доступна ли бесплатная пробная версия?
 Да, вы можете изучить бесплатную пробную версию[здесь](https://releases.aspose.com/).
### Где я могу найти документацию по Aspose.Page для Java?
 Полная документация доступна[здесь](https://reference.aspose.com/page/java/).
### Как получить временную лицензию для целей тестирования?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Существуют ли форумы сообщества для обсуждений Aspose.Page?
 Да, посетите форумы сообщества[здесь](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
