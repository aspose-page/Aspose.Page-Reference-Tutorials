---
title: Добавьте круговой эллипс в PostScript (PS) с помощью Aspose.Page
linktitle: Добавить эллипс круга в PostScript (PS)
second_title: Aspose.Page .NET API
description: Узнайте, как легко добавлять круговые эллипсы в документы PostScript (PS) с помощью Aspose.Page для .NET. Следуйте нашему пошаговому руководству для бесшовной интеграции.
weight: 10
url: /ru/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте круговой эллипс в PostScript (PS) с помощью Aspose.Page

## Введение

Добро пожаловать в это подробное руководство по добавлению круговых эллипсов в документы PostScript (PS) с использованием Aspose.Page для .NET. Aspose.Page — это мощная библиотека, которая позволяет разработчикам беспрепятственно работать с PostScript и другими форматами документов. В этом руководстве мы покажем вам процесс простого включения круговых эллипсов в ваши документы PS.

## Предварительные условия

Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:

1.  Библиотека Aspose.Page для .NET: загрузите и установите библиотеку Aspose.Page для .NET с сайта[здесь](https://releases.aspose.com/page/net/).

2. Среда разработки: убедитесь, что на вашем компьютере установлена работающая среда разработки .NET.

Теперь давайте начнем с пошагового руководства.

## Импортировать пространства имен

На первом этапе вам необходимо импортировать необходимые пространства имен, чтобы сделать функциональность Aspose.Page доступной в вашем коде.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Теперь давайте разобьем приведенный пример на несколько шагов, которые помогут вам добавить круговые эллипсы в документ PostScript.

## Шаг 1. Установите каталог документов

```csharp
// ExStart:1
// Путь к каталогу документов.
string dataDir = "Your Document Directory";
```

Обязательно замените «Каталог ваших документов» фактическим путем к каталогу ваших документов.

## Шаг 2. Создайте выходной поток для документа PostScript

```csharp
//Создать выходной поток для документа PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Здесь создается FileStream для записи документа PostScript, а файловый режим устанавливается для создания нового файла.

## Шаг 3. Создайте параметры сохранения и документ PS.

```csharp
//Создайте варианты сохранения с размером А4.
PsSaveOptions options = new PsSaveOptions();

// Создать новый одностраничный документ PS
PsDocument document = new PsDocument(outPsStream, options, false);
```

Этот шаг включает в себя создание параметров сохранения формата A4 и инициализацию нового одностраничного документа PS.

## Шаг 4. Создайте графический путь для первого эллипса

```csharp
//Создайте графический путь из первого эллипса
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Для первого эллипса создается графический путь с указанием его положения и размеров.

## Шаг 5: Установите краску и заполните эллипс

```csharp
//Установить краску
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Заполните эллипс
document.Fill(path);
```

Здесь краска задана, и первый эллипс заполняется указанным цветом.

## Шаг 6. Создайте графический путь для второго эллипса

```csharp
//Создайте графический путь из второго эллипса
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Аналогичным образом создается графический путь для второго эллипса, определяющий его положение и размеры.

## Шаг 7: Установите обводку и нарисуйте эллипс

```csharp
//Установить ход
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Обводка (обводка) эллипса
document.Draw(path);
```

На этом этапе задается обводка, а второй эллипс обводится указанным цветом и толщиной линии.

## Шаг 8. Закройте текущую страницу и сохраните документ.

```csharp
//Закрыть текущую страницу
document.ClosePage();

//Сохраните документ
document.Save();
```

Наконец, текущая страница закрывается, и весь документ сохраняется, завершая процесс.

## Заключение

Поздравляем! Вы успешно научились добавлять круговые эллипсы в документы PostScript с помощью Aspose.Page для .NET. В этом руководстве представлено подробное пошаговое руководство, которое поможет вам легко интегрировать эту функцию в ваши проекты.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Page для .NET с другими форматами документов?

 A1: Aspose.Page в первую очередь ориентирован на PostScript, но Aspose предоставляет и другие библиотеки для различных форматов документов. Проверить[Aspose документация](https://reference.aspose.com/page/net/) Больше подробностей.

### Вопрос 2. Где я могу найти дополнительную поддержку и обсуждения в сообществе?

 A2: Посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для общественных обсуждений и поддержки.

### Вопрос 3. Существует ли бесплатная пробная версия Aspose.Page для .NET?

 A3: Да, вы можете получить доступ к[бесплатная пробная версия](https://releases.aspose.com/)чтобы изучить возможности Aspose.Page для .NET.

### Вопрос 4: Как я могу получить временную лицензию для Aspose.Page?

 A4: Получите временную лицензию[здесь](https://purchase.aspose.com/temporary-license/) для целей тестирования и оценки.

### Вопрос 5: Где я могу приобрести Aspose.Page для .NET?

 A5: Приобретите Aspose.Page для .NET на сайте[страница покупки](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
