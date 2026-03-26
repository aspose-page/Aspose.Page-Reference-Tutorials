---
date: 2026-03-26
description: Узнайте, как создавать документы PostScript в .NET с текстурными шаблонами‑мозаикой
  с помощью Aspose.Page. Следуйте нашему пошаговому руководству, чтобы добавить богатые
  текстуры в ваши PS‑файлы.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Создать документ PostScript .NET с текстурным тайлингом
url: /ru/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PostScript‑документа .NET с текстурным тайлингом

## Как создать PostScript‑документ .NET с текстурным тайлингом

В этом руководстве вы узнаете, как **создать PostScript‑документ .NET** и обогатить его шаблоном текстурного тайлинга с помощью библиотеки Aspose.Page. Мы пройдем каждый шаг, от настройки проекта до заполнения и обводки текста текстурной кистью, чтобы вы могли за считанные минуты получать визуально привлекательные PS‑файлы.

## Быстрые ответы
- **Какая библиотека используется?** Aspose.Page for .NET  
- **Можно ли использовать .NET Core?** Да, библиотека поддерживает .NET Core и .NET 5/6  
- **Какие форматы изображений подходят для текстуры?** Любой формат, поддерживаемый System.Drawing (BMP, PNG, JPEG и т.д.)  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового примера  
- **Нужна ли лицензия?** Бесплатная trial‑версия подходит для тестирования; для продакшна требуется лицензия  

## Предварительные требования

- [Visual Studio](https://visualstudio.microsoft.com/) установленный на вашем компьютере.  
- Базовые знания программирования на C#.  
- Скачать и установить [Aspose.Page for .NET library](https://releases.aspose.com/page/net/).  
- Файл изображения для текстурного шаблона (например, **TestTexture.bmp**).

## Импорт пространств имён

В вашем C#‑файле импортируйте необходимые пространства имён, чтобы компилятор знал, где искать используемые типы:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Шаг 1: Настройка каталога документа

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Замените **Your Document Directory** на папку, в которой вы хотите сохранить сгенерированный PS‑файл.

## Шаг 2: Создание выходного потока для PS‑документа

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Этот блок открывает файловый поток, задаёт размер страницы (по умолчанию A4) и создаёт новый экземпляр **PsDocument**, на котором мы будем рисовать.

## Шаг 3: Применение шаблона текстурного тайлинга

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Здесь мы загружаем bitmap, оборачиваем его в **TextureBrush**, при необходимости растягиваем по горизонтали и указываем **PsDocument** использовать эту кисть для последующих операций рисования.

## Шаг 4: Создание пути прямоугольника и заполнение

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Определяется простой прямоугольник и заполняется текстурной кистью, установленной ранее.

## Шаг 5: Установка обводки и рисование

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Мы получаем текущий paint (текстурную кисть), создаём красную ручку для контура и рисуем границу прямоугольника.

## Шаг 6: Заполнение и обводка текста текстурным шаблоном

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Этот шаг демонстрирует возможность **fill and stroke text**: символы «ABC» заполняются текстурной кистью, а затем обводятся, создавая яркий визуальный эффект.

## Шаг 7: Сохранение и закрытие документа

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Закрытие страницы завершает команды рисования, а `Save()` записывает PostScript‑файл на диск.

## Распространённые проблемы и решения

- **Текстура выглядит неправильно растянутой** – Отрегулируйте значения `Matrix`, чтобы контролировать масштабирование по осям X/Y.  
- **Изображение не найдено** – Убедитесь, что `dataDir` указывает на правильную папку и имя файла точно совпадает, включая регистр.  
- **Цвета выглядят некорректно** – Помните, что PostScript использует независимое от устройства цветовое пространство; убедитесь, что вы используете объекты `Color`, корректно отображающие цвета.

## Часто задаваемые вопросы

**В:** Можно ли использовать другие форматы изображений для текстурного шаблона?  
**О:** Да, любой формат, поддерживаемый `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF и т.д.), подходит.

**В:** Совместима ли Aspose.Page с .NET Core?  
**О:** Абсолютно. Библиотека работает на .NET Framework, .NET Core и .NET 5/6.

**В:** Как изменить размер текстурированного прямоугольника?  
**О:** Измените значения `RectangleF` в шаге создания прямоугольника (например, `new RectangleF(0, 0, 300, 150)`).

**В:** Можно ли применить несколько текстурных шаблонов в одном документе?  
**О:** Да. Просто создайте новый `TextureBrush` с другим изображением и вызовите `SetPaint` снова перед рисованием следующей фигуры или текста.

**В:** Где найти больше примеров и справочную информацию по API?  
**О:** Посетите [Aspose.Page Forum](https://forum.aspose.com/c/page/39) для помощи сообщества и официальную [documentation](https://reference.aspose.com/page/net/) для детального описания API.

## Заключение

Теперь вы знаете, как **создать PostScript‑документ .NET** и применить к нему шаблон текстурного тайлинга, включая **fill and stroke text** с этой текстурой. Экспериментируйте с разными изображениями, матрицами масштабирования и графическими примитивами, чтобы создавать кастомные PS‑файлы для отчётов, листовок или любой графически‑насыщенной продукции.

---

**Последнее обновление:** 2026-03-26  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}