---
title: Добавить прямоугольник в Java XPS
linktitle: Добавить прямоугольник в Java XPS
second_title: API Aspose.Page Java
description: Узнайте, как добавлять прямоугольники в Java XPS с помощью Aspose.Page. Следуйте нашему пошаговому руководству для беспрепятственного управления документами. #JavaXPS #AsposePage
weight: 11
url: /ru/java/xps-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить прямоугольник в Java XPS

## Введение
Добро пожаловать в это подробное руководство по добавлению прямоугольников в Java XPS с помощью Aspose.Page! Независимо от того, являетесь ли вы опытным разработчиком или только начинаете работать с Java XPS, это руководство проведет вас через процесс с пошаговыми инструкциями, гарантируя, что вы получите глубокое понимание темы.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
- Базовые знания языка программирования Java.
-  Установлена библиотека Aspose.Page. Если нет, вы можете скачать его с сайта[Документация Aspose.Page Java](https://reference.aspose.com/page/java/).
- Рабочая среда разработки Java.
## Импортировать пакеты
Для начала импортируйте необходимые пакеты в свой Java-проект. Убедитесь, что библиотека Aspose.Page правильно добавлена в ваш путь к классам. Вот базовый пример:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Теперь давайте разобьем приведенный пример на несколько шагов по добавлению прямоугольника в Java XPS.
## Шаг 1. Установите каталог документов
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
```
Замените «Каталог ваших документов» на путь к нужному каталогу.
## Шаг 2. Создайте новый документ XPS
```java
// Создать новый документ XPS
XpsDocument doc = new XpsDocument();
```
Это инициализирует новый документ XPS.
## Шаг 3. Добавьте прямоугольник с обводкой сплошным цветом CMYK
```java
// CMYK (синий) прямоугольник со сплошной заливкой в левом нижнем углу.
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
На этом шаге добавляется обведенный прямоугольник сплошным цветом CMYK.
## Шаг 4. Сохраните полученный документ XPS.
```java
// Сохраните полученный документ XPS.
doc.save(dataDir + "AddRectangle_out.xps");
```
Наконец, сохраните измененный документ XPS с добавленным прямоугольником.
Повторите эти шаги, корректируя параметры по мере необходимости, чтобы дополнительно настроить прямоугольники.
## Заключение
Поздравляем! Вы успешно научились добавлять прямоугольники в Java XPS с помощью Aspose.Page. Это руководство обеспечивает прочную основу для ваших усилий по манипулированию документами XPS.
## Часто задаваемые вопросы
### Могу ли я добавить несколько прямоугольников в один документ XPS?
Да, вы можете добавить столько прямоугольников, сколько необходимо, повторяя шаги, описанные в руководстве.
### Как изменить цвет прямоугольника?
 Измените значения цвета в`createColor` метод достижения желаемого цвета.
### Подходит ли Aspose.Page для обработки сложных манипуляций с документами XPS?
Абсолютно! Aspose.Page предоставляет надежный набор функций для решения различных задач, связанных с документами XPS.
### Где я могу найти дополнительные примеры и поддержку?
 Исследовать[Форум Aspose.Page](https://forum.aspose.com/c/page/39)чтобы получить больше примеров и обратиться за помощью к сообществу.
### Могу ли я попробовать Aspose.Page перед покупкой?
 Да, вы можете изучить[бесплатная пробная версия](https://releases.aspose.com/) чтобы испытать возможности Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
