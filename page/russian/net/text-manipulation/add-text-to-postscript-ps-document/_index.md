---
date: 2026-03-21
description: Узнайте, как заполнять текст и добавлять текст в PS‑документы с помощью
  Aspose.Page для .NET. Пошаговое руководство с примерами кода.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Как заполнить текст в документах PostScript (PS) с помощью Aspose.Page
url: /ru/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как заполнить текст в документах PostScript (PS) с помощью Aspose.Page

## Введение

Если вам нужно **how to fill text** внутри файла PostScript (PS), Aspose.Page для .NET делает это простым. Независимо от того, генерируете ли вы отчёты, счета или пользовательскую графику, добавление и стилизация текста является основной задачей. В этом руководстве мы пройдём весь процесс — от настройки среды до сохранения окончательного PS‑документа — чтобы вы могли уверенно добавлять текст в PS‑файлы в ваших .NET‑приложениях.

## Быстрые ответы
- **Что означает “fill text”?** Он отрисовывает символы с помощью сплошной кисти, рисуя глифы непосредственно на странице.  
- **Могу ли я использовать пользовательские шрифты?** Да — Aspose.Page поддерживает пользовательские шрифты через функцию `add custom font ps`.  
- **Как сохранить PS‑документ?** Вызовите `document.Save()` после закрытия страницы; это записывает файл на диск (`save ps document`).  
- **Поддерживается ли “fill and stroke text”?** Абсолютно; используйте `FillAndStrokeText` для применения как заливки, так и обводки.  
- **Какие версии .NET требуются?** Любой .NET Framework 4.5+ или .NET Core/5/6+ runtime.

## Что такое “how to fill text” в PS‑документе?

Заполнение текста означает покраску символов сплошным цветом (или кистью) без контура. В PostScript это аналогично оператору `fill`. Aspose.Page абстрагирует это в удобные методы, такие как `FillText` и `FillAndStrokeText`.

## Почему стоит использовать Aspose.Page для добавления пользовательского шрифта ps?

- **Полная поддержка шрифтов** – системные шрифты и внешние TrueType/OpenType шрифты работают сразу.  
- **Точное позиционирование** – вы контролируете координаты X/Y, размер и стиль.  
- **Богатое стилизование** – комбинируйте заливки, обводки и пера для эффектов, таких как “fill and stroke text”.  
- **Кросс‑платформенный** – работает на Windows, Linux и macOS с тем же API.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

- **Aspose.Page for .NET** – загрузите библиотеку из [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/).  
- **Document Directory** – папка на вашем компьютере, где будут находиться исходные и выходные PS‑файлы (в коде называется *Your Document Directory*).  
- **Fonts Folder** – подпапка, содержащая любые пользовательские шрифты, которые вы планируете использовать.

## Импорт пространств имён

Сначала импортируйте необходимые пространства имён, чтобы компилятор знал, где искать используемые классы:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Пошаговое руководство

### Шаг 1: Создать поток вывода для PS‑документа  

Мы открываем `FileStream`, который будет хранить сгенерированный PS‑файл, настраиваем `PsSaveOptions`, указывая нашу папку пользовательских шрифтов, и создаём экземпляр `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Совет:** Оставьте блок `using`, чтобы поток закрывался автоматически, что также завершает PS‑файл (`save ps document`).

### Шаг 2: Заполнить текст системным шрифтом  

Здесь мы демонстрируем базовую операцию **how to fill text** с использованием встроенного шрифта *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Шаг 3: Заполнить текст пользовательским шрифтом  

Если вам нужен определённый вид, загрузите пользовательский шрифт из папки шрифтов с помощью `ExternalFontCache.FetchDrFont`. Это удовлетворяет требованию **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Шаг 4: Обвести (Stroke) текст системным шрифтом  

Обводка рисует контур глифа. Сочетайте её с заливкой для эффекта “fill and stroke”.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Почему это важно:** Вызов `FillAndStrokeText` показывает, как **fill and stroke text** в один шаг, предоставляя более богатый контроль над типографикой.

### Шаг 5: Обвести текст пользовательским шрифтом  

Та же техника обводки работает с любым пользовательским шрифтом, который вы загрузили.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Шаг 6: Закрыть страницу и сохранить документ  

Завершить просто: закройте текущую страницу и вызовите `Save()`, чтобы записать PS‑файл на диск.

```csharp
document.ClosePage();
document.Save();
}
```

> **Результат:** Вы найдёте `AddText_outPS.ps` в *Your Document Directory*, содержащий как заполненный, так и обведённый текст, отрисованный системными и пользовательскими шрифтами.

## Распространённые проблемы и решения

| Проблема | Решение |
|----------|---------|
| **Пользовательский шрифт не найден** | Убедитесь, что файл шрифта (.ttf/.otf) существует в папке, указанной в `AdditionalFontsFolders`. |
| **Текст отображается в неправильном положении** | Отрегулируйте координаты X/Y, передаваемые в `FillText`/`OutlineText`. Помните, что PostScript использует пункты (1/72 дюйма). |
| **Цвета выглядят иначе** | Убедитесь, что вы используете `SolidBrush` или `Pen` с правильными значениями `Color`. |
| **Документ не сохраняется** | Убедитесь, что блок `using` завершается без исключений и приложение имеет права записи в целевую папку. |

## Часто задаваемые вопросы

**В: Могу ли я использовать Aspose.Page с другими .NET библиотеками?**  
**О:** Да, Aspose.Page легко интегрируется с другими .NET компонентами, позволяя комбинировать библиотеки PDF, изображений или диаграмм в одном решении.

**В: Являются ли пользовательские шрифты обязательными для этого процесса?**  
**О:** Хотя системные шрифты работают нормально, пользовательские шрифты предоставляют полную свободу дизайна и полезны, когда требуется фирменная типографика.

**В: Подходит ли Aspose.Page для масштабной обработки документов?**  
**О:** Абсолютно. Библиотека оптимизирована для сценариев с высокой пропускной способностью и может эффективно обрабатывать тысячи PS‑файлов.

**В: Могу ли я изменить позицию текста в PS‑документе?**  
**О:** Конечно — просто измените числовые значения X/Y в вызовах `FillText` или `OutlineText`.

**В: Где я могу получить помощь по вопросам, связанным с Aspose.Page?**  
**О:** Посетите [Aspose.Page Forum](https://forum.aspose.com/c/page/39), чтобы связаться с сообществом и получить экспертную помощь.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-03-21  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose