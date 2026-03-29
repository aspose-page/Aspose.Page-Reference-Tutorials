---
date: 2026-03-29
description: Узнайте, как использовать линейную градиентную кисть в C# для создания
  псевдопрозрачности в PostScript с помощью Aspose.Page для .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Линейный градиентный кисть C# для псевдо‑прозрачности в PS
url: /ru/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Кисть линейного градиента C# для псевдо‑прозрачности в PostScript (PS)

## Введение

Если вам нужно добавить тонкий эффект просвечивания в ваши файлы PostScript (PS), **кисть линейного градиента C#** — идеальный инструмент. Aspose.Page для .NET упрощает рисование прямоугольников с непрозрачными и полупрозрачными градиентными заливками, придавая документам современный, многослойный вид. В этом руководстве мы подробно пройдем все шаги, необходимые для создания псевдо‑прозрачности с помощью кисти линейного градиента в C#.

## Быстрые ответы
- **Какая библиотека предоставляет кисть линейного градиента?** Aspose.Page для .NET
- **Какой графический класс создает градиент?** `LinearGradientBrush`
- **Можно ли управлять непрозрачностью для каждого цвета?** Да, используя `Color.FromArgb(alpha, …)`
- **Нужна ли лицензия для продакшн?** Требуется действующая лицензия Aspose.Page
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Что такое кисть линейного градиента C#?

`LinearGradientBrush` — объект GDI+, который рисует плавный переход между двумя цветами вдоль прямой линии. Указывая альфа‑канал (0‑255) для каждого цвета, можно создавать полупрозрачные градиенты — именно то, что нужно для псевдо‑прозрачности в PostScript.

## Почему использовать кисть линейного градиента C# для псевдо‑прозрачности?

- **Тонкая настройка непрозрачности:** Регулируйте альфа‑канал каждого цвета для достижения нужного уровня просвечивания.  
- **Независимая от устройства отрисовка:** Кисть работает одинаково в экране, PDF, EPS и PS.  
- **Простой API:** Несколько строк кода на C# создают профессиональные визуальные эффекты.

## Предварительные требования

Перед тем как приступить к коду, убедитесь, что у вас есть:

- Установленный Aspose.Page для .NET. Скачать можно из [документации Aspose.Page](https://reference.aspose.com/page/net/).
- Папка с правом записи, куда будет сохранён сгенерированный документ PostScript.

Теперь, когда инструменты готовы, начнём создавать псевдо‑прозрачные прямоугольники.

## Импорт пространств имён

Перед началом импортируйте пространства имён, содержащие необходимые классы:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Шаг 1: Создание выходного потока для документа PostScript

Создаём файловый поток, который будет хранить полученный PS‑файл, затем инициализируем `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Шаг 2: Создание прямоугольника с **непрозрачной** градиентной заливкой

Здесь мы создаём `LinearGradientBrush` с полностью непрозрачными цветами (alpha = 255). Этот прямоугольник будет служить фоновым слоем.

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Шаг 3: Создание прямоугольника с **полупрозрачной** градиентной заливкой

Теперь используем **кисть линейного градиента C#**, где значения альфа меньше 255 (например, 150 и 50). Это делает прямоугольник частично просвечивающим, достигая эффекта псевдо‑прозрачности.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Шаг 4: Закрытие страницы и сохранение документа

В конце закрываем страницу и записываем PS‑файл на диск.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Следуя этим четырём шагам, вы сможете плавно сочетать непрозрачные и полупрозрачные прямоугольники, создавая убедительный эффект псевдо‑прозрачности в любом выводе PostScript.

## Распространённые проблемы и решения

| Проблема | Почему происходит | Решение |
|----------|-------------------|----------|
| Цвета выглядят полностью непрозрачными | Значение альфа случайно установлено в 255 | Используйте `Color.FromArgb(alpha, …)` с `alpha` < 255 |
| Градиент растянут неправильно | Неправильная матрица преобразования | Проверьте параметры матрицы, соответствующие размерам прямоугольника |
| Выходной файл пустой | Поток не закрыт или не вызван `Save()` | Убедитесь, что `document.ClosePage()` и `document.Save()` выполнены внутри блока `using` |

## Часто задаваемые вопросы

**В: Совместим ли Aspose.Page со всеми версиями .NET?**  
О: Aspose.Page для .NET совместим с различными версиями .NET Framework, обеспечивая гибкость и простоту интеграции.

**В: Можно ли применить псевдо‑прозрачность к другим фигурам, кроме прямоугольников?**  
О: Да, те же принципы можно использовать для любой фигуры, изменив соответствующим образом `GraphicsPath`.

**В: Где найти дополнительные примеры и документацию?**  
О: Изучите [документацию Aspose.Page](https://reference.aspose.com/page/net/) для полного набора примеров и подробных справочных материалов API.

**В: Есть ли бесплатная пробная версия Aspose.Page?**  
О: Да, бесплатную пробную версию Aspose.Page можно получить по [этой ссылке](https://releases.aspose.com/).

**В: Как получить временную лицензию для Aspose.Page?**  
О: Перейдите по [этой ссылке](https://purchase.aspose.com/temporary-license/) для получения временной лицензии Aspose.Page.

---

**Последнее обновление:** 2026-03-29  
**Тестировано с:** Aspose.Page 24.11 для .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}