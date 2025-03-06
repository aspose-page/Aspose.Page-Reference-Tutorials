---
title: Добавить изображение в Java PostScript
linktitle: Добавить изображение в Java PostScript
second_title: API Aspose.Page Java
description: Изучите плавную интеграцию Aspose.Page Java в этом руководстве по добавлению изображений в документы PostScript. Расширьте свои возможности манипулирования документами.
weight: 10
url: /ru/java/postscript-image-manipulation/add-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить изображение в Java PostScript

## Введение
В этом уроке мы рассмотрим, как добавлять изображения в документ Java PostScript с помощью библиотеки Aspose.Page для Java. Aspose.Page — это мощная библиотека, предоставляющая различные функции для работы с файлами PostScript, позволяющая разработчикам легко манипулировать и улучшать свои документы.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлен Java Development Kit (JDK).
-  Aspose.Page для библиотеки Java. Вы можете скачать его[здесь](https://releases.aspose.com/page/java/).
- Базовое понимание программирования на Java.
## Импортировать пакеты
Для начала импортируйте необходимые пакеты в свой Java-проект. Используйте следующий фрагмент кода в качестве ссылки:
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Шаг 1: Напишите сохранение графики
Первый шаг включает запись графического изображения в документ. Это гарантирует, что любые преобразования или изменения, сделанные впоследствии, можно будет при необходимости отменить.
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать выходной поток для документа PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Создайте варианты сохранения с размером А4.
PsSaveOptions options = new PsSaveOptions();
// Создайте новый документ PS с открытой страницей.
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## Шаг 2: Перевести и преобразовать
Затем переведите документ и создайте объект BufferedImage из файла изображения. Примените серию преобразований, таких как масштабирование и вращение, с помощью AffineTransform.
```java
document.translate(100, 100);
// Создайте объект BufferedImage из файла изображения.
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Создать преобразование изображения
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## Шаг 3. Добавьте изображение в документ
Теперь добавьте преобразованное изображение в документ.
```java
document.drawImage(image, transform, null);
```
## Шаг 4. Запись восстановления графики
После добавления изображения запишите восстановление графики, чтобы завершить внесенные изменения.
```java
document.writeGraphicsRestore();
```
## Шаг 5. Закройте текущую страницу и сохраните.
Закройте текущую страницу и сохраните документ.
```java
document.closePage();
document.save();
```
Повторите эти шаги для добавления нескольких изображений или настройте преобразования в соответствии со своими требованиями.
## Заключение
 Поздравляем! Вы успешно научились добавлять изображения в документ Java PostScript с помощью Aspose.Page для Java. Исследовать[документация](https://reference.aspose.com/page/java/) для более продвинутых функций и возможностей.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java с другими языками программирования?
Aspose.Page в основном поддерживает Java, но существуют версии и для других языков программирования.
### Доступна ли бесплатная пробная версия Aspose.Page для Java?
 Да, вы можете получить доступ к бесплатной пробной версии[здесь](https://releases.aspose.com/).
### Как я могу получить временную лицензию на Aspose.Page для Java?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу найти поддержку сообщества и обсуждения, связанные с Aspose.Page для Java?
 Посетить[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.
### Существуют ли дополнительные ресурсы для приобретения Aspose.Page для Java?
 Вы можете купить библиотеку[здесь](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
