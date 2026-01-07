---
date: 2026-01-07
description: Узнайте, как создать XPS‑документ, добавить клоны глифов, использовать
  сплошную кисть цвета и сохранить файл XPS с помощью Aspose.Page для .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Создание XPS‑документа – добавление клона глифа и изменение цвета с помощью
  Aspose.Page для .NET
url: /ru/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание XPS Document – добавление Glyph Clone и изменение цвета с помощью Aspose.Page for .NET

## Introduction

Добро пожаловать в это пошаговое руководство, которое покажет вам, **как создавать файлы XPS Document**, клонировать глифы и изменять их цвета с помощью Aspose.Page for .NET. Независимо от того, создаёте ли вы динамические отчёты, счета‑фактуры или пользовательскую графику, освоение этих техник позволяет получать визуально насыщенный XPS‑вывод, оставаясь в экосистеме .NET.

## Quick Answers
- **Какова основная цель?** Создать XPS Document, добавить клоны глифов и изменить их цвета.  
- **Какая библиотека используется?** Aspose.Page for .NET.  
- **Нужна ли лицензия?** Доступна временная лицензия для оценки; полная лицензия требуется для продакшн‑использования.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Как сохранить результат?** Используйте метод `Save`, чтобы записать файл XPS на диск.

## Prerequisites

Перед тем как приступить к уроку, убедитесь, что у вас есть следующее:

- Базовое понимание языка программирования C#.  
- Установленная Visual Studio или любая другая предпочтительная среда разработки C#.  
- Библиотека Aspose.Page for .NET. Вы можете скачать её [здесь](https://releases.aspose.com/page/net/).  
- Знакомство с форматом XPS Document.

## Import Namespaces

Чтобы начать, включите необходимые пространства имён в ваш проект C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How to Create XPS Document and Add Glyph Clones

### Step 1: Set up Your Document Directory

Начните с настройки каталога, в котором будут храниться ваши документы:

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create the First XPS Document

Теперь создадим первый XPS Document:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Step 3: Add Glyphs to the First Document

Добавьте глифы в первый документ, используя указанные параметры:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 4: Fill Glyphs with a Solid Color Brush

Заполните глифы в первом документе **сплошной кистью цвета**, например, зелёным:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Step 5: Create the Second XPS Document

Теперь создадим второй XPS Document:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Step 6: How to Add Glyph Clone to Another Document

Клонируйте глифы из первого документа и добавьте их во второй документ:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Step 7: How to Change Color of the Cloned Glyph

Измените цвет клонированных глифов во втором документе, например, на красный. Это демонстрирует **как изменить цвет** глифа после клонирования:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Step 8: Save XPS File – First Document

Сохраните первый XPS Document в папку, которую вы определили ранее:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Step 9: Save XPS File – Second Document

Сохраните второй XPS Document:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Поздравляем! Вы успешно **создали XPS Document**, добавили клоны глифов и изменили их цвета с помощью Aspose.Page for .NET.

## Why Use Glyph Cloning and Color Changes?

- **Повторное использование:** Клонируйте существующие глифы, чтобы повторно использовать сложные векторные формы без их повторного определения.  
- **Производительность:** Сокращает время обработки по сравнению с воссозданием глифов с нуля.  
- **Гибкость дизайна:** Применяйте разные экземпляры `SolidColorBrush` к одному глифу для получения разнообразных визуальных тем.  
- **Редактирование между документами:** Клонируйте глифы между несколькими XPS‑файлами, обеспечивая единый брендинг в отчётах.

## Common Issues & Troubleshooting

| Issue | Solution |
|-------|----------|
| **Clone returns null** | Убедитесь, что исходный глиф (`glyphs`) добавлен в первый документ перед клонированием. |
| **Color does not change** | Приведите `glyphs.Fill` к типу `XpsSolidColorBrush` перед установкой свойства `Color` (как показано в Шаге 7). |
| **File not saved** | Проверьте, что `dataDir` указывает на действительную, доступную для записи папку, и что у вас есть соответствующие права доступа к файловой системе. |
| **Unexpected glyph size** | Отрегулируйте параметр размера шрифта (второй аргумент в `AddGlyphs`), чтобы масштабировать глиф должным образом. |

## Frequently Asked Questions

**Q1: Можно ли использовать Aspose.Page for .NET с другими форматами документов?**  
A1: Aspose.Page for .NET специально разработан для работы с XPS Document. Если вам нужно обрабатывать другие форматы, вы можете изучить другие библиотеки Aspose, предназначенные для этих форматов.

**Q2: Доступна ли временная лицензия для Aspose.Page for .NET?**  
A2: Да, вы можете получить временную лицензию для тестирования. Посетите [здесь](https://purchase.aspose.com/temporary-license/) для получения дополнительной информации.

**Q3: Как получить поддержку или помощь по возникшим вопросам?**  
A3: Вы можете посетить [форум Aspose.Page](https://forum.aspose.com/c/page/39), чтобы связаться с сообществом и получить помощь.

**Q4: Есть ли ограничения у бесплатной пробной версии?**  
A4: У бесплатной пробной версии есть некоторые ограничения; рекомендуется ознакомиться с документацией для получения деталей перед использованием.

**Q5: Где найти полную документацию по Aspose.Page for .NET?**  
A5: Вы можете обратиться к документации [здесь](https://reference.aspose.com/page/net/) для получения подробной информации и примеров.

**Q6: Как изменить цвет обводки глифа вместо заливки?**  
A6: Используйте `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);`, чтобы задать кисть обводки.

**Q7: Можно ли добавить несколько клонов глифа в один документ?**  
A7: Да, вызывайте `doc2.Add(glyphs.Clone());` многократно, при необходимости корректируя позиции.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}