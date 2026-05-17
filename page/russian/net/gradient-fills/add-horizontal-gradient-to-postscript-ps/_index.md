---
date: 2026-02-25
description: Улучшайте документы PostScript, добавляя прямоугольник с линейным градиентом,
  используя Aspose.Page для .NET. Следуйте нашему пошаговому руководству, чтобы узнать,
  как заполнять текст градиентом и создавать контурный градиент текста.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Добавить прямоугольник с линейным градиентом в PostScript (PS) с помощью Aspose.Page
url: /ru/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить прямоугольник с линейным градиентом в PostScript (PS) с помощью Aspose.Page

## Введение

Добро пожаловать в этот подробный учебник по добавлению **прямоугольника с линейным градиентом** в документы PostScript (PS) с использованием Aspose.Page для .NET. Aspose.Page — мощная библиотека, позволяющая создавать, изменять и рендерить документы в различных форматах, а сегодня мы сосредоточимся на том, как добавить эффектные градиенты в ваши PS‑файлы.

### Быстрые ответы
- **Что делает прямоугольник с линейным градиентом?** Он заполняет прямоугольную область плавным переходом цвета от одной стороны к другой.  
- **Какой API обрабатывает заполнение текста градиентом?** `LinearGradientBrush` в сочетании с `SetPaint` и `FillAndStrokeText`.  
- **Могу ли я обвести текст градиентом?** Да — используйте `SetStroke` с градиентной кистью и вызовите `OutlineText`.  
- **Нужна ли лицензия для продакшн?** Для использования не в режиме оценки требуется коммерческая лицензия Aspose.Page.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Требования

Прежде чем приступить, убедитесь, что у вас есть:

- **Aspose.Page for .NET Library:** Убедитесь, что библиотека подключена к вашему проекту. Вы можете скачать её из [документации Aspose.Page для .NET](https://reference.aspose.com/page/net/).
- **Document Directory:** Создайте папку на диске, куда будет сохраняться сгенерированный PS‑файл, и замените **«Your Document Directory»** в коде на этот путь.

## Импорт пространств имён

Чтобы начать, импортируйте пространства имён, которые дают доступ к классам рисования и специфическим для PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Что такое прямоугольник с линейным градиентом?

**Прямоугольник с линейным градиентом** — это просто прямоугольная форма, внутренность которой окрашена линейным градиентом: цвета плавно переходят вдоль прямой линии, обычно слева направо (горизонтально) или сверху вниз (вертикально). В Aspose.Page это достигается комбинированием `GraphicsPath`, определяющего прямоугольник, и `LinearGradientBrush`, описывающего переход цветов.

## Зачем использовать градиентное заполнение текста и градиент обводки текста?

- **Визуальная привлекательность:** Текст, заполненный градиентом, добавляет глубину и современный стиль в отчёты, счета или рекламные материалы.  
- **Согласованность бренда:** Точно соответствуйте корпоративным цветам, используя ARGB‑значения.  
- **Гибкость:** Одна и та же кисть может использоваться для заполнения фигур, текста и градиентной обводки, уменьшая дублирование кода.

## Шаг 1: Настройка документа

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Шаг 2: Определение градиентного прямоугольника и цветов

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Шаг 3: Установка трансформации для кисти

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Шаг 4: Установка краски и заполнение прямоугольника

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Как применить градиентное заполнение текста

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Использование градиентной обводки текста

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Шаг 7: Закрыть текущую страницу и сохранить документ

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Поздравляем! Вы успешно добавили **прямоугольник с линейным градиентом** в документ PostScript и использовали ту же кисть для **градиентного заполнения текста** и **градиентной обводки текста**.

## Общие случаи использования и советы

- **Заголовки отчётов:** Заполняйте большие блоки текста градиентом, чтобы выделить названия разделов.  
- **Логотипы бренда:** Воссоздавайте формы логотипов с градиентными заливками для единообразного брендинга.  
- **Pro Tip:** Переиспользуйте один экземпляр `LinearGradientBrush` для нескольких вызовов рисования, чтобы цвета оставались идеально согласованными между фигурами и текстом.

## Часто задаваемые вопросы

### Q1: Могу ли я применять градиенты к другим фигурам, кроме прямоугольников?
**A:** Да, градиенты можно применять к любой фигуре, определённой `GraphicsPath`. Просто добавьте круги, полигоны или пользовательские пути перед вызовом `document.Fill(path)`.

### Q2: Как изменить цвета градиента?
**A:** Измените значения `Color.FromArgb` при создании `LinearGradientBrush`. Первый цвет — начало градиента, второй — его конец.

### Q3: Совместим ли Aspose.Page с различными форматами документов?
**A:** Абсолютно. Aspose.Page поддерживает XPS, PS, PDF и несколько других векторных форматов. См. официальную документацию для полного списка.

### Q4: Можно ли использовать Aspose.Page в коммерческих проектах?
**A:** Да, доступна коммерческая лицензия. Подробнее см. страницу покупки: [here](https://purchase.aspose.com/buy).

### Q5: Где найти поддержку сообщества?
**A:** Присоединяйтесь к форуму сообщества Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}