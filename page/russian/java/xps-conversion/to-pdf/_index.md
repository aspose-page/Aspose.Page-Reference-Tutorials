---
date: 2025-12-23
description: Изучите, как преобразовать XPS в PDF на Java с помощью Aspose.Page. Это
  руководство показывает пошаговое преобразование, как отрисовать PDF из XPS и указать
  номера страниц PDF.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Как конвертировать XPS в PDF на Java
url: /ru/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как конвертировать XPS в PDF на Java

## Как конвертировать XPS в PDF на Java
В мире разработки на Java **как конвертировать XPS в PDF** – часто задаваемый вопрос. Независимо от того, создаёте ли вы систему управления документами или вам нужно генерировать печатные отчёты, надёжное преобразование XPS‑файлов может стать решающим фактором. К счастью, Aspose.Page for Java делает процесс **рендеринга PDF из XPS** простым и требует всего несколько строк кода.

## Быстрые ответы
- **Какая библиотека выполняет конвертацию?** Aspose.Page for Java.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базовой настройки.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; для продакшн‑использования требуется лицензия.  
- **Можно ли конвертировать только выбранные страницы?** Да – используйте опцию *specify PDF page numbers*.  
- **Является ли конвертация без потерь?** Библиотека сохраняет векторную графику и точность текста.

## Что такое конвертация XPS в PDF?
XPS (XML Paper Specification) – фиксированный формат документов от Microsoft. Преобразование его в PDF позволяет делиться, печатать или архивировать документы, используя общепринятый стандарт PDF.

## Почему стоит использовать Aspose.Page for Java для рендеринга PDF из XPS?
- **Высокая точность** – сохраняет векторную графику, шрифты и макет.  
- **Тонкая настройка** – можно задать качество изображений, степень сжатия и даже выбрать конкретные страницы.  
- **Отсутствие внешних зависимостей** – чистый Java‑код, работает на любой платформе с поддержкой JDK.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть:

- **Java Development Kit (JDK)** – любая современная версия (рекомендовано 8+).  
- **Aspose.Page for Java** – скачайте библиотеку из официальной [documentation](https://reference.aspose.com/page/java/).  
- XPS‑файл, который вы хотите конвертировать.

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые пакеты для работы с Aspose.Page for Java. Этот шаг важен для доступа к функциям, необходимым для конвертации XPS в PDF.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Пошаговое руководство

### Шаг 1: Установите каталог документов
Определите путь к папке, содержащей ваш исходный XPS‑файл.

```java
String dataDir = "Your Document Directory";
```

### Шаг 2: Инициализируйте поток вывода PDF
Создайте `FileOutputStream`, который будет принимать сгенерированный PDF.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Шаг 3: Загрузите XPS‑документ
Загрузите XPS‑файл с помощью Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Шаг 4: Инициализируйте параметры сохранения PDF  
Создайте параметры конвертации. Здесь вы можете **specify PDF page numbers**, настроить качество изображений и задать степень сжатия.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Шаг 5: Создайте устройство рендеринга PDF  
Настройте устройство рендеринга, которое будет записывать вывод в PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Шаг 6: Сохраните документ  
Наконец, сохраните XPS‑документ как PDF, используя настроенные параметры и устройство.

```java
document.save(device, options);
```

Повторите эти шаги, изменяя пути к файлам и параметры в соответствии с вашими конкретными требованиями.

## Как указать номера страниц PDF при конвертации XPS
Если вам нужен только подмножество страниц из исходного XPS, заполните массив `setPageNumbers` нужными индексами страниц (начиная с 1). Это помогает уменьшить размер файла и сократить время обработки.

## Распространённые проблемы и их решение
- **FileNotFoundException** – Убедитесь, что `dataDir` указывает на правильную папку и имя XPS‑файла совпадает.  
- **LicenseException** – Для продакшн‑использования требуется действующая лицензия Aspose.Page; иначе библиотека работает в режиме оценки с водяным знаком.  
- **Низкое качество изображений** – Увеличьте `setJpegQualityLevel` или переключитесь на без потерь сжатие при необходимости.

## Часто задаваемые вопросы
### Могу ли я конвертировать XPS‑файлы с несколькими страницами, используя Aspose.Page for Java?
Да, вы можете **specify PDF page numbers** в `PdfSaveOptions` (см. Шаг 4), чтобы включить любые нужные страницы.

### Где можно получить дополнительную поддержку или обсудить вопросы, связанные с Aspose.Page?
Посетите [Aspose.Page forum](https://forum.aspose.com/c/page/39) для общения с сообществом и получения помощи.

### Доступна ли бесплатная пробная версия Aspose.Page for Java?
Да, вы можете изучить возможности с помощью [free trial](https://releases.aspose.com/).

### Как получить временную лицензию для Aspose.Page for Java?
Перейдите по [this link](https://purchase.aspose.com/temporary-license/) для получения информации о временной лицензии.

### Где можно приобрести лицензию Aspose.Page for Java?
Купить лицензию можно [here](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2025-12-23  
**Тестировано с:** Aspose.Page for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}