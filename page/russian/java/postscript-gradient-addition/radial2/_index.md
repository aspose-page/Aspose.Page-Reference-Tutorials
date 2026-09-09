---
date: 2026-09-09
description: Узнайте, как создать градиент в Java PostScript и добавить градиент к
  фигуре с помощью Aspose.Page. Следуйте этому пошаговому руководству с кодом и советами.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient с Aspose.Page
og_description: Узнайте, как создать градиент в Java PostScript и добавить градиент
  к фигуре с помощью Aspose.Page. Следуйте этому пошаговому руководству с кодом и
  советами.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Как создать градиент в Java PostScript с radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Как создать градиент в Java PostScript с radial fill
url: /ru/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать градиент в Java PostScript с радиальным заполнением

## Введение
В этом руководстве вы узнаете **как создавать градиентные** графики в документе PostScript с использованием Java и Aspose.Page. Мы пройдём каждый шаг — от настройки проекта до рендеринга круга, заполненного плавным радиальным градиентом — чтобы вы могли **добавлять градиент к формам** мгновенно и повысить визуальное качество ваших Java‑приложений.

## Быстрые ответы
- **Что создаёт это руководство?** Файл PostScript (`.ps`), содержащий круг, заполненный радиальным градиентом.  
- **Какая библиотека требуется?** Aspose.Page for Java (последняя версия).  
- **Сколько времени занимает реализация?** Около 10‑15 минут для работающего примера.  
- **Нужна ли лицензия?** Для использования в продакшене требуется временная или полная лицензия; бесплатная пробная версия подходит для разработки.  
- **Можно ли переиспользовать код для PDF или SVG?** Да — Aspose.Page поддерживает несколько форматов вывода с минимальными изменениями.

## Как заполнить форму градиентом в PostScript
Вы можете заполнить форму радиальным градиентом в PostScript, создав `PsDocument`, определив `RadialGradientPaint`, применив его к целевой форме и, наконец, сохранив документ. Такой лаконичный рабочий процесс позволяет создавать профессиональные векторные графики без растровых изображений, а тот же код можно переиспользовать для вывода в PDF или SVG. Процесс прост и работает последовательно во всех поддерживаемых форматах.

## Что такое радиальный градиент?
Радиальный градиент изменяет цвета от центральной точки наружу, создавая плавное круговое смешивание. Он идеален для подсветки, фона кнопок или любого визуального элемента, требующего естественного эффекта «сияния». Меняя цветовые остановки и радиус, можно имитировать освещение, глубину и свойства материалов в чистом векторном виде.

## Почему использовать Aspose.Page для радиальных градиентов?
Aspose.Page позволяет генерировать независимую от устройства векторную графику с помощью единого Java‑API. Он поддерживает более 50 форматов ввода и вывода — включая PostScript, PDF и SVG — при сохранении точности цветов и сглаживания для вывода высокого разрешения. Библиотека также предоставляет простые в использовании классы градиентов, делая реализацию сложных визуальных эффектов простой.

## Требования
- Базовое знакомство с программированием на Java.  
- Установленный JDK 8 или новее.  
- Библиотека Aspose.Page for Java (скачайте из [документации Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Импорт пакетов
Сначала импортируйте необходимые классы. Они включают стандартные типы графики AWT и API Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Шаг 1: настройка каталога документа
Определите папку, в которой будет сохранён сгенерированный файл PostScript. Замените заполнитель реальным путём на вашей системе.

```java
String dataDir = "Your Document Directory";
```

## Шаг 2: создание выходного потока
`FileOutputStream` записывает необработанные байты в файл, позволяя сохранять бинарные данные. Открытие потока, направленного в файл `.ps`, позволяет Aspose.Page передавать сгенерированные данные PostScript напрямую на диск.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Шаг 3: создание параметров сохранения
`PsSaveOptions` настраивает процесс сохранения файла PostScript, включая размер страницы и сжатие. Вы можете изменить эти параметры, но значения по умолчанию подходят для данного примера.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Шаг 4: создание PS‑документа
`PsDocument` представляет документ PostScript в памяти и предоставляет методы для добавления страниц и графики.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Шаг 5: создание круга
`Ellipse2D.Float` описывает форму эллипса; когда ширина = высоте, это идеальный круг. Этот объект будет служить холстом для нашего градиентного заполнения.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Как нарисовать круг с градиентом
Чтобы нарисовать круг с радиальным градиентом, загрузите `RadialGradientPaint` в графический контекст и затем заполните ранее определённый эллипс. Эта единственная операция раскрасит форму плавным переходом цвета от центра наружу, создавая визуально привлекательный эффект.

## Шаг 6: определение цветов градиента
Подготовьте два массива: один для цветов, которые будут использоваться в градиенте, и другой для соответствующих дробных позиций (0 = центр, 1 = край).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Шаг 7: создание AffineTransform
`AffineTransform` — это матрица, которая может перемещать, вращать, масштабировать или сдвигать графические объекты. Здесь она масштабирует и перемещает градиент, чтобы он точно вписался в круг.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Шаг 8: создание RadialGradientPaint
`RadialGradientPaint` создаёт радиальный цветовой градиент на основе центральной точки, радиуса и цветовых остановок.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Шаг 9: установка краски и заполнение круга
Примените градиентную краску к документу и заполните ранее определённый круг. Это ядро нашего **примера радиального градиента** и демонстрация того, как **заполнять форму градиентом**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Шаг 10: закрытие страницы и сохранение документа
Завершите страницу, запишите содержимое на диск и закройте поток. Ваш файл PostScript теперь готов к просмотру в любом PS‑просмотрщике.

```java
document.closePage();
document.save();
```

Поздравляем! Вы успешно создали пример радиального градиента в Java PostScript с использованием Aspose.Page. Теперь у вас есть переиспользуемый шаблон для **заполнения формы градиентом**, который можно адаптировать к другим формам и форматам вывода.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|----------|
| **FileNotFoundException** при открытии выходного потока | Убедитесь, что `dataDir` указывает на существующую папку и у вас есть права на запись. |
| Градиент выглядит плоским или отсутствует | Убедитесь, что массив `fractions` соответствует длине массива `colors` и что `AffineTransform` масштабируется корректно. |
| Цвета отображаются инвертированно | Поменяйте порядок цветов в массиве `colors` или скорректируйте координаты точки `focus`. |

## Часто задаваемые вопросы

**В: Где можно найти документацию по Aspose.Page for Java?**  
О: Полная ссылка на API доступна в [документации Aspose.Page Java API](https://reference.aspose.com/page/java/).

**В: Как скачать Aspose.Page for Java?**  
О: Скачайте последнюю JAR‑файл со [страницы релизов](https://releases.aspose.com/page/java/).

**В: Доступна ли бесплатная пробная версия?**  
О: Да — скачайте пробную версию со [страницы бесплатной пробной загрузки Aspose](https://releases.aspose.com/).

**В: Можно ли получить временную лицензию для тестирования?**  
О: Конечно, запросите её на [странице временной лицензии](https://purchase.aspose.com/temporary-license/).

**В: Где можно получить поддержку сообщества?**  
О: Присоединяйтесь к обсуждению на [форуме Aspose.Page](https://forum.aspose.com/c/page/39).

## Заключение
В этом руководстве мы создали полноценный **пример радиального градиента** для документа PostScript с использованием Aspose.Page for Java. Следуя шагам, вы получили переиспользуемый шаблон для **заполнения формы градиентом**, который можно адаптировать к PDF, SVG или любому другому формату, поддерживаемому Aspose.Page. Экспериментируйте с различными цветами, радиусами и формами, чтобы обогатить ваши Java‑графические проекты.

---

**Последнее обновление:** 2026-09-09  
**Тестировано с:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Автор:** Aspose

## Связанные руководства

- [Создать градиент PostScript в Java — добавить вертикальный градиент](/page/java/postscript-gradient-addition/vertical/)
- [Создать текстурный шаблон в PostScript с Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Учебник по прозрачности Aspose.Page — добавить прозрачность в Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}