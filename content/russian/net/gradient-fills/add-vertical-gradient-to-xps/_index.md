---
title: Добавьте вертикальный градиент в XPS с помощью Aspose.Page для .NET
linktitle: Добавьте вертикальный градиент в XPS
second_title: Aspose.Page .NET API
description: Узнайте, как улучшить документы XPS с помощью вертикальных градиентов с помощью Aspose.Page для .NET. Следуйте нашему пошаговому руководству для бесшовной интеграции.
type: docs
weight: 15
url: /ru/net/gradient-fills/add-vertical-gradient-to-xps/
---
## Введение

Добро пожаловать в это пошаговое руководство о том, как добавить вертикальный градиент в документ XPS с помощью Aspose.Page для .NET. Aspose.Page — это мощный API, который позволяет вам работать с файлами XPS (спецификация бумаги XML) в ваших .NET-приложениях. В этом уроке мы покажем вам процесс создания нового документа XPS, добавления вертикального градиента к контуру и сохранения результата.

## Предварительные условия

Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:

-  Библиотека Aspose.Page для .NET: убедитесь, что в вашей среде разработки установлена библиотека Aspose.Page для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/page/net/).

- Среда разработки: настройте среду разработки .NET с помощью предпочитаемой вами среды разработки, например Visual Studio.

Теперь давайте начнем с добавления вертикального градиента в документ XPS с помощью Aspose.Page для .NET.

## Импортировать пространства имен

В вашем .NET-приложении включите необходимые пространства имен для доступа к классам и методам Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Шаг 1. Настройте каталог документов

Прежде чем начать, укажите путь к каталогу вашего документа, в котором вы хотите сохранить полученный документ XPS.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Шаг 2. Создайте новый документ XPS

Инициализируйте новый документ XPS, используя следующий код:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Шаг 3. Определите остановки градиента

Создайте список остановок градиента, указав цвет и положение каждой остановки. В этом примере мы определяем вертикальный градиент с пятью остановками.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Шаг 4. Создайте путь с градиентом

Определите путь, указав его геометрию, и примените к нему кисть с линейным градиентом.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Шаг 5. Сохраните полученный документ XPS.

Сохраните измененный документ XPS в указанном вами каталоге.

```csharp
// ЭксСтарт:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

Поздравляем! Вы успешно добавили вертикальный градиент в документ XPS с помощью Aspose.Page для .NET.

## Заключение

В этом уроке мы рассмотрели, как использовать Aspose.Page для .NET для улучшения документов XPS с помощью вертикальных градиентов. Aspose.Page упрощает сложные задачи, предоставляя разработчикам удобный способ манипулировать файлами XPS в своих .NET-приложениях.

## Часто задаваемые вопросы

### Вопрос 1. Совместим ли Aspose.Page с Visual Studio 2019?

О1: Да, Aspose.Page совместим с Visual Studio 2019. Убедитесь, что у вас установлена правильная версия библиотеки.

### Вопрос 2: Могу ли я использовать Aspose.Page для коммерческих проектов?

 О2: Да, Aspose.Page можно использовать для коммерческих проектов. Посещать[здесь](https://purchase.aspose.com/buy) изучить варианты лицензирования.

### В3: Есть ли бесплатная пробная версия?

 О3: Да, вы можете получить бесплатную пробную версию Aspose.Page.[здесь](https://releases.aspose.com/).

### Вопрос 4: Где я могу найти документацию Aspose.Page?

 A4: документация доступна.[здесь](https://reference.aspose.com/page/net/).

### В5: Как я могу получить поддержку или задать вопросы?

 A5: Посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.