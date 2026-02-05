---
date: 2026-02-05
description: Узнайте, как сохранить EPS в PNG с помощью Aspose.Page для Java, настроив
  лицензирование по счётчику. Пошаговое руководство с полным примером кода.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Сохранить EPS в PNG с помощью Aspose.Page Java (лицензия с измерением)
url: /ru/java/license-management/set-metered-license/
weight: 10
---

)" maybe.

But keep as heading.

Proceed.

Will produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохранить EPS как PNG с Aspose.Page Java (лицензия с измерением)

## Введение
Если вам нужно **сохранить EPS как PNG** в Java‑приложении и вы хотите простой способ управления лицензированием, вы попали по адресу. В этом руководстве показано, как настроить лицензию с измерением для Aspose.Page, загрузить файл PostScript (EPS) и преобразовать его в изображение PNG — все шаги изложены ясно и по‑пунктно, чтобы вы могли сразу приступить к работе. К концу вы также поймёте, как **рендерить EPS в PNG** эффективно и как написать код **write PNG file Java**, который будет работать в продакшн‑среде.

## Быстрые ответы
- **Что означает «save EPS as PNG»?** Это преобразование векторного файла EPS в растровое изображение PNG.  
- **Зачем использовать лицензию с измерением?** Вы платите только за обработанные страницы, что идеально подходит для переменных нагрузок.  
- **Нужен ли интернет?** Нет, ключи с измерением проверяются локально.  
- **Какая версия Java требуется?** Java 8 или выше.  
- **Сколько времени занимает настройка?** Около 10 минут для базовой реализации.  

## Что такое «save EPS as PNG»?
Сохранение EPS как PNG преобразует масштабируемый документ Encapsulated PostScript в широко поддерживаемый растровый формат. PNG сохраняет прозрачность и обеспечивает сжатие без потерь, что делает его идеальным для веб‑графики, миниатюр и предварительного просмотра печати.

## Почему рендерить EPS в PNG с Aspose.Page?
- **Pure Java API** — без нативных зависимостей, поэтому работает в любой среде, где поддерживается JVM.  
- **Высокоточное рендеринг** — векторная графика растеризуется точно, сохраняется качество линий.  
- **Лицензирование с измерением** — вы платите только за то, что конвертируете, что делает расходы предсказуемыми.  
- **Множество вариантов вывода** — помимо PNG можно генерировать JPEG, TIFF и другие форматы, что даёт гибкость для разных проектов.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Библиотека Aspose.Page установлена — скачайте её [здесь](https://releases.aspose.com/page/java/).  
- Публичный и приватный ключи с измерением, которые можно получить через ваш аккаунт Aspose.

## Импорт пакетов
Сначала импортируем необходимые классы. Сохраните блок импорта точно таким, как показано, чтобы код компилировался без изменений.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Как сохранить EPS как PNG с помощью Aspose.Page Java
Ниже пошаговое руководство, объединяющее лицензирование, загрузку, рендеринг и запись окончательного PNG‑файла.

### Шаг 1: Инициализация документа и формата изображения
Здесь мы задаём ключи с измерением и определяем выходной формат (PNG). Это основа операции **save EPS as PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Шаг 2: Инициализация входного потока PostScript
Откройте EPS‑файл, который хотите конвертировать. Поток передаёт документ в Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Шаг 3: Проверка лицензии документа
Всегда проверяйте, что лицензия с измерением применена корректно перед обработкой.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Шаг 4: Инициализация параметров и графического устройства
Создайте объект параметров, который управляет настройками конвертации, и устройство, которое получит отрендеренное изображение.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Шаг 5: Сохранить EPS‑файл как изображение
Это основной вызов **save EPS as PNG**. Документ рендерится в графическое устройство с использованием настроенных параметров.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Шаг 6: Получить и сохранить байты изображения
Извлеките байты PNG из устройства и запишите их в файл на диске. Этот шаг демонстрирует, как безопасно выполнить **write PNG file Java**.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Лицензия не распознана** | Неправильные ключи или неверный порядок их установки. | Проверьте строки публичного/приватного ключа и убедитесь, что `setMeteredKey` вызывается до любой обработки документа. |
| **Выходной файл пустой** | `device.getImagesBytes()` вернул `null`. | Убедитесь, что EPS‑файл корректен и параметры `ImageSaveOptions` не задают нулевой размер холста. |
| **OutOfMemoryError при большом EPS** | Рендеринг крупных векторных файлов требует много памяти. | Обрабатывайте страницы по одной или увеличьте размер кучи JVM (`-Xmx2g`). |

## Часто задаваемые вопросы

**В: Как получить публичный и приватный ключи с измерением?**  
О: Их можно получить через ваш аккаунт Aspose.

**В: Бесплатна ли библиотека Aspose.Page?**  
О: Aspose.Page предлагает как бесплатную пробную, так и платные версии. Скачайте пробную [здесь](https://releases.aspose.com/).

**В: Можно ли использовать Aspose.Page в коммерческих проектах?**  
О: Да, доступны коммерческие лицензии. Приобрести их можно [здесь](https://purchase.aspose.com/buy).

**В: Где найти дополнительную документацию?**  
О: Обратитесь к документации [здесь](https://reference.aspose.com/page/java/).

**В: Как получить временные лицензии?**  
О: Временные лицензии доступны [здесь](https://purchase.aspose.com/temporary-license/).

**В: Что делать, если нужно конвертировать многостраничный EPS?**  
О: Пройдитесь по каждой странице с помощью `device.getImagesBytes()` и запишите каждый массив байт в отдельный PNG‑файл.

**В: Можно ли изменить качество PNG или глубину цвета?**  
О: Да, настройте `ImageSaveOptions` (например, `options.setCompressionLevel(...)`) перед вызовом `document.save(...)`.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Page 24.12 for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}