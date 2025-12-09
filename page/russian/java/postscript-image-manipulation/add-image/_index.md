---
date: 2025-12-09
description: Узнайте, как создавать PostScript‑документы на Java и перемещать и вращать
  изображение с помощью Aspose.Page для бесшовной обработки изображений.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Создание документа PostScript в Java – Добавление изображения в PostScript
  на Java
url: /ru/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PostScript документа в Java – Добавление изображения в Java PostScript

## Введение
В этом руководстве вы узнаете, как **создать PostScript документ в Java** и встроить изображения с помощью библиотеки Aspose.Page for Java. Мы пройдем каждый шаг, от настройки документа до применения преобразований, таких как **перемещение и вращение изображения**. К концу вы сможете программно генерировать богатые PostScript‑файлы и настраивать размещение изображений в соответствии с вашими требованиями к макету.

## Быстрые ответы
- **Какая библиотека требуется?** Aspose.Page for Java  
- **Можно ли добавить несколько изображений?** Да – повторяйте шаги преобразования и отрисовки  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшена требуется лицензия  
- **Какая версия Java поддерживается?** Java 8 и выше  
- **Поддерживается ли вращение изображения?** Конечно – используйте `AffineTransform.rotate()`  

## Что значит создание PostScript документа в Java?
PostScript документ – это файл языка описания страниц, который описывает текст, графику и изображения. С помощью Aspose.Page вы можете программно генерировать такие файлы в Java, получая полный контроль над макетом, состоянием графики и обработкой изображений без необходимости в PostScript‑интерпретаторе.

## Почему стоит использовать Aspose.Page для работы с изображениями?
- **Высокоуровневый API:** упрощает сложные команды PostScript.  
- **Кроссплатформенный:** работает на любой ОС, поддерживающей Java.  
- **Полный контроль над состоянием графики:** легко сохранять, восстанавливать, перемещать, масштабировать и вращать графику.  
- **Без внешних зависимостей:** загрузка и конвертация изображений осуществляется внутри библиотеки.

## Предварительные требования
Прежде чем перейти к коду, убедитесь, что у вас есть:

- Установленный Java Development Kit (JDK).  
- Библиотека Aspose.Page for Java. Скачать её можно [здесь](https://releases.aspose.com/page/java/).  
- Базовые знания программирования на Java.  

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

## Шаг 1: Сохранение графического состояния
Первый шаг – записать сохранение графического состояния в документ. Это гарантирует, что любые последующие преобразования или изменения можно будет откатить при необходимости.

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

## Шаг 2: Перемещение и преобразование (перемещение и вращение изображения)
Далее переместите документ и создайте объект `BufferedImage` из файла изображения. Примените серию преобразований, таких как масштабирование и вращение, с помощью `AffineTransform`. Здесь происходит операция **перемещения и вращения изображения**.

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

## Шаг 3: Добавление изображения в документ
Теперь добавьте преобразованное изображение в документ.

```java
document.drawImage(image, transform, null);
```

## Шаг 4: Восстановление графического состояния
После добавления изображения запишите восстановление графического состояния, чтобы завершить внесённые изменения.

```java
document.writeGraphicsRestore();
```

## Шаг 5: Закрытие текущей страницы и сохранение
Закройте текущую страницу и сохраните документ.

```java
document.closePage();
document.save();
```

Вы можете повторять эти шаги, чтобы добавить несколько изображений или настроить преобразования в соответствии с вашими требованиями.

## Распространённые проблемы и решения
- **FileNotFoundException:** Убедитесь, что путь `dataDir` заканчивается разделителем файлов (`/` или `\\`) и имя файла изображения указано точно.  
- **ImageIO.read возвращает null:** Проверьте, поддерживается ли формат изображения (например, JPEG, PNG).  
- **Неправильный угол вращения:** `AffineTransform.rotate` ожидает радианы. При необходимости преобразуйте градусы в радианы (`Math.toRadians(degrees)`).  

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.Page for Java с другими языками программирования?**  
О: Aspose.Page в основном поддерживает Java, но существуют версии для других языков.

**В: Есть ли бесплатная пробная версия Aspose.Page for Java?**  
О: Да, её можно получить [здесь](https://releases.aspose.com/).

**В: Как получить временную лицензию для Aspose.Page for Java?**  
О: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где найти сообщество и обсуждения, связанные с Aspose.Page for Java?**  
О: Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.

**В: Есть ли дополнительные ресурсы для покупки Aspose.Page for Java?**  
О: Приобрести библиотеку можно [здесь](https://purchase.aspose.com/buy).

## Заключение
Поздравляем! Вы успешно научились **создавать PostScript документ в Java** и встраивать изображения с помощью Aspose.Page for Java. Изучайте [документацию](https://reference.aspose.com/page/java/) для более продвинутых возможностей, таких как векторная графика, рендеринг текста и пользовательские размеры страниц.

---

**Последнее обновление:** 2025-12-09  
**Тестировано с:** Aspose.Page for Java 23.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}