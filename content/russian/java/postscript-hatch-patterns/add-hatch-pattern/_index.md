---
title: Добавить образец штриховки в Java PostScript
linktitle: Добавить образец штриховки в Java PostScript
second_title: API Aspose.Page Java
description: Узнайте, как добавлять привлекательные образцы штриховки в документы Java PostScript с помощью Aspose.Page. Улучшите свой визуальный контент без особых усилий.
type: docs
weight: 10
url: /ru/java/postscript-hatch-patterns/add-hatch-pattern/
---
## Введение
В мире программирования на Java улучшение визуальных элементов является обычным требованием для разработчиков. Одним из интригующих визуальных улучшений является добавление образцов штриховки в документы PostScript. Это руководство проведет вас через процесс добавления образцов штриховки с помощью Aspose.Page для Java.
## Предварительные условия
Прежде чем погрузиться в руководство, убедитесь, что у вас есть следующие настройки:
- Среда разработки Java: убедитесь, что у вас есть готовая среда разработки Java.
-  Библиотека Aspose.Page для Java: Загрузите и установите библиотеку Aspose.Page для Java. Вы можете найти необходимые файлы[здесь](https://releases.aspose.com/page/java/).
## Импортировать пакеты
Для начала импортируйте необходимые пакеты в свой Java-проект. Используйте следующий фрагмент кода:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Шаг 1. Установите начальные параметры
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать выходной поток для документа PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Создайте варианты сохранения с размером А4.
PsSaveOptions options = new PsSaveOptions();
// Создайте новый документ PS с открытой страницей.
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## Шаг 2. Сохраните состояние графики и переведите
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## Шаг 3. Создайте квадрат для каждого узора
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## Шаг 4. Настройте перо для контура квадратного узора
```java
BasicStroke stroke = new BasicStroke(2);
```
## Шаг 5. Перебор образцов штриховки
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (продолжите с предоставленным кодом)
}
```
## Шаг 6. Восстановите состояние графики
```java
document.writeGraphicsRestore();
```
## Шаг 7. Заполните текст штриховкой
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## Шаг 8: Обведите текст штриховкой
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## Шаг 9: Закройте и сохраните документ
```java
document.closePage();
document.save();
```
Выполните следующие шаги, и вы успешно добавите образцы штриховки в документ Java PostScript с помощью Aspose.Page.
## Заключение
Включение визуальных элементов, таких как штриховки, может значительно повысить привлекательность ваших Java-приложений. Aspose.Page для Java упрощает этот процесс, позволяя вам без особых усилий создавать визуально потрясающие документы PostScript.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java с другими платформами Java?
Да, Aspose.Page для Java предназначен для полной интеграции с различными платформами Java.
### Доступна ли пробная версия Aspose.Page для Java?
 Да, вы можете получить доступ к бесплатной пробной версии[здесь](https://releases.aspose.com/).
### Как я могу получить временную лицензию на Aspose.Page для Java?
 Вы можете приобрести временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу найти дополнительные руководства и поддержку по Aspose.Page для Java?
 Исследовать[Форум Aspose.Page для Java](https://forum.aspose.com/c/page/39) за обучающие материалы и поддержку сообщества.
### Существует ли исчерпывающая документация по Aspose.Page для Java?
 Да, обратитесь к документации[здесь](https://reference.aspose.com/page/java/).