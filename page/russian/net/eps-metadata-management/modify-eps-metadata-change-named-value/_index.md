---
title: Измените именованное значение с помощью Aspose.Page для .NET
linktitle: Изменить именованное значение
second_title: Aspose.Page .NET API
description: Узнайте, как изменить именованные значения в файлах EPS с помощью Aspose.Page для .NET. Легко настраивайте метаданные XMP для индивидуальной обработки документов.
type: docs
weight: 16
url: /ru/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## Введение

В мире обработки документов Aspose.Page для .NET выделяется как мощный инструмент для работы с файлами EPS. Одной из ключевых функций, которые он предлагает, является возможность изменять именованные значения в метаданных XMP. Это руководство проведет вас через процесс изменения именованного значения с помощью Aspose.Page для .NET, что позволит вам настроить файлы EPS в соответствии с вашими конкретными потребностями.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

-  Aspose.Page для .NET: убедитесь, что у вас установлена библиотека Aspose.Page для .NET. Если нет, то вы можете скачать его[здесь](https://releases.aspose.com/page/net/).

- Каталог документов. Создайте специальный каталог для ваших файлов EPS, в котором вы сможете выполнять изменения именованных значений.

## Импортировать пространства имен

В вашем проекте .NET вам необходимо импортировать необходимые пространства имен для доступа к функциям, предоставляемым Aspose.Page. Добавьте в свой код следующие пространства имен:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Теперь давайте разобьем код на несколько шагов для более полного понимания:

## Шаг 1. Инициализация входного потока файла EPS

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

На этом этапе мы настраиваем входной поток для файла EPS, который вы хотите изменить. Обязательно замените «Каталог ваших документов» фактическим путем к каталогу ваших документов.

## Шаг 2. Получите метаданные XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Получите существующие метаданные XMP из файла EPS. Если файл EPS не содержит метаданных XMP, будет создан новый файл со значениями из комментариев метаданных PS.

## Шаг 3. Измените значения метаданных XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Здесь мы демонстрируем изменение двух именованных значений в структуре «xmpTPg:MaxPageSize». Вы можете настроить это в соответствии с вашими конкретными требованиями.

## Шаг 4. Сохраните файл EPS с измененными метаданными XMP

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Сохраните измененный файл EPS в выходной поток. Теперь файл будет отражать изменения, внесенные в метаданные XMP.

## Заключение

Из этого руководства вы узнали, как использовать Aspose.Page для .NET для изменения именованных значений в метаданных XMP в файлах EPS. Эта функциональность открывает целый мир возможностей для настройки и адаптации ваших документов в соответствии с конкретными требованиями.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Page для .NET с другими форматами документов?

О1: Да, Aspose.Page поддерживает различные форматы документов, включая EPS, XPS и PDF.

### Вопрос 2. Доступна ли пробная версия Aspose.Page для .NET?

 О2: Да, вы можете получить доступ к бесплатной пробной версии.[здесь](https://releases.aspose.com/).

### Вопрос 3. Где я могу найти дополнительную документацию по Aspose.Page для .NET?

 A3: обратитесь к документации[здесь](https://reference.aspose.com/page/net/).

### Вопрос 4: Как я могу получить временную лицензию на Aspose.Page для .NET?

 A4: Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).

### Вопрос 5: Какие варианты поддержки доступны для пользователей Aspose.Page для .NET?

 A5: Посетите форум сообщества.[здесь](https://forum.aspose.com/c/page/39) за поддержку и обсуждения.