---
title: Отредактируйте существующий билет на печать с помощью Aspose.Page для .NET
linktitle: Редактировать существующий билет на печать
second_title: Aspose.Page .NET API
description: Научитесь редактировать заявки на печать в документах XPS с помощью Aspose.Page для .NET. Пошаговое руководство для разработчиков. Улучшите контроль печати документов без особых усилий.
weight: 11
url: /ru/net/print-ticket-management/print-ticket-management/aspose.page/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Отредактируйте существующий билет на печать с помощью Aspose.Page для .NET

## Введение

Добро пожаловать в это подробное руководство по редактированию существующих билетов на печать с помощью Aspose.Page для .NET! Aspose.Page — мощная библиотека, которая позволяет разработчикам легко работать с документами XPS. В этом уроке мы познакомим вас с процессом редактирования печатных билетов на практических примерах, разбив каждый шаг для беспрепятственного обучения.

## Предварительные условия

Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:

- Базовые знания программирования на C#.
- Visual Studio установлена на вашем компьютере.
- Библиотека Aspose.Page для .NET загружена и используется в вашем проекте.

 Если вы еще не установили Aspose.Page для .NET, вы можете скачать его.[здесь](https://releases.aspose.com/page/net/).

## Импортировать пространства имен

Для начала импортируйте необходимые пространства имен в свой проект C#. Это гарантирует, что у вас есть доступ к функциям Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Теперь давайте разобьем предоставленный вами пример кода на несколько шагов.

## Шаг 1. Установите каталог документов

```csharp
// Путь к каталогу документов.
string dir = "Your Document Directory";
```

 Вот замените`"Your Document Directory"` с фактическим путем, по которому расположены ваши документы XPS.

## Шаг 2. Откройте документ XPS с билетами на печать

```csharp
// ExStart:3
XpsDocument xDocs = new XpsDocument(dir + "input3.xps");
JobPrintTicket pt = xDocs.JobPrintTicket;
// ExEnd:3
```

Этот шаг включает открытие документа XPS и получение его JobPrintTicket.

## Шаг 3. Удаление параметров из билета печати задания

```csharp
// ExStart:4
pt.Remove(
	"ns0000:PageDevmodeSnapshot",
	"ns0000:JobInterleaving",
	"ns0000:JobImageType");
// ExEnd:4
```

 Удалите ненужные параметры из JobPrintTicket, используя команду`Remove`метод.

## Шаг 4. Добавьте параметры в билет печати задания

```csharp
// ExStart:5
pt.Add(
	new JobCopiesAllDocuments(2),
	new PageMediaSize(PageMediaSize.PageMediaSizeOption.ISOA4));
// ExEnd:5
```

 Добавьте нужные параметры в JobPrintTicket, используя`Add`метод.

## Шаг 5. Сохраните документ с измененным билетом на печать задания

```csharp
// ExStart:6
xDocs.Save(dir + "output3.xps");
// ExEnd:6
```

Сохраните измененный документ XPS с обновленным JobPrintTicket.

Повторите эти шаги, чтобы упростить процесс редактирования билетов на печать с помощью Aspose.Page для .NET!

## Заключение

Поздравляем! Вы успешно научились редактировать существующие билеты на печать с помощью Aspose.Page для .NET. Эта мощная библиотека обеспечивает гибкость и простоту работы с документами XPS, что делает ее бесценным инструментом для разработчиков.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Page для .NET с другими форматами документов?

О1: Да, Aspose.Page для .NET в первую очередь ориентирован на документы XPS, но Aspose предлагает различные библиотеки для разных форматов. Проверьте их документацию для получения более подробной информации.

### Вопрос 2. Совместим ли Aspose.Page для .NET с .NET Core?

О2: Да, Aspose.Page для .NET совместим с .NET Core, что обеспечивает гибкость вашей среды разработки.

### В3: Как я могу получить поддержку или задать вопросы, связанные с Aspose.Page?

 A3: Посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39)чтобы получить поддержку сообщества и связаться с другими разработчиками.

### Вопрос 4. Существует ли бесплатная пробная версия Aspose.Page для .NET?

 A4: Да, вы можете получить бесплатную пробную версию.[здесь](https://releases.aspose.com/).

### Вопрос 5: Как я могу получить временную лицензию на Aspose.Page для .NET?

 А5: Посетите[эта ссылка](https://purchase.aspose.com/temporary-license/) получить временную лицензию.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
