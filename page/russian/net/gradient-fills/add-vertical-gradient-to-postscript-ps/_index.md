---
date: 2026-02-25
description: Узнайте, как использовать линейную градиентную кисть в C# для добавления
  градиента в PS‑файлы и заполнения прямоугольника градиентом с помощью Aspose.Page
  для .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Linear Gradient Brush – Добавить вертикальный градиент в PostScript (PS)
  с помощью Aspose.Page
url: /ru/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Добавление вертикального градиента в PostScript (PS) с Aspose.Page

## Введение

В области манипуляций с документами и их создания **Aspose.Page for .NET** выделяется как мощный инструмент для разработчиков. В этом руководстве вы узнаете, как **добавить градиент в PS** файлы, используя **C# linear gradient brush** для **заполнения прямоугольника градиентом**. К концу этого урока у вас будет чёткое пошаговое понимание необходимого кода и того, почему эта техника создаёт плавный вертикальный градиент в вашем выводе PostScript.

## Быстрые ответы
- **Что делает C# linear gradient brush?** Он создаёт плавный переход между несколькими цветами по всей форме.
- **Можно ли использовать это с любой версией .NET?** Да, Aspose.Page поддерживает .NET Framework 4.5+ и .NET Core/5+.
- **Нужна ли лицензия для продакшн?** Для не‑оценочных сборок требуется коммерческая лицензия.
- **Градиент действительно вертикальный?** Кисть вращается на 90°, обеспечивая вертикальное направление.
- **Где сохраняется вывод?** По пути, указанному в `dataDir` (например, `VerticalGradient_outPS.ps`).

## Что такое C# Linear Gradient Brush?
**C# linear gradient brush** — это объект GDI+ (`LinearGradientBrush`), который рисует линейный переход цветов между заданными точками. В сочетании с API рисования Aspose.Page он позволяет напрямую рендерить сложные градиенты в документ PostScript (PS).

## Почему использовать Linear Gradient Brush для PostScript?
- **Высококачественный вывод:** Градиенты рендерятся на уровне принтера, сохраняют точность.
- **Полный контроль:** Вы можете задавать пользовательские цветовые остановки, вращение и масштабирование.
- **Повторно используемый код:** Та же логика кисти работает для PDF, SVG и других форматов, поддерживаемых Aspose.Page.

## Предварительные требования

Прежде чем погрузиться в урок, убедитесь, что у вас есть следующее:

- Aspose.Page for .NET: Убедитесь, что библиотека Aspose.Page установлена. Необходимые ресурсы и документацию можно найти [здесь](https://reference.aspose.com/page/net/).
- Среда разработки: Настройте подходящую среду разработки, включая интегрированную среду разработки (IDE) для .NET.
- Базовые знания: Ознакомитесь с основами разработки на .NET, включая работу с потоками, графическими путями и управлением цветом.

## Импорт пространств имён

В вашем C# проекте включите необходимые пространства имён в начале файла кода:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Шаг 1: Настройка каталога документа

Начните с указания пути к каталогу вашего документа. Это место, где будет сохраняться ваш PS‑документ.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Создание выходного потока для PostScript документа

Создайте выходной поток для PostScript документа, используя класс `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Шаг 3: Создание параметров сохранения и PS‑документа

Создайте параметры сохранения с размером A4 и инициализируйте новый одностраничный PS‑документ.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Шаг 4: Определение размеров прямоугольника

Укажите размеры и позицию прямоугольника, в котором будет применён вертикальный градиент.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Шаг 5: Создание графического пути

Создайте графический путь из заданного прямоугольника.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Шаг 6: Определение интерполяционных цветов

Создайте массив интерполяционных цветов и позиций для градиента.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Шаг 7: Создание Linear Gradient Brush

Создайте линейную кисть градиента, используя прямоугольник как границы, начальный и конечный цвета.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Шаг 8: Установка трансформации кисти

Установите трансформацию для кисти, гарантируя, что компоненты масштабирования X и Y соответствуют ширине и высоте прямоугольника.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Шаг 9: Установка краски и заполнение прямоугольника

Установите краску для документа и **заполните прямоугольник градиентом**, используя ранее определённый путь.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Шаг 10: Закрытие текущей страницы и сохранение документа

Закройте текущую страницу и сохраните PostScript документ.

```csharp
document.ClosePage();
document.Save();
```

Поздравляем! Вы успешно **добавили вертикальный градиент в PostScript документ** с помощью **C# linear gradient brush** в Aspose.Page for .NET. Экспериментируйте с различными параметрами и цветами, чтобы достичь разнообразных визуальных эффектов в ваших документах.

## Распространённые проблемы и решения

| Проблема | Почему происходит | Как исправить |
|----------|-------------------|---------------|
| Градиент выглядит горизонтальным | Не применено вращение кисти | Убедитесь, что `brushTransform.Rotate(90);` вызывается до назначения `brush.Transform`. |
| Цвета выглядят вымытыми | Низкое разрешение выходного потока | Используйте `PsSaveOptions` с более высоким разрешением или увеличьте размер документа. |
| Файл вывода пустой | Поток не был сброшен | Проверьте, что `document.Save();` вызывается вне блока `using`. |

## Часто задаваемые вопросы

**Q1: Можно ли применить несколько градиентов к разным областям одного документа?**  
A: Да, можно. Просто повторите шаги для каждой области с её конкретными размерами и схемой цветов.

**Q2: Как интегрировать этот код в существующий .NET проект?**  
A: Скопируйте и вставьте код в файл проекта и убедитесь, что библиотека Aspose.Page подключена.

**Q3: Есть ли другие типы градиентов в Aspose.Page для .NET?**  
A: Aspose.Page поддерживает различные типы градиентов, включая радиальные и градиенты по пути. Обратитесь к документации для получения подробностей.

**Q4: Можно ли использовать Aspose.Page в коммерческих проектах?**  
A: Да, можно. Посетите [здесь](https://purchase.aspose.com/buy), чтобы ознакомиться с вариантами лицензирования.

**Q5: Есть ли сообщество или форум по Aspose.Page, где можно получить помощь?**  
A: Конечно! Перейдите на [форум Aspose.Page](https://forum.aspose.com/c/page/39), чтобы связаться с другими разработчиками и получить поддержку.

---

**Последнее обновление:** 2026-02-25  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}