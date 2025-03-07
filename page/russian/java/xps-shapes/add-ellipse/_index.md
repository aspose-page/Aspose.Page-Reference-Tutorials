---
title: Добавьте эллипс радиального градиента с помощью Aspose.Page
linktitle: Добавить эллипс в Java XPS
second_title: API Aspose.Page Java
description: Изучите пошаговое руководство по добавлению эллипса с радиальным градиентом в Java XPS с помощью Aspose.Page для Java. Улучшите процесс создания документов без особых усилий.
weight: 10
url: /ru/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте эллипс радиального градиента с помощью Aspose.Page

## Введение
Добро пожаловать в наше пошаговое руководство по добавлению эллипса в Java XPS с использованием Aspose.Page для Java. Aspose.Page — это мощная библиотека Java, которая позволяет разработчикам легко работать с документами XPS. В этом уроке мы покажем вам процесс создания эллипса с радиальным градиентом и сохранения его в виде документа XPS.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- На вашем компьютере установлен Java Development Kit (JDK).
-  Скачана библиотека Aspose.Page для Java. Ты можешь его достать[здесь](https://releases.aspose.com/page/java/).
- Редактор кода по вашему выбору (Eclipse, IntelliJ и т. д.) для написания и выполнения кода Java.
## Импортировать пакеты
Убедитесь, что в ваш проект Java импортированы необходимые пакеты для использования Aspose.Page. Добавьте следующие операторы импорта в начало вашего Java-файла:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## Шаг 1. Настройка каталога документов
Определите путь к каталогу вашего документа, в котором будет сохранен документ XPS:
```java
String dataDir = "Your Document Directory";
```
## Шаг 2. Создайте документ XPS
Инициализируйте новый документ XPS, используя следующий код:
```java
XpsDocument doc = new XpsDocument();
```
## Шаг 3. Определите ограничители радиального градиента
Создайте список остановок градиента для эллипса с радиальным градиентом:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Шаг 4. Создайте геометрию пути
Определите эллипс с радиальным градиентом, используя геометрию пути:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Шаг 5. Добавьте холст и путь
Добавьте в документ новый холст и добавьте путь с определенной геометрией:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Шаг 6: Установите обводку и градиент
Настройте обводку пути с помощью кисти радиального градиента:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Шаг 7: Установите толщину обводки
Укажите толщину обводки контура:
```java
path.setStrokeThickness(12f);
```
## Шаг 8: Сохраните документ
Сохраните полученный документ XPS:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Поздравляем! Вы успешно добавили эллипс с радиальным градиентом в Java XPS, используя Aspose.Page для Java.
## Заключение
В этом уроке мы рассмотрели шаги по созданию документа XPS с визуально привлекательным эллипсом с радиальным градиентом. Aspose.Page для Java упрощает манипулирование документами XPS, предоставляя разработчикам мощный набор инструментов.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java с другими библиотеками Java?
Да, Aspose.Page для Java можно легко интегрировать с другими библиотеками Java.
### Подходит ли Aspose.Page для крупномасштабной обработки документов?
Абсолютно! Aspose.Page предназначен для эффективной обработки крупномасштабных документов.
### Где я могу найти дополнительные руководства и примеры для Aspose.Page для Java?
 Посетить[Документация Aspose.Page для Java](https://reference.aspose.com/page/java/)для подробных руководств и примеров.
### Как я могу получить временную лицензию на Aspose.Page для Java?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Существуют ли форумы сообщества для обсуждений Aspose.Page?
 Да, присоединяйтесь[Форум сообщества Aspose.Page](https://forum.aspose.com/c/page/39) взаимодействовать с другими разработчиками и получать помощь.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
