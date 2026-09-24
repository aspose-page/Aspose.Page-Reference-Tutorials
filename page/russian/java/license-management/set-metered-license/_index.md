---
date: 2026-09-24
description: Узнайте, как использовать Aspose.Page для конвертации EPS в PNG в Java,
  настроить metered license и эффективно писать код Java для создания PNG‑файла.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Установить metered license в Java
og_description: Aspose.Page конвертировать EPS в PNG в Java с metered license. Это
  руководство пошагово показывает, как настроить лицензирование, отрисовать EPS и
  написать код Java для создания PNG‑файла.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page конвертировать EPS в PNG в Java (metered license)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page конвертировать EPS в PNG в Java (metered license)
url: /ru/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page: конвертация EPS в PNG на Java (метрическая лицензия)

## Введение
Если вам нужно **сохранить EPS как PNG** в Java‑приложении, при этом упростив работу с лицензией, вы попали по адресу. Это руководство покажет, как настроить **метрическую лицензию** для Aspose.Page, загрузить файл EPS (Encapsulated PostScript) и преобразовать его в изображение PNG. В конце вы поймёте, как **эффективно рендерить EPS в PNG** и как написать код **write PNG file Java**, который надёжно работает в продакшене.

## Быстрые ответы
- **Что означает «сохранить EPS как PNG»?** Это преобразует векторный файл EPS в растровое изображение PNG, сохраняет прозрачность и использует без потерь сжатие.  
- **Зачем использовать метрическую лицензию?** Вы платите только за обработанные страницы, что идеально подходит для переменных нагрузок.  
- **Нужен ли интернет?** Нет, ключи метрической лицензии проверяются локально в JVM.  
- **Какая версия Java требуется?** Полностью поддерживается Java 8 и выше.  
- **Сколько времени занимает настройка?** Около 10 минут для базовой реализации.

## Что означает «сохранить EPS в PNG»?
Сохранение EPS как PNG преобразует векторный документ Encapsulated PostScript в растровое изображение PNG, сохраняет прозрачность и обеспечивает без потерь сжатие. Такое преобразование полезно, когда нужны графики для веба, миниатюры или печатные превью, которые можно отобразить в любом браузере без необходимости PostScript‑интерпретатора.

## Почему рендерить EPS в PNG с помощью Aspose.Page?
Aspose.Page предоставляет чисто Java‑API, которое растеризует файлы EPS с высокой точностью, поддерживает более 50 форматов вывода и предлагает метрическую лицензию, так что вы платите только за то, что конвертируете. Библиотека может обрабатывать документы из сотен страниц без загрузки всего файла в память, обеспечивая быструю и точную отрисовку на любой платформе, поддерживающей JVM.

## Необходимые условия
Перед началом убедитесь, что у вас есть:

- Базовый опыт разработки на Java.  
- Библиотека Aspose.Page, скачанная со [страницы загрузки Aspose.Page Java](https://releases.aspose.com/page/java/).  
- Пара публичного и приватного ключей метрической лицензии из вашего аккаунта Aspose.  

## Импорт пакетов
Операторы `import` подключают необходимые классы. Сохраните этот блок точно как показано, чтобы код компилировался без изменений.

Классы из `java.io` работают с файловыми потоками, а классы Aspose.Page управляют лицензированием, загрузкой документа и рендерингом изображения.

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

### Прямой ответ
Загрузите ваш EPS‑файл, примените метрическую лицензию, настройте `ImageSaveOptions` для PNG, отрендерите документ в `ImageDevice` и, наконец, запишите полученный массив байтов на диск. Эта последовательность завершает процесс **сохранить EPS как PNG** всего в несколько строк кода Java.

### Шаг 1: инициализация документа и формата изображения
Сначала задайте метрические ключи и определите формат вывода (PNG). Это закладывает основу для конвертации.

Класс `MeteredLicense` хранит ваши публичный и приватный ключи, а `ImageSaveOptions` указывает Aspose.Page генерировать PNG‑вывод.

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

### Шаг 2: инициализация входного потока PostScript
Откройте EPS‑файл, который хотите конвертировать. Поток передаёт документ в Aspose.Page.

`FileInputStream` читает EPS‑файл с диска, позволяя конструктору `Document` разобрать данные PostScript.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Шаг 3: проверка лицензии документа
Всегда проверяйте, что метрическая лицензия применена корректно перед обработкой.

Метод `isLicensed()` возвращает `true` только при валидных ключах, предотвращая случайное использование нелицензированной библиотеки.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Шаг 4: инициализация параметров и устройства изображения
Создайте объект параметров, управляющий настройками конвертации, и устройство, которое получит отрисованное изображение.

`ImageDevice` захватывает растровый вывод в памяти, а `ImageSaveOptions` позволяет настроить DPI, уровень сжатия и глубину цвета.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Шаг 5: сохранение EPS‑файла как изображения
Это основной вызов **сохранить EPS как PNG**. Документ рендерится в устройство изображения с использованием настроек.

Метод `document.save(device, options)` выполняет растеризацию за один шаг.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Шаг 6: получение и сохранение байтов изображения
Извлеките PNG‑байты из устройства и запишите их в файл на диске. Этот шаг демонстрирует, как **write PNG file Java** безопасно.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` сохраняет изображение без дополнительных библиотек.

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
| **Лицензия не распознана** | Ключи неверны или `setMeteredKey` вызывается после обработки документа. | Дважды проверьте строки публичного/приватного ключа и убедитесь, что `setMeteredKey` вызывается до любых вызовов Aspose.Page. |
| **Выходной файл пустой** | `device.getImagesBytes()` вернул `null`, потому что EPS‑файл не удалось разобрать. | Убедитесь, что EPS‑файл корректен и `ImageSaveOptions` задаёт ненулевой размер холста. |
| **OutOfMemoryError при большом EPS** | Рендеринг крупных векторных файлов потребляет много памяти кучи. | Обрабатывайте страницы по одной или увеличьте размер кучи JVM (`-Xmx2g`). |

## Часто задаваемые вопросы

**Q: Как получить публичный и приватный ключи метрической лицензии?**  
**A:** Войдите в ваш аккаунт Aspose, перейдите в раздел **Metered License** и скопируйте сгенерированные публичный и приватный ключи.

**Q: Является ли библиотека Aspose.Page бесплатной?**  
**A:** Aspose.Page предлагает бесплатную пробную версию с полной функциональностью; для продакшн‑использования требуется платная лицензия. Скачайте пробную версию со [страницы загрузки Aspose trial download page](https://releases.aspose.com/).

**Q: Можно ли использовать Aspose.Page в коммерческих проектах?**  
**A:** Да, коммерческая лицензия позволяет развёртывать библиотеку в продакшн‑окружениях. Приобретите лицензию на [странице покупки Aspose purchase page](https://purchase.aspose.com/buy).

**Q: Где найти дополнительную документацию?**  
**A:** Полная ссылка на API доступна в [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Как получить временную лицензию для оценки?**  
**A:** Временные лицензии выдаются через портал Aspose на [странице временной лицензии Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Что делать, если нужно конвертировать многостраничные EPS‑файлы?**  
**A:** Пройдитесь по каждой странице с помощью `device.getImagesBytes()` и запишите каждый массив байтов в отдельный PNG‑файл.

**Q: Можно ли изменить качество PNG или глубину цвета?**  
**A:** Да, настройте `ImageSaveOptions` (например, `options.setCompressionLevel(9)`) перед вызовом `document.save(...)`.

**Последнее обновление:** 2026-09-24  
**Тестировано с:** Aspose.Page 24.12 for Java (latest)  
**Автор:** Aspose

## Связанные руководства

- [Как установить лицензию для Aspose.Page Java API – Управление лицензией](/page/java/license-management/)
- [Конвертация PS в PNG с помощью Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Изменение размера EPS с помощью Aspose.Page – Манипуляция EPS на Java](/page/java/manipulation-eps/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}