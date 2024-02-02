---
title: Измените размер изображений EPS с помощью Aspose.Page для .NET
linktitle: Изменение размера изображений EPS
second_title: Aspose.Page .NET API
description: Изучите простой процесс изменения размера изображений EPS в .NET с помощью Aspose.Page. Достигайте точности в пунктах, дюймах, миллиметрах и процентах без особых усилий.
type: docs
weight: 11
url: /ru/net/image-manipulation/resize-eps-images/
---
## Введение

Вы хотите легко изменить размер изображений EPS с помощью Aspose.Page для .NET? Это руководство представляет собой полное руководство по легкому управлению размером изображений EPS в различных единицах измерения, таких как пункты, дюймы, миллиметры и проценты. Aspose.Page для .NET предоставляет мощный набор инструментов, и в этом руководстве мы шаг за шагом проведем вас через этот процесс.

## Предварительные условия

Прежде чем погрузиться в магию изменения размера, убедитесь, что у вас есть следующие предварительные условия:

-  Библиотека Aspose.Page для .NET: убедитесь, что у вас установлена библиотека Aspose.Page для .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/page/net/).

- Каталог документов: создайте каталог, в котором вы будете хранить входной файл EPS и выходные файлы с измененным размером.

Теперь, когда у вас все настроено, приступим к импорту необходимых пространств имен и углубимся в пошаговое руководство.

## Импортировать пространства имен

В вашем проекте .NET начните с импорта необходимых пространств имен для работы с Aspose.Page. Добавьте следующий код в начало вашего файла:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Шаг 1. Изменение размера в пунктах

Начнем с изменения размера изображения EPS в пунктах. Баллы — стандартная единица измерения в полиграфии.

```csharp
public static void ResizeInPoints()
{
    // Ваш каталог документов
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Шаг 2. Изменение размера в дюймах

Теперь давайте изменим размер изображения EPS в дюймах — общепринятой единице измерения, используемой в графическом дизайне.

```csharp
public static void ResizeInInches()
{
    // Ваш каталог документов
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Шаг 3. Изменение размера в миллиметрах

Теперь давайте изменим размер изображения EPS в миллиметрах, еще одной широко используемой единице измерения в дизайне и печати.

```csharp
public static void ResizeInMillimeters()
{
    // Ваш каталог документов
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Шаг 4. Изменение размера в процентах

Наконец, давайте изменим размер изображения EPS, используя проценты, что обеспечит гибкий подход к настройке размера изображения.

```csharp
public static void ResizeInPercents()
{
    // Ваш каталог документов
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Не стесняйтесь интегрировать эти методы в свой проект, и вы сможете легко изменять размер изображений EPS. Поэкспериментируйте с различными единицами измерения, чтобы добиться желаемых размеров.

## Заключение

Поздравляем! Вы овладели искусством изменения размера изображений EPS с помощью Aspose.Page для .NET. Эта мощная библиотека открывает мир возможностей для работы с векторной графикой. Независимо от того, разрабатываете ли вы дизайн для печати или цифровых носителей, Aspose.Page дает вам возможность добиться точных и индивидуальных результатов.

## Часто задаваемые вопросы

### Вопрос 1. Могу ли я изменить размер нескольких изображений EPS одновременно?

О1: Да, вы можете просмотреть коллекцию файлов EPS, соответствующим образом применяя методы изменения размера.

### Вопрос 2: Совместим ли Aspose.Page с другими форматами изображений?

A2: Aspose.Page в первую очередь ориентирован на форматы PostScript и EPS. Для других форматов изображений рассмотрите возможность использования Aspose.Imaging.

### Вопрос 3. Есть ли какие-либо аспекты лицензирования коммерческих проектов?

 О3: Да, убедитесь, что у вас есть действующая лицензия. Посещать[здесь](https://purchase.aspose.com/buy) для получения подробной информации о лицензировании.

### Вопрос 4: Могу ли я попробовать Aspose.Page перед покупкой?

 А4: Абсолютно! Вы можете получить бесплатную пробную версию[здесь](https://releases.aspose.com/).

### В5: Где я могу получить дополнительную помощь или обсудить проблемы?

 A5: Посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) чтобы связаться с сообществом и получить помощь.