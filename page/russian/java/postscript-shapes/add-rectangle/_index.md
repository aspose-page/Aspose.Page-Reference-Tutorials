---
title: Настройка Java PostScript — добавление прямоугольников с помощью Aspose.Page
linktitle: Добавить прямоугольник в Java PostScript
second_title: API Aspose.Page Java
description: Изучите пошаговое руководство по добавлению ярких прямоугольников в документы Java PostScript с помощью Aspose.Page для Java. Улучшите настройку своего документа без особых усилий!
weight: 11
url: /ru/java/postscript-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка Java PostScript — добавление прямоугольников с помощью Aspose.Page

## Введение
Вы хотите улучшить свои документы Java PostScript с помощью ярких прямоугольников? Не смотрите дальше! В этом пошаговом руководстве мы рассмотрим, как использовать Aspose.Page для Java для добавления прямоугольников в ваши документы PostScript. Aspose.Page — это мощная библиотека, предоставляющая надежные функции для работы с файлами PostScript, что делает ее идеальным выбором для разработчиков, желающих манипулировать и настраивать свои документы.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Базовое понимание программирования на Java.
-  Установлена библиотека Aspose.Page для Java. Если нет, загрузите его с[Документация Aspose.Page для Java](https://reference.aspose.com/page/java/).
- На вашем компьютере установлена среда разработки Java.
## Импортировать пакеты
В вашем Java-проекте начните с импорта необходимых пакетов:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Учебник: добавление прямоугольников в Java PostScript
## Шаг 1: Установите краску для заполнения прямоугольника
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать выходной поток для документа PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Создайте варианты сохранения с размером А4.
PsSaveOptions options = new PsSaveOptions();
// Создайте новый документ PS с открытой страницей.
PsDocument document = new PsDocument(outPsStream, options, false);
// Установите краску для заливки прямоугольника.
document.setPaint(Color.ORANGE);        
// Заполните первый прямоугольник
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Шаг 2: Установите краску для обводки прямоугольника
```java
// Установите краску для обводки прямоугольника.
document.setPaint(Color.RED);
// Установить ход
document.setStroke(new BasicStroke(3));
// Обводка (обводка) второго прямоугольника
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Шаг 3. Закройте текущую страницу и сохраните документ.
```java
// Закрыть текущую страницу
document.closePage();
// Сохраните документ
document.save();
```
Поздравляем! Вы успешно добавили яркие прямоугольники в документ Java PostScript с помощью Aspose.Page.
## Заключение
В этом уроке мы рассмотрели процесс улучшения ваших документов Java PostScript с помощью прямоугольников с помощью Aspose.Page для Java. Эта мощная библиотека открывает целый мир возможностей для разработчиков, желающих легко настраивать и манипулировать своими документами.
Получайте удовольствие, экспериментируя с различными формами и цветами, чтобы сделать ваши документы визуально привлекательными!
## Часто задаваемые вопросы

### Могу ли я использовать Aspose.Page для Java с другими языками программирования?
Aspose.Page в основном поддерживает Java, но аналогичные библиотеки доступны и для других языков.
### Доступна ли пробная версия Aspose.Page для Java?
 Да, вы можете изучить возможности Aspose.Page для Java с помощью[бесплатная пробная версия](https://releases.aspose.com/).
### Где я могу найти дополнительную помощь и обсуждения?
 Посетить[Форум Aspose.Page](https://forum.aspose.com/c/page/39) взаимодействовать с сообществом и получать помощь.
### Как я могу получить временную лицензию на Aspose.Page для Java?
 Получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу приобрести лицензионную версию Aspose.Page для Java?
 Купить лицензионную версию[здесь](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
