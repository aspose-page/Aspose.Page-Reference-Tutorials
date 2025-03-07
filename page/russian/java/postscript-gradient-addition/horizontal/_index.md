---
title: Добавьте горизонтальный градиент в Java PostScript
linktitle: Добавьте горизонтальный градиент в Java PostScript
second_title: API Aspose.Page Java
description: Узнайте, как добавить горизонтальный градиент в Java PostScript с помощью Aspose.Page для Java. Создавайте визуально потрясающие документы без особых усилий.
weight: 11
url: /ru/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте горизонтальный градиент в Java PostScript

## Введение
Добро пожаловать в это подробное руководство по добавлению горизонтального градиента в Java PostScript с использованием Aspose.Page для Java. Aspose.Page — мощная библиотека Java, которая позволяет разработчикам работать с PostScript и другими форматами документов. В этом уроке мы проведем вас через процесс создания документа PostScript с горизонтальным градиентом, используя пошаговые примеры.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- На вашем компьютере установлен Java Development Kit (JDK).
- Aspose.Page для библиотеки Java. Вы можете скачать его с сайта[Документация Aspose.Page Java](https://reference.aspose.com/page/java/).
## Импортировать пакеты
Начните с импорта необходимых пакетов в ваш Java-проект. Эти пакеты имеют решающее значение для работы с Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Шаг 1: Создайте прямоугольник
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать выходной поток для документа PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Создайте варианты сохранения с размером А4.
PsSaveOptions options = new PsSaveOptions();
// Создайте новый документ PS с открытой страницей.
PsDocument document = new PsDocument(outPsStream, options, false);
//Создайте прямоугольник
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Шаг 2. Создайте горизонтальный линейный градиент.
```java
// Создайте горизонтальную линейную градиентную краску. Компоненты масштаба в преобразовании должны быть равны ширине и высоте прямоугольника.
// Компоненты перевода — это смещения прямоугольника.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Установить краску
document.setPaint(paint);
```
## Шаг 3: Заполните прямоугольник
```java
// Заполните прямоугольник
document.fill(rectangle);
```
## Шаг 4. Заполните текст градиентом
```java
// Залейте текст градиентом
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Шаг 5: обведите текст градиентом
```java
// Обводка текста градиентом
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Заключение
Поздравляем! Вы успешно добавили горизонтальный градиент в Java PostScript, используя Aspose.Page для Java. В этом руководстве представлено подробное пошаговое руководство, которое поможет вам создавать визуально привлекательные документы PostScript.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java в коммерческих проектах?
Да, Aspose.Page для Java можно использовать в коммерческих проектах. Подробности о лицензировании см.[Aspose.Купить](https://purchase.aspose.com/buy).
### Доступна ли бесплатная пробная версия?
 Да, вы можете получить доступ к бесплатной пробной версии Aspose.Page для Java.[здесь](https://releases.aspose.com/).
### Где я могу найти дополнительную документацию и поддержку?
 Посетить[Документация Aspose.Page Java](https://reference.aspose.com/page/java/) для комплексных ресурсов. Для поддержки сообщества проверьте[Форум Aspose.Page](https://forum.aspose.com/c/page/39).
### Как получить временную лицензию?
 Вы можете получить временную лицензию[Aspose.Купить](https://purchase.aspose.com/temporary-license/).
### Каковы системные требования для Aspose.Page для Java?
 Обратитесь к[документация](https://reference.aspose.com/page/java/) подробные системные требования.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
