---
date: 2026-01-05
description: Узнайте, как добавить путь отсечения в PostScript с помощью Aspose.Page
  для .NET — пошаговое руководство с техникой установки кисти и рисования пунктирного
  прямоугольника.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Добавить обрезающий путь в PS с Aspose.Page для .NET
url: /ru/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавление обрезающего пути в PS с помощью Aspose.Page для .NET

## Введение

В этом полном руководстве вы узнаете, как **добавить обрезающий путь** к документу PostScript (PS) с помощью Aspose.Page для .NET. Мы пройдем каждый шаг, покажем, как **установить кисть рисования**, и продемонстрируем, как **нарисовать пунктирный прямоугольник** вокруг обрезанного содержимого. К концу вы получите полностью функционирующий PS‑файл, иллюстрирующий обрезку по форме, делая вашу графику более динамичной и профессиональной.

## Быстрые ответы
- **Что делает «добавление обрезающего пути»?** Оно ограничивает операции рисования определённой формой, скрывая всё, что находится за её пределами.  
- **Какая библиотека обрабатывает обрезку в .NET?** Aspose.Page для .NET предоставляет богатый API для работы с PS/EPS.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Можно ли изменить цвет кисти?** Да, используйте `SetPaint` с любой `SolidBrush` или градиентом по вашему выбору.  
- **Можно ли нарисовать пунктирный прямоугольник?** Конечно – создайте `Pen` с `DashStyle.Dash` и используйте `Draw`.  

## Что такое обрезающий путь в PostScript?
Обрезающий путь определяет видимую область последующих команд рисования. Всё, что нарисовано за пределами пути, игнорируется, позволяя создавать сложные маскированные графики без изменения исходного содержимого.

## Почему стоит использовать Aspose.Page для обрезки?
- **Без внешних зависимостей** – чистая .NET‑библиотека.  
- **Полный контроль** над состоянием графики (save/restore, translate, rotate).  
- **Богатый набор примитивов рисования** таких как `SetPaint`, `Clip` и `Draw` с настраиваемыми перьями и кистями.  

## Предварительные требования

- Базовые знания программирования на C#.  
- Установленная библиотека Aspose.Page для .NET – её можно скачать [здесь](https://releases.aspose.com/page/net/).  
- Visual Studio или любой другой предпочтительный .NET IDE.  

## Импорт пространств имён

Сначала импортируйте пространства имён, необходимые для работы с графикой:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Теперь разберём пример на чётко обозначенные шаги.

### Шаг 1: Установка каталога документа

Определите папку, где будут находиться исходные и выходные файлы.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Шаг 2: Создание потока вывода для документа PostScript

Создайте поток записи, который будет содержать сгенерированный PS‑файл.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Шаг 3: Создание параметров сохранения

Создайте экземпляр `PsSaveOptions` с настройками по умолчанию. При необходимости их можно будет изменить позже.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Шаг 4: Создание нового 1‑страничного PS‑документа

Инициализируйте объект `PsDocument`, представляющий ваш PS‑файл.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Шаг 5: Создание графического пути из прямоугольника

Мы будем использовать прямоугольник как базовую форму, которую позже обрежем.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Шаг 6: Обрезка по форме

Здесь мы **добавляем обрезающий путь** с помощью круга, **устанавливаем кисть** синего цвета и заполняем прямоугольник внутри обрезанной области.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Шаг 7: Смещение графического состояния верхнего уровня и рисование пунктирного прямоугольника

После восстановления предыдущего состояния мы снова перемещаем графический курсор, **рисуем пунктирный прямоугольник** и применяем синюю обводку.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Шаг 8: Закрытие и сохранение документа

Завершите страницу и запишите PS‑файл на диск.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Теперь вы успешно **добавили обрезающий путь**, задали пользовательскую кисть и нарисовали пунктирный прямоугольник вокруг графики с помощью Aspose.Page для .NET.

## Распространённые проблемы и решения

- **Обрезка не видна:** Убедитесь, что вызвали `WriteGraphicsSave()` перед трансляцией и `WriteGraphicsRestore()` после заполнения.  
- **Неправильные цвета:** Проверьте, что `SetPaint` вызывается после `Clip` и перед `Fill`.  
- **Пунктирные линии выглядят сплошными:** Убедитесь, что у `Pen` свойство `DashStyle` установлено в `DashStyle.Dash` перед `SetStroke`.  

## Часто задаваемые вопросы

### Q1: Можно ли использовать Aspose.Page для .NET с другими языками программирования?
A: Aspose.Page в основном предназначен для приложений .NET. Тем не менее, Aspose предоставляет аналогичные библиотеки для других языков программирования.

### Q2: Где я могу найти дополнительные примеры и документацию по Aspose.Page для .NET?
A: Вы можете изучить больше примеров и подробную документацию на странице [Aspose.Page documentation](https://reference.aspose.com/page/net/).

### Q3: Есть ли бесплатная пробная версия Aspose.Page для .NET?
A: Да, бесплатную пробную версию Aspose.Page для .NET можно получить [здесь](https://releases.aspose.com/).

### Q4: Как получить временную лицензию для Aspose.Page для .NET?
A: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### Q5: Где я могу получить поддержку или обсудить вопросы, связанные с Aspose.Page?
A: Посетите [форумы Aspose.Page](https://forum.aspose.com/c/page/39) для общения с сообществом и получения поддержки.

---

**Последнее обновление:** 2026-01-05  
**Тестировано с:** Aspose.Page 24.11 для .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}