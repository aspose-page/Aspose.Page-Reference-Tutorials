---
title: Добавьте круговой эллипс в документ XPS с помощью Aspose.Page для .NET
linktitle: Добавьте круговой эллипс в документ XPS
second_title: Aspose.Page .NET API
description: Улучшите документы XPS с помощью ярких радиальных градиентов с помощью Aspose.Page для .NET. Следуйте нашему пошаговому руководству, чтобы получить потрясающие визуальные эффекты.
type: docs
weight: 11
url: /ru/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## Введение

Создание визуально привлекательных документов XPS является общим требованием в различных приложениях. Aspose.Page для .NET предоставляет мощный набор функций для эффективного управления документами XPS. В этом уроке мы сосредоточимся на добавлении кругового эллипса в документ XPS с помощью Aspose.Page для .NET. Следуйте инструкциям ниже, чтобы улучшить ваши документы XPS с помощью ярких радиальных градиентов.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

-  Установлена библиотека Aspose.Page для .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/page/net/).
- Среда разработки, предпочтительно Visual Studio или любой другой инструмент разработки .NET.
- Базовые знания программирования на C#.

## Импортировать пространства имен

Для начала включите необходимые пространства имен в свой код C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Теперь давайте разобьем пример на несколько этапов:

## Шаг 1. Настройте документ

```csharp
// ExStart:1
// Путь к каталогу документов.
string dataDir = "Your Document Directory";
// Создать новый документ XPS
XpsDocument doc = new XpsDocument();
```

Здесь мы инициализируем новый документ XPS, используя Aspose.Page для .NET.

## Шаг 2. Определите эллипс радиального градиента

```csharp
// Эллипс с радиальным градиентом в левом нижнем углу
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Этот шаг включает в себя определение эллипса радиального градиента с различными цветовыми точками.

## Шаг 3: Установите кисть радиального градиента

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Здесь мы задаем обводку эллипса кистью радиального градиента, снабжая ее необходимыми параметрами.

## Шаг 4: Отрегулируйте толщину обводки

```csharp
path.StrokeThickness = 12f;
```

Этот шаг включает в себя настройку толщины обводки для лучшей визуализации.

## Шаг 5. Сохраните полученный документ XPS.

```csharp
// Сохраните полученный документ XPS.
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd:1
```

Наконец, сохраните измененный документ XPS в нужном месте.

## Заключение

Поздравляем! Вы успешно добавили круговой эллипс с радиальными градиентами в свой документ XPS с помощью Aspose.Page для .NET. Поэкспериментируйте с различными параметрами и цветами, чтобы добиться желаемых визуальных эффектов в ваших документах.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Page для .NET с другими форматами документов?

A1: Aspose.Page для .NET специально предназначен для манипулирования документами XPS. Для других форматов рассмотрите возможность использования связанных библиотек Aspose.

### Вопрос 2. Доступна ли временная лицензия для целей тестирования?

 О2: Да, вы можете получить временную лицензию на тестирование, посетив[эта ссылка](https://purchase.aspose.com/temporary-license/).

### Вопрос 3. Где я могу найти дополнительную помощь и обсуждения?

 A3: Посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) за поддержку сообщества и обсуждения.

### В4: Есть ли образцы документов для справки?

 А4: Исследуйте[документация](https://reference.aspose.com/page/net/) подробные примеры и рекомендации.

### Вопрос 5: Могу ли я приобрести Aspose.Page для .NET?

 О5: Да, вы можете приобрести библиотеку.[здесь](https://purchase.aspose.com/buy).