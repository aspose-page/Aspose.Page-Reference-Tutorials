---
date: 2026-01-12
description: Узнайте, как сохранять файлы PostScript и создавать документы PostScript
  с помощью Aspose.Page для .NET, а также применять множественные преобразования для
  динамической графики.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Сохранить файл PostScript с помощью преобразований Aspose.Page (.NET)
url: /ru/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохранить файл PostScript с помощью трансформаций Aspose.Page (.NET)

## Введение

В этом руководстве вы узнаете, как **сохранить файл PostScript**, работая с Aspose.Page для .NET. Мы пройдём процесс создания документа PostScript, применения нескольких трансформаций, таких как перемещение, масштабирование, вращение и сдвиг, а затем сохраним результат. К концу вы будете уверенно создавать динамическую графику программно и точно знать, где разместить каждую трансформацию в графическом состоянии.

## Быстрые ответы
- **Что я могу создать?** Полнофункциональный документ PostScript с трансформированной графикой.  
- **Какая библиотека требуется?** Aspose.Page for .NET (доступна для скачивания с официального сайта).  
- **Как сохранить файл?** Используйте `PsDocument.Save()` после настройки графических состояний.  
- **Можно ли применить несколько трансформаций?** Да — объединяйте их с помощью `Transform` или последовательных вызовов.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшн требуется коммерческая лицензия.

## Что представляет собой операция «сохранить файл postscript»?

Сохранение файла PostScript означает запись построенных в памяти команд рисования в файл с расширением `.ps` на диске. Затем файл может быть обработан любым интерпретатором PostScript, принтером или просмотрщиком.

## Почему стоит использовать Aspose.Page for .NET для создания документа postscript?

Aspose.Page предоставляет высокоуровневый, независимый от устройства API, который абстрагирует низкоуровневый синтаксис PostScript. Вы получаете:

- Сильно типизированные объекты C# для путей, кистей и трансформаций.  
- Автоматическое управление стеком графических состояний (save/restore).  
- Полную поддержку сложных матриц трансформаций без ручных вычислений.  

## Требования

Перед началом убедитесь, что у вас есть:

- **Aspose.Page for .NET** библиотека, интегрированная в ваш проект. Скачайте её по [download link](https://releases.aspose.com/page/net/).  
- Папка с правом записи, куда будет сохранён сгенерированный файл `.ps`. Замените путь‑заполнитель в коде на ваш реальный каталог.

## Импорт пространств имён

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Теперь давайте рассмотрим каждый шаг трансформации.

## Без трансформаций

### Шаг 1: Создать поток вывода

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Этот фрагмент кода создаёт **документ PostScript** с одним оранжевым прямоугольником и **сохраняет файл PostScript** без применения каких‑либо трансформаций.

## Перемещение

### Шаг 1: Сохранить состояние графики

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Сохранение состояния графики позволяет вернуться к нему после перемещения объектов.

### Шаг 2: Переместить состояние графики

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Перемещение смещает всё, что будет нарисовано после этого вызова, на 250 единиц вправо.

### Шаг 3: Заполнить прямоугольник с трансформацией перемещения

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Теперь синий прямоугольник появляется на 250 пунктов правее оранжевого.

### Шаг 4: Восстановить состояние графики

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Восстановление возвращает систему координат в исходное положение, поэтому последующее рисование не будет затронуто перемещением.

## Масштабирование

> *Вы можете следовать той же схеме — сохранить состояние, применить `Scale`, нарисовать, затем восстановить.*  
> **Pro tip:** Используйте неравномерное масштабирование (`Scale(sx, sy)`), чтобы растянуть объекты только в одном направлении.

## Поворот

> *Вращайте вокруг начала координат или пользовательской точки опоры с помощью `Rotate(angle)`.*
> **Pro tip:** Сначала выполните `Translate`, а затем вращение, чтобы вращать вокруг конкретной точки.

## Сдвиг

> *Трансформации сдвига (`Shear(shx, shy)`) наклоняют формы, полезно для создания эффекта курсивного текста.*  

## Сложные трансформации

> *Для продвинутых сценариев создайте пользовательскую `Matrix` и передайте её в `Transform(matrix)`.*
> Здесь вы **применяете несколько трансформаций** за один шаг.

## Заключение

Вы узнали, как **сохранить файл PostScript**, **создать документ PostScript** и **применить несколько трансформаций** с помощью Aspose.Page for .NET. Экспериментируйте с различными порядками трансформаций, комбинируйте их и наблюдайте, как меняется графика.

## Часто задаваемые вопросы

**Q: Как применить несколько трансформаций к одному объекту?**  
A: Используйте метод `Transform` с пользовательской `Matrix`, объединяющей перемещение, масштабирование, вращение или сдвиг в нужном порядке.

**Q: Можно ли предварительно просмотреть трансформации перед сохранением документа?**  
A: Да — отрендерите `PsDocument` в изображение или используйте просмотрщик PostScript для проверки вывода перед вызовом `Save()`.

**Q: Возможно ли применять трансформации к отдельным элементам документа?**  
A: Конечно. Сохраните состояние графики перед рисованием элемента, примените нужную трансформацию, нарисуйте, затем восстановите состояние.

**Q: Есть ли особенности производительности при работе со сложными трансформациями?**  
A: Сложные матрицы увеличивают нагрузку на CPU. Делайте трансформации как можно проще и переиспользуйте сохранённые состояния при рисовании множества похожих объектов.

**Q: Как получить поддержку или помощь по вопросам, связанным с Aspose.Page?**  
A: Посетите [Aspose.Page forum](https://forum.aspose.com/c/page/39) для получения помощи от сообщества или свяжитесь напрямую со службой поддержки Aspose.

**Последнее обновление:** 2026-01-12  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}