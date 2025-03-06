---
title: Добавьте прямоугольник в документ XPS с помощью Aspose.Page для .NET
linktitle: Добавить прямоугольник в документ XPS
second_title: Aspose.Page .NET API
description: Усовершенствуйте создание документов с помощью Aspose.Page для .NET. Узнайте, как добавлять прямоугольники в документы XPS, в этом пошаговом руководстве.
weight: 13
url: /ru/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте прямоугольник в документ XPS с помощью Aspose.Page для .NET

## Введение

Aspose.Page для .NET — это мощная библиотека, предоставляющая множество функций для работы с документами XPS (XML Paper Spectrum) в приложениях .NET. В этом уроке мы сосредоточимся на добавлении прямоугольника в документ XPS с помощью Aspose.Page для .NET. Следуйте этому пошаговому руководству, чтобы улучшить процесс создания документов.

## Предварительные условия

Прежде чем приступить к работе с этим руководством, убедитесь, что у вас есть следующие предварительные условия:

1.  Библиотека Aspose.Page для .NET: убедитесь, что в вашей среде разработки установлена библиотека Aspose.Page для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/page/net/).

2. Каталог документов: настройте каталог, в котором вы хотите хранить документы XPS.

## Импортировать пространства имен

В вашем .NET-приложении включите необходимые пространства имен для использования функций Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Шаг 1. Установите каталог документов

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

## Шаг 3: Добавьте прямоугольник

```csharp
// ExStart:5
// CMYK (синий) прямоугольник со сплошной заливкой в левом нижнем углу.
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

## Шаг 4. Сохраните документ

```csharp
// ExStart:6
// Сохраните полученный документ XPS.
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Поздравляем! Вы успешно добавили прямоугольник в документ XPS с помощью Aspose.Page для .NET.

## Заключение

Aspose.Page для .NET упрощает задачи манипулирования документами, позволяя разработчикам легко создавать и изменять документы XPS. В этом пошаговом руководстве показано, как добавить прямоугольник в документ XPS, обеспечивая прочную основу для дальнейшего изучения.

## Часто задаваемые вопросы

### Вопрос 1. Совместим ли Aspose.Page со всеми приложениями .NET?

О1: Да, Aspose.Page разработан для бесперебойной работы со всеми приложениями .NET.

### Вопрос 2. Где я могу найти документацию по Aspose.Page для .NET?

 A2: документация доступна.[здесь](https://reference.aspose.com/page/net/).

### Вопрос 3: Могу ли я бесплатно попробовать Aspose.Page для .NET перед покупкой?

 A3: Да, вы можете получить бесплатную пробную версию.[здесь](https://releases.aspose.com/).

### Вопрос 4: Как я могу получить временную лицензию на Aspose.Page для .NET?

 А4: Посетите[эта ссылка](https://purchase.aspose.com/temporary-license/) получить временную лицензию.

### Вопрос 5: Где я могу обратиться за поддержкой сообщества или задать вопросы, связанные с Aspose.Page для .NET?

 A5: Посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
