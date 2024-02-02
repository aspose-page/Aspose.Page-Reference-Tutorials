---
title: Добавьте горизонтальный градиент в XPS с помощью Aspose.Page для .NET
linktitle: Добавьте горизонтальный градиент в XPS
second_title: Aspose.Page .NET API
description: Узнайте, как добавить потрясающие горизонтальные градиенты в ваши документы XPS с помощью Aspose.Page для .NET. Повышайте визуальную привлекательность без особых усилий.
type: docs
weight: 13
url: /ru/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## Введение

В этом уроке мы рассмотрим, как улучшить документы XPS, добавив горизонтальный градиент с помощью Aspose.Page для .NET. Aspose.Page для .NET — это мощная библиотека, обеспечивающая плавную обработку документов XPS (спецификация бумаги XML) в приложениях .NET. Добавление градиентов может сделать ваши документы визуально привлекательными, и это руководство шаг за шагом проведет вас через этот процесс.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1.  Библиотека Aspose.Page для .NET: убедитесь, что в вашей среде разработки установлена библиотека Aspose.Page для .NET. Вы можете скачать его с сайта[Документация Aspose.Page для .NET](https://reference.aspose.com/page/net/).

2. Среда разработки: настройте подходящую среду разработки, включая редактор кода, например Visual Studio.

## Импортировать пространства имен

Начните с импорта необходимых пространств имен в ваш проект. Эти пространства имен необходимы для работы с Aspose.Page для .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Теперь давайте разобьем приведенный пример на несколько этапов.

## Шаг 1. Установите путь к каталогу документов

```csharp
// ExStart:3
// Путь к каталогу документов.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Шаг 2. Создайте новый документ XPS

```csharp
// ExStart:4
// Создать новый документ XPS
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Шаг 3. Инициализируйте остановки градиента

```csharp
// ExStart:5
// Инициализировать список XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Шаг 4: Создайте новый путь

```csharp
// ExStart:6
//Создайте новый путь, определив геометрию в виде сокращений.
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Шаг 5. Сохраните полученный документ XPS.

```csharp
// ЭксСтарт:7
// Сохраните полученный документ XPS.
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Теперь вы успешно добавили горизонтальный градиент в свой документ XPS с помощью Aspose.Page для .NET.

## Заключение

Улучшение ваших документов XPS с помощью градиентов не только улучшает их визуальную привлекательность, но и обеспечивает более привлекательный пользовательский опыт. Aspose.Page для .NET упрощает этот процесс, позволяя вам без особых усилий добиться профессиональных результатов.

## Часто задаваемые вопросы

### Вопрос 1. Где я могу найти документацию Aspose.Page для .NET?

 A1: Вы можете найти документацию[здесь](https://reference.aspose.com/page/net/).

### Вопрос 2: Как загрузить Aspose.Page для .NET?

 A2: Вы можете скачать библиотеку с сайта[Страница загрузки Aspose.Page для .NET](https://releases.aspose.com/page/net/).

### Вопрос 3. Где я могу приобрести Aspose.Page для .NET?

 О3: Вы можете приобрести Aspose.Page для .NET на сайте[страница покупки](https://purchase.aspose.com/buy).

### В4: Доступна ли бесплатная пробная версия?

 О4: Да, вы можете получить бесплатную пробную версию на сайте[здесь](https://releases.aspose.com/).

### Вопрос 5: Как получить временную лицензию на Aspose.Page для .NET?

 О5: Вы можете получить временную лицензию на[эта ссылка](https://purchase.aspose.com/temporary-license/).