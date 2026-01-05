---
date: 2026-01-05
description: Узнайте, как без усилий преобразовывать XPS‑документы с помощью Aspose.Page
  для .NET. Следуйте нашему пошаговому руководству для бесшовных преобразований.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Как преобразовать XPS с помощью Aspose.Page для .NET
url: /ru/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как преобразовать XPS с помощью Aspose.Page для .NET

## Введение

Добро пожаловать в мир Aspose.Page для .NET, мощной библиотеки, позволяющей без усилий выполнять различные преобразования XPS‑документов. **В этом руководстве вы узнаете, как преобразовать XPS‑документы с помощью Aspose.Page для .NET**, независимо от того, являетесь ли вы опытным разработчиком или только начинаете. Мы пройдём каждый шаг, объясним причины каждого преобразования и дадим практические советы, которые можно применить в реальных проектах.

## Быстрые ответы
- **Что вы можете достичь?** Создавать, перемещать, масштабировать и вращать элементы канвы XPS программно.  
- **Какая библиотека требуется?** Aspose.Page для .NET (последняя версия).  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Поддерживаемые платформы?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базовых преобразований, показанных здесь.

## Что означает «как преобразовать xps»?
Фраза *как преобразовать xps* относится к программному изменению макета, размера и ориентации элементов внутри документа XPS (XML Paper Specification). С помощью Aspose.Page вы можете применять матричные преобразования к канвам, получая точный контроль над позиционированием, масштабированием и вращением без ручного редактирования XML‑структуры XPS.

## Почему использовать Aspose.Page для преобразования XPS?
- **Полная интеграция с .NET** – без проблем работает с Visual Studio, Rider и другими IDE.  
- **Отсутствие внешних зависимостей** – API обрабатывает все низкоуровневые детали XPS за вас.  
- **Широкая поддержка преобразований** – перемещение, масштабирование, вращение и комбинирование нескольких преобразований в одном вызове.  
- **Оптимизированная производительность** – подходит для генерации отчётов, счетов‑фактур или любой печатной графики «на лету».

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- **Библиотека Aspose.Page для .NET** – скачайте и установите её из официальной документации: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Среда разработки** – Visual Studio, Visual Studio Code или любой другой IDE, совместимый с .NET.  
- **Каталог документов** – папка на вашем компьютере, где будут читаться/записываться XPS‑файлы. Замените заполнитель в коде реальным путём.

Теперь, когда всё готово, приступим к коду.

## Импорт пространств имён

Сначала импортируйте пространства имён, которые предоставляют необходимые классы Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Как преобразовать XPS – пошаговое руководство

### Шаг 1: Создать новый XPS‑документ

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Объяснение*: Мы определяем папку, в которой находятся исходные и выходные файлы, затем создаём пустой `XpsDocument`. Этот объект будет канвой для всех последующих преобразований.

### Шаг 2: Создать основную канву

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Почему это важно*: Основная канва служит контейнером для всех остальных канв. Небольшой смещение гарантирует, что содержимое не будет обрезано у края страницы.

### Шаг 3: Создать геометрию пути прямоугольника

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Подсказка*: Строка пути следует стандартному синтаксису XPS (`M` – перемещение, `L` – линия, `Z` – замыкание). Изменяйте координаты, чтобы изменить размер прямоугольника.

### Шаг 4: Добавить заливку для прямоугольников

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Профессиональный совет*: Используйте `CreateColor` с RGB‑значениями, соответствующими палитре вашего бренда.

### Шаг 5: Добавить новую канву без преобразований

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Здесь мы просто размещаем прямоугольник на странице без дополнительных преобразований — полезно как базовый элемент.

### Шаг 6: Добавить новую канву с преобразованием перемещения

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Что происходит?* Первая матрица перемещает прямоугольник вниз на 200 единиц. Последующий вызов `Translate` сдвигает его на 500 единиц вправо, демонстрируя возможность цепочки нескольких перемещений.

### Шаг 7: Добавить новую канву с двойным масштабированием

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Зачем масштабировать?* Масштабирование в 2 раза удваивает ширину и высоту прямоугольника, позволяя создавать более крупные графики без переопределения геометрии.

### Шаг 8: Добавить новую канву с вращением вокруг точки

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Ключевой момент*: `RotateAround` вращает канву вокруг пользовательской точки (здесь (100, 50)), давая точный контроль над точкой опоры вращения.

### Шаг 9: Сохранить полученный XPS‑документ

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

После применения всех преобразований документ сохраняется в `output1.xps`. Откройте файл в любом XPS‑просмотрщике, чтобы увидеть наложенные прямоугольники с их соответствующими перемещениями, масштабированием и вращением.

## Распространённые проблемы и их решение

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| Пустой выходной файл | `dataDir` указывает на несуществующую папку | Убедитесь, что каталог существует, либо используйте абсолютный путь |
| Прямоугольники расположены не так, как ожидалось | Неправильные значения матрицы | Проверьте порядок вызовов `Translate`, `Scale` и `RotateAround` |
| Цвета отображаются неверно | RGB‑значения выходят за диапазон 0‑255 | Используйте корректные байтовые значения для каждого канала |

## Часто задаваемые вопросы

**В: Совместима ли Aspose.Page для .NET со всеми средами разработки .NET?**  
О: Да, она без проблем работает с Visual Studio, Visual Studio Code, Rider и любой IDE, поддерживающей .NET.

**В: Где можно найти дополнительные примеры и подробную документацию API?**  
О: Посетите официальную документацию по ссылке [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**В: Можно ли попробовать Aspose.Page перед покупкой лицензии?**  
О: Конечно. Бесплатная пробная версия доступна здесь: [Aspose.Page Free Trial](https://releases.aspose.com/).

**В: Как получить временную лицензию для тестирования?**  
О: Вы можете запросить её на странице временной лицензии: [Temporary License](https://purchase.aspose.com/temporary-license/).

**В: Где купить полную лицензию?**  
О: Приобретайте напрямую в магазине Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2026-01-05  
**Тестировано с:** Aspose.Page 24.11 для .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}