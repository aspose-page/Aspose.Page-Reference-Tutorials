---
date: 2025-12-03
description: Узнайте, как сохранить EPS в PNG с помощью Aspose.Page для Java, настроив
  лицензирование по метрам. Пошаговое руководство с полным примером кода.
language: ru
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Сохранить EPS как PNG с Aspose.Page Java (метрическая лицензия)
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохранить EPS как PNG с Aspose.Page Java (метрическая лицензия)

## Введение
Если вам нужно **сохранить EPS как PNG** в Java‑приложении и вы хотите простой способ управления лицензированием, вы попали по адресу. В этом руководстве мы покажем, как настроить метрическую лицензию для Aspose.Page, загрузить файл PostScript (EPS) и преобразовать его в изображение PNG — всё с понятными пошаговыми инструкциями, которые вы можете выполнить сразу.

## Быстрые ответы
- **Что означает «save EPS as PNG»?** Это преобразует векторный файл EPS в растровое изображение PNG.  
- **Зачем использовать метрическую лицензию?** Она позволяет платить только за обработанные страницы, что идеально подходит для переменных нагрузок.  
- **Нужен ли интернет?** Нет, метрические ключи проверяются локально.  
- **Какая версия Java требуется?** Java 8 или выше.  
- **Сколько времени занимает настройка?** Около 10 минут для базовой реализации.

## Что такое «save EPS as PNG»?
Сохранение EPS как PNG преобразует масштабируемый документ Encapsulated PostScript в широко поддерживаемый растровый формат. PNG сохраняет прозрачность и обеспечивает без потерь сжатие, что делает его идеальным для веб‑графики, миниатюр и предварительного просмотра печати.

## Почему использовать Aspose.Page для этой задачи?
- **Чистый Java API** — без нативных зависимостей.  
- **Высокая точность** — векторная графика отображается точно.  
- **Метрическое лицензирование** — вы платите только за то, что конвертируете.  
- **Поддержка нескольких форматов вывода** — PNG, JPEG, TIFF и др.

## Предварительные требования
Перед началом убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Библиотека Aspose.Page установлена — скачайте её [здесь](https://releases.aspose.com/page/java/).  
- Метрические публичный и приватный ключи, которые можно получить через ваш аккаунт Aspose.

## Импорт пакетов
Сначала импортируйте необходимые классы. Сохраните блок импорта точно как показано, чтобы код компилировался без изменений.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Шаг 1: Инициализация документа и формата изображения
Здесь мы задаём метрические ключи и определяем формат вывода (PNG). Это основа операции **save EPS as PNG**.

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

## Шаг 2: Инициализация входного потока PostScript
Откройте файл EPS, который хотите конвертировать. Поток передаёт документ в Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Шаг 3: Проверка лицензии документа
Всегда проверяйте, что метрическая лицензия применена корректно перед обработкой.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Шаг 4: Инициализация параметров и устройства изображения
Создайте объект параметров, который управляет настройками конвертации, и устройство, которое получит отрисованное изображение.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Шаг 5: Сохранить файл EPS как изображение
Это основной вызов **save EPS as PNG**. Документ отрисовывается в устройство изображения с использованием настроенных параметров.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Шаг 6: Получить и сохранить байты изображения
Извлеките байты PNG из устройства и запишите их в файл на диске.

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
|-------|----------------|-----|
| **License not recognized** | Ключи некорректны или находятся в неправильном порядке. | Дважды проверьте строки публичного/приватного ключа и убедитесь, что `setMeteredKey` вызывается до любой обработки документа. |
| **Output file is empty** | `device.getImagesBytes()` вернул `null`. | Убедитесь, что файл EPS действителен и что `ImageSaveOptions` не настроены на холст нулевого размера. |
| **OutOfMemoryError on large EPS** | Отрисовка больших векторных файлов потребляет много памяти. | Обрабатывайте страницы по одной или увеличьте размер кучи JVM (`-Xmx2g`). |

## Часто задаваемые вопросы

**В: Как получить публичный и приватный метрические ключи?**  
О: Вы можете получить эти ключи через ваш аккаунт Aspose.

**В: Является ли библиотека Aspose.Page бесплатной?**  
О: Aspose.Page предлагает как бесплатную пробную, так и платную версии. Посетите [здесь](https://releases.aspose.com/) для бесплатного пробного периода.

**В: Можно ли использовать Aspose.Page в коммерческих проектах?**  
О: Да, Aspose.Page предлагает коммерческие лицензии. Вы можете приобрести их [здесь](https://purchase.aspose.com/buy).

**В: Где можно найти дополнительную документацию?**  
О: Обратитесь к документации [здесь](https://reference.aspose.com/page/java/).

**В: Как получить временные лицензии?**  
О: Временные лицензии можно получить [здесь](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2025-12-03  
**Тестировано с:** Aspose.Page 24.12 for Java  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
