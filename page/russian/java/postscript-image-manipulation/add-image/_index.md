---
date: 2026-02-15
description: Узнайте, как создавать документы PostScript на Java и генерировать файлы
  документов PostScript с перемещением и вращением изображений, используя Aspose.Page
  для Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Создать PostScript Java – Добавить изображение в Java PostScript
url: /ru/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PostScript Java – Добавление изображения в Java PostScript

## Введение
В этом руководстве вы узнаете, как **create postscript java** документы и встраивать изображения с помощью библиотеки Aspose.Page for Java. Мы пройдем каждый шаг, от инициализации нового файла PostScript до применения преобразований **translate and rotate image**. К концу вы сможете программно генерировать файлы PostScript и точно управлять размещением изображений — идеально для автоматизированных отчетов, печатных процессов или любой ситуации, когда необходимо **generate postscript document** вывод из Java.

## Быстрые ответы
- **What library is required?** Aspose.Page for Java  
- **Can I add multiple images?** Да — повторите шаги трансформации и отрисовки  
- **Do I need a license for development?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется лицензия  
- **Which Java version is supported?** Java 8 и новее  
- **Is image rotation supported?** Абсолютно — используйте `AffineTransform.rotate()`

## Что такое create postscript java?
Операция **create postscript java** создает файл описания страницы PostScript, который кодирует текст, векторную графику и растровые изображения. С помощью Aspose.Page вы можете создавать такие файлы напрямую из Java‑кода, получая полный программный контроль над расположением, масштабированием и вращением без необходимости отдельного интерпретатора PostScript.

## Почему использовать Aspose.Page для работы с изображениями?
- **High‑level API:** Абстрагирует низкоуровневые команды PostScript в простые методы Java.  
- **Cross‑platform:** Работает на любой ОС, поддерживающей Java.  
- **Full graphics‑state control:** Сохранение, восстановление, перемещение, масштабирование и вращение графики по желанию.  
- **No external dependencies:** Внутри обрабатывает загрузку изображений, конвертацию форматов и встраивание.

## Требования
- Установленный Java Development Kit (JDK).  
- Библиотека Aspose.Page for Java. Скачать её можно [здесь](https://releases.aspose.com/page/java/).  
- Базовое понимание программирования на Java.  

## Импорт пакетов
Чтобы начать, импортируйте необходимые пакеты в ваш Java‑проект. Используйте следующий фрагмент кода в качестве справки:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Шаг 1: Сохранить графику
Первый шаг заключается в записи сохранения графики в документ. Это гарантирует, что любые последующие трансформации или изменения можно будет откатить при необходимости.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Шаг 2: Переместить и трансформировать (translate and rotate image)
Далее переместите документ и создайте объект `BufferedImage` из файла изображения. Примените серию трансформаций, таких как масштабирование и вращение, используя `AffineTransform`. Здесь происходит операция **translate and rotate image**.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Шаг 3: Добавить изображение в документ
Теперь добавьте трансформированное изображение в документ.

```java
document.drawImage(image, transform, null);
```

## Шаг 4: Восстановить графику
После добавления изображения запишите восстановление графики, чтобы завершить внесённые изменения.

```java
document.writeGraphicsRestore();
```

## Шаг 5: Закрыть текущую страницу и сохранить
Закройте текущую страницу и сохраните документ.

```java
document.closePage();
document.save();
```

Вы можете повторять эти шаги для добавления нескольких изображений или настройки трансформаций в соответствии с вашими требованиями.

## Распространённые проблемы и решения
- **FileNotFoundException:** Убедитесь, что путь `dataDir` заканчивается разделителем файлов (`/` или `\\`) и имя файла изображения указано точно.  
- **ImageIO.read returns null:** Проверьте, поддерживается ли формат изображения (например, JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` ожидает радианы. При необходимости преобразуйте градусы в радианы (`Math.toRadians(degrees)`).

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Page for Java с другими языками программирования?**  
A: Aspose.Page в основном поддерживает Java, но существуют версии для других языков программирования.

**Q: Есть ли бесплатная пробная версия Aspose.Page for Java?**  
A: Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

**Q: Как получить временную лицензию для Aspose.Page for Java?**  
A: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Где найти поддержку сообщества и обсуждения, связанные с Aspose.Page for Java?**  
A: Посетите [Aspose.Page Forum](https://forum.aspose.com/c/page/39) для поддержки сообщества.

**Q: Есть ли дополнительные ресурсы для покупки Aspose.Page for Java?**  
A: Приобрести библиотеку можно [здесь](https://purchase.aspose.com/buy).

## Заключение
Поздравляем! Вы успешно изучили, как **create postscript java** документы и встраивать изображения с помощью Aspose.Page for Java. Изучите [документацию](https://reference.aspose.com/page/java/) для более продвинутых функций и возможностей, таких как векторная графика, рендеринг текста и пользовательские размеры страниц.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}