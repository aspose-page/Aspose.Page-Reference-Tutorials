---
date: 2026-02-23
description: Узнайте, как добавить градиент в файлы PostScript, сохранить файл PostScript
  с размером страницы A4 и заполнить прямоугольник градиентом с помощью Aspose.Page
  для .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Как добавить градиент – диагональный градиент в PostScript (PS) с помощью Aspose.Page
  .NET
url: /ru/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить градиент: Диагональный градиент в PostScript (PS) с помощью Aspose.Page .NET

## Введение

Добавление диагонального градиента в документ PostScript (PS) может значительно улучшить визуальную привлекательность, особенно когда вам нужны **how to add gradient** эффекты в технических отчетах, брошюрах или графически насыщенных приложениях. В этом руководстве вы увидите, как именно добавить градиент в файл PostScript, установить размер страницы A4 и заполнить прямоугольник плавным переходом цветов с помощью Aspose.Page для .NET.

## Быстрые ответы
- **Какая библиотека требуется?** Aspose.Page for .NET  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Можно ли изменить направление градиента?** Да – поверните трансформацию кисти, как показано в коде  
- **Как сохранить результат?** Используйте `PsDocument.Save()`, который записывает файл PostScript на диск  
- **Нужна ли лицензия для продакшн?** Да, коммерческая лицензия разблокирует полный функционал  

## Что такое диагональный градиент в PostScript?

Диагональный градиент — это линейный переход цветов, который проходит под углом (обычно 45°) через форму. В PostScript это достигается применением `LinearGradientBrush` с пользовательской матрицей преобразования, которая вращает, масштабирует и перемещает градиент, чтобы соответствовать требуемому прямоугольнику.

## Почему использовать Aspose.Page для заливок градиентом?

Aspose.Page абстрагирует низкоуровневые команды PostScript, позволяя работать с привычными объектами графики .NET. Вы можете создавать сложные заливки, задавать размеры страниц и экспортировать напрямую в **save PostScript file** без работы с сырым синтаксисом PS.

## Предварительные требования

- **Aspose.Page for .NET Library** – загрузите её [here](https://releases.aspose.com/page/net/).  
- **Document Directory** – папка, в которой будет записан сгенерированный файл `*.ps`.

Теперь, когда основные моменты покрыты, давайте пошагово рассмотрим реализацию.

## Импорт пространств имён

Сначала импортируйте пространства имён, которые предоставляют доступ к устройству EPS, утилитам рисования и классам ввода‑вывода.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Шаг 1: Создать поток вывода для документа PostScript (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Шаг 2: Установить размер страницы A4 (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Шаг 3: Создать новый одностраничный PS документ

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Шаг 4: Определить параметры прямоугольника

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Шаг 5: Создать графический путь

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Шаг 6: Создать линейную кисть градиента (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Шаг 7: Создать трансформацию для кисти

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Шаг 8: Применить трансформации к кисти (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Шаг 9: Установить трансформацию для кисти

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Шаг 10: Установить заливку и заполнить прямоугольник

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Шаг 11: Закрыть текущую страницу

```csharp
	//Close current page
	document.ClosePage();
```

## Шаг 12: Сохранить документ (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Как сохранить файл PostScript

Вызов `PsDocument.Save()` записывает полностью сформированное содержимое PostScript в поток, открытый в **Step 1**. После завершения блока `using` файл `DiagonaGradient_outPS.ps` будет доступен в указанной вами директории.

## Распространённые сценарии использования

- **Technical documentation**, которой требуется тонкая фоновая затенённость.  
- **Marketing brochures**, где диагональный градиент придаёт современный вид.  
- **Automated report generators**, генерирующие печатные PS‑файлы «на лету».

## Устранение неполадок и советы

- **Incorrect colors** – дважды проверьте ARGB‑значения, передаваемые в `LinearGradientBrush`.  
- **Gradient not visible** – убедитесь, что матрица преобразования правильно вращает и масштабирует; вызов `Rotate(-45)` задаёт диагональный угол.  
- **File not created** – проверьте, что `dataDir` указывает на существующую папку и приложение имеет права записи.

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Page со всеми версиями .NET?**  
A: Aspose.Page поддерживает широкий спектр версий .NET, от .NET Framework 4.5+ до .NET 6+, обеспечивая широкую совместимость.

**Q: Можно ли настроить цвета градиента в Aspose.Page?**  
A: Да, вы можете указать любые ARGB‑цвета при создании `LinearGradientBrush`, получая полный контроль над начальными и конечными оттенками.

**Q: Доступна ли пробная версия Aspose.Page?**  
A: Да, вы можете ознакомиться с возможностями Aspose.Page, скачав пробную версию [here](https://releases.aspose.com/).

**Q: Как получить временную лицензию для Aspose.Page?**  
A: Получите временную лицензию для Aspose.Page [here](https://purchase.aspose.com/temporary-license/), чтобы разблокировать дополнительные возможности во время оценки.

**Q: Где можно найти поддержку сообщества Aspose.Page?**  
A: Взаимодействуйте с сообществом Aspose.Page на [forum](https://forum.aspose.com/c/page/39) для получения помощи и обсуждений.

---

**Последнее обновление:** 2026-02-23  
**Тестировано с:** Aspose.Page for .NET (latest stable release)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}