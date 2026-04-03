---
date: 2026-04-03
description: Узнайте, как добавить прозрачный прямоугольник и применить кисть Grid
  Visual Brush в .NET с помощью Aspose.Page для создания впечатляющих XPS‑документов.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Применить кисть визуальной сетки
second_title: Aspose.Page .NET API
title: Добавить прозрачный прямоугольник с помощью Grid Visual Brush (.NET)
url: /ru/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить прозрачный прямоугольник с использованием Grid Visual Brush (.NET)

## Введение

Если вы хотите **добавить прозрачный прямоугольник** в документ XPS, одновременно применив стильный Grid Visual Brush, вы попали по адресу. В этом руководстве мы пошагово рассмотрим необходимые действия с Aspose.Page for .NET, чтобы вы могли создавать визуально насыщенные документы, выделяющиеся. К концу у вас будет полностью готовый, исполняемый пример, демонстрирующий обе техники в едином, простом для выполнения рабочем процессе.

## Быстрые ответы
- **Что делает прозрачный прямоугольник?** Он добавляет полупрозрачный наложение, позволяющее видеть содержимое фона.  
- **Какой API создает кисть?** `XpsDocument.CreateVisualBrush` создает Grid Visual Brush.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового примера.

## Что такое прозрачный прямоугольник в XPS?

Прозрачный прямоугольник — это просто фигура, у которой цвет заливки содержит альфа‑компонент меньше 1.0, что позволяет частично видеть графику, находящуюся под ним. Это идеально подходит для выделения секций без полного затемнения фона.

## Почему использовать Grid Visual Brush?

Grid Visual Brush позволяет заполнять большую область небольшим векторным изображением, создавая узоры, такие как сетки, штриховки или пользовательские текстуры. Сочетание его с прозрачным прямоугольником дает слоистые визуальные эффекты, которые одновременно легки и независимы от разрешения.

## Предварительные требования

- **Aspose.Page for .NET** – вы можете скачать его [здесь](https://releases.aspose.com/page/net/).
- Среда разработки .NET (Visual Studio, VS Code или любой другой предпочитаемый IDE).
- Папка, в которой будут сохраняться сгенерированные файлы XPS.

## Импорт пространств имён

В вашем C#‑файле импортируйте необходимые пространства имён:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Теперь давайте разобьём решение на чёткие, пронумерованные шаги.

## Шаг 1: Инициализация XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Мы начинаем с создания экземпляра `XpsDocument`, который будет содержать все последующие операции рисования.

## Шаг 2: Создание магентовой геометрии сетки

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Эта геометрия определяет контур сетки, которую будет заполнять визуальная кисть.

## Шаг 3: Проектирование магентовой VisualBrush сетки

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Здесь мы рисуем небольшую магентовую плитку, которая будет повторяться по всей сетке.

## Шаг 4: Применение VisualBrush к сетке

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

Вызов `CreateVisualBrush` связывает магентовую плитку с геометрией сетки и включает режим повторения.

## Шаг 5: Добавление сетки на Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Мы размещаем повторяющуюся сетку на холсте и применяем трансформацию переноса, чтобы она оказалась в нужном месте.

## Шаг 6: Добавление прозрачного прямоугольника

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

На этом этапе мы **добавляем прозрачный прямоугольник** (красную форму с `Opacity = 0.7f`). Отрегулируйте значение непрозрачности, чтобы контролировать степень просвечиваемости прямоугольника.

## Шаг 7: Сохранение документа

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Файл XPS записывается в папку, указанную вами ранее.

## Распространённые сценарии использования

- **Выделение в отчётах:** Наложите полупрозрачный прямоугольник, чтобы подчеркнуть график или таблицу.  
- **Эффекты водяного знака:** Сочетайте повторяющуюся сетку с прозрачным наложением для тонкого брендинга.  
- **Интерактивные PDF/XPS:** Используйте узор как фон для полей формы, сохраняя читаемость интерфейса.

## Советы по устранению неполадок

- **Непрозрачность не видна?** Убедитесь, что ваш просмотрщик поддерживает прозрачность XPS; некоторые старые просмотрщики могут игнорировать свойство `Opacity`.  
- **Неправильный размер плитки?** Проверьте, что исходный прямоугольник (`new RectangleF(0f, 0f, 10f, 10f)`) соответствует размерам векторной плитки.  
- **Файл не сохраняется?** Дважды проверьте, что `dataDir` указывает на существующую, доступную для записи директорию.

## Часто задаваемые вопросы

**В: Могу ли я использовать Aspose.Page for .NET как в веб, так и в настольных приложениях?**  
О: Да, библиотека работает со всеми типами .NET‑приложений.

**В: Доступна ли пробная версия перед покупкой?**  
О: Конечно, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

**В: Где я могу найти дополнительную поддержку или обсуждения сообщества?**  
О: Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для получения помощи от сообщества и инженеров Aspose.

**В: Как получить временную лицензию для оценки?**  
О: Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

**В: Какая еще документация доступна для Aspose.Page for .NET?**  
О: Изучите полную документацию [здесь](https://reference.aspose.com/page/net/).

---

**Последнее обновление:** 2026-04-03  
**Тестировано с:** Aspose.Page 24.12 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}