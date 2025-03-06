---
title: Добавьте прямоугольник в PostScript (PS) с помощью Aspose.Page для .NET
linktitle: Добавить прямоугольник в PostScript (PS)
second_title: Aspose.Page .NET API
description: Улучшите создание документов в .NET с помощью Aspose.Page. Научитесь шаг за шагом добавлять прямоугольники в файлы PostScript (PS).
weight: 12
url: /ru/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте прямоугольник в PostScript (PS) с помощью Aspose.Page для .NET

## Введение

Если вы хотите расширить свои возможности создания документов в .NET, Aspose.Page предоставляет мощное решение для обработки документов PostScript. В этом уроке мы проведем вас через процесс добавления прямоугольников в документ PostScript с помощью Aspose.Page для .NET.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

-  Библиотека Aspose.Page для .NET: загрузите и установите библиотеку Aspose.Page для .NET с сайта[здесь](https://releases.aspose.com/page/net/).

- Среда разработки: убедитесь, что на вашем компьютере установлена среда разработки .NET.

## Импортировать пространства имен

Прежде чем приступить к кодированию, обязательно импортируйте необходимые пространства имен для доступа к необходимым классам и методам:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Теперь давайте разобьем пример на несколько этапов:

## Шаг 1. Настройте каталог документов

```csharp
// ExStart:1
// Путь к каталогу документов.
string dataDir = "Your Document Directory";
```

На этом этапе замените «Каталог вашего документа» на путь, по которому вы хотите сохранить документ PostScript.

## Шаг 2. Создайте выходной поток для документа PostScript

```csharp
//Создать выходной поток для документа PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Здесь мы создаем выходной поток для документа PostScript и указываем имя файла («AddRectangle_outPS.ps»). Настройте имя и местоположение файла в соответствии с вашими предпочтениями.

## Шаг 3. Установите параметры сохранения и создайте документ PS

```csharp
//Создайте варианты сохранения с размером А4.
PsSaveOptions options = new PsSaveOptions();

// Создать новый одностраничный документ PS
PsDocument document = new PsDocument(outPsStream, options, false);
```

Задайте параметры сохранения, указав желаемый размер страницы (в данном случае A4). Затем создайте новый одностраничный документ PostScript.

## Шаг 4: Добавьте прямоугольник и заливку

```csharp
//Создайте графический путь из первого прямоугольника
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Установить краску
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Заполните прямоугольник
document.Fill(path);
```

Здесь мы создаем графический путь, представляющий первый прямоугольник, устанавливаем цвет краски (в данном случае оранжевый) и заливаем прямоугольник.

## Шаг 5: Добавьте еще один прямоугольник и обводку

```csharp
//Создайте графический путь из второго прямоугольника
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Установить ход
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Обводка (обводка) прямоугольника
document.Draw(path);
```

Аналогично предыдущему шагу мы создаем графический путь для второго прямоугольника, устанавливаем цвет обводки (красный с толщиной 3) и обводим прямоугольник.

## Шаг 6. Закройте страницу и сохраните документ.

```csharp
//Закрыть текущую страницу
document.ClosePage();

//Сохраните документ
document.Save();
```

Наконец, закройте текущую страницу и сохраните весь документ.

## Заключение

Поздравляем! Вы успешно добавили прямоугольники в документ PostScript, используя Aspose.Page для .NET. В этом руководстве описаны основные шаги: от настройки среды разработки до сохранения окончательного документа.

## Часто задаваемые вопросы

### В1: Могу ли я настроить цвета прямоугольников?

A1: Да, вы можете настроить цвета, отрегулировав параметры в`SolidBrush` и`Pen` занятия.

### Вопрос 2: Совместим ли Aspose.Page с другими форматами документов?

О2: Да, Aspose.Page поддерживает различные форматы документов, включая XPS и PostScript.

### Вопрос 3: Как добавить текст в документ?

 A3: Вы можете использовать`TextFragment` класс в Aspose.Page, чтобы добавить текст в документ.

### Вопрос 4. Где я могу найти дополнительные примеры и документацию?

 A4: Изучите документацию[здесь](https://reference.aspose.com/page/net/) и посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.

### В5: Могу ли я попробовать Aspose.Page перед покупкой?

 A5: Да, вы можете получить бесплатную пробную версию.[здесь](https://releases.aspose.com/) , а для расширенного использования рассмотрите[временная лицензия](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
