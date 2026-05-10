---
date: 2026-01-28
description: Узнайте, как конвертировать EPS в PNG с помощью Aspose.Page для .NET
  и применить лицензию с оплатой за использование для беспрепятственной обработки
  документов.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Конвертировать EPS в PNG и применить лицензирование по метрам с Aspose.Page
  для .NET
url: /ru/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование EPS в PNG и применение лицензии с измерением в Aspose.Page для .NET

## Introduction

Откройте весь потенциал Aspose.Page для .NET, **преобразуя EPS в PNG** и применяя лицензию с измерением. Этот учебник проведет вас через каждый шаг — от загрузки файла EPS до сохранения его как изображения PNG — чтобы вы могли эффективно обрабатывать документы без водяных знаков оценки.

## Quick Answers
- **Что охватывает этот учебник?** Преобразование файлов EPS в изображения PNG и применение лицензии с измерением с Aspose.Page для .NET.  
- **Нужна ли лицензия?** Да, для использования в продакшене требуется лицензия с измерением.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Сколько времени занимает реализация?** Около 10–15 минут для базового преобразования.  
- **Можно ли запускать это на Linux/macOS?** Конечно — Aspose.Page кроссплатформенный.

## What is “convert EPS to PNG”?

Преобразование EPS в PNG означает растеризацию векторного Encapsulated PostScript (EPS) файла в растровое изображение PNG. Это полезно, когда необходимо отображать или встраивать графику в веб‑страницы, отчёты или UI‑компоненты, которые не поддерживают EPS.

## Why use a metered license for EPS to image conversion?

Лицензия с измерением позволяет платить только за обработанные страницы, что идеально для нагрузок с переменным объёмом. Она также удаляет красный баннер оценки, который появляется при использовании бесплатной версии, обеспечивая чистый вывод для конечных пользователей.

## Prerequisites

Прежде чем приступить к шагам, убедитесь, что у вас есть следующие предварительные требования:

- Действительная лицензия Aspose.Page для .NET: её можно получить на [purchase.aspose.com](https://purchase.aspose.com/buy).
- Установленная библиотека Aspose.Page: см. [documentation](https://reference.aspose.com/page/net/) для инструкций по установке.
- Среда разработки .NET: убедитесь, что на вашем компьютере настроена рабочая среда .NET.

## Import Namespaces

In your .NET project, import the necessary namespaces to access Aspose.Page functionalities:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## How to convert EPS to PNG with a metered license?

Ниже представлено пошаговое руководство, охватывающее всё, что вам нужно знать.

### Step 1: Set Metered Public and Private Keys

Инициализируйте класс `Aspose.Page.Metered` и задайте публичный и приватный ключи лицензии с измерением. Замените `<type public key here>` и `<type private key here>` вашими реальными ключами.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Step 2: Load EPS File and Create Document

Укажите путь к вашему файлу EPS и создайте поток для чтения его содержимого. Затем создайте экземпляр класса `PsDocument` из этого потока.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Step 3: Convert EPS to PNG Image

Создайте `ImageDevice` для преобразования файла EPS в изображение PNG. Сохраните файл EPS как изображение, используя `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Step 4: Retrieve Image Bytes

Получите массивы байтов изображения, где каждый массив представляет одну страницу. В данном случае у нас одна страница.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Step 5: Save Image Bytes to File

Сохраните массивы байтов изображения в файл, обеспечивая успешное преобразование EPS в PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Step 6: Verify Metered License

Визуально проверьте, применена ли лицензия с измерением. Если полученное изображение не содержит красного сообщения об оценке, это означает, что лицензия с измерением применена без проблем.

Теперь вы готовы использовать все возможности Aspose.Page для .NET с лицензией с измерением!

## Common Issues and Solutions

| Проблема | Причина | Решение |
|-------|-------|-----|
| Красный баннер оценки всё ещё появляется | Лицензия не установлена или неверные ключи | Дважды проверьте публичный/приватный ключи и убедитесь, что `SetMeteredKey` вызывается до любой обработки документа |
| Файл вывода не создан | Неправильный путь `dataDir` или права доступа к файлам | Убедитесь, что каталог существует и приложение имеет права записи |
| Несколько страниц не сохранены | Сохранена только первая страница | Пройдите в цикле по `imagesBytes` и запишите каждый массив в отдельный PNG‑файл |

## Frequently Asked Questions

**В: Можно ли использовать лицензию с измерением в конвейере CI/CD?**  
О: Да, вы можете хранить ключи безопасно (например, в переменных окружения) и вызывать `SetMeteredKey` во время процесса сборки.

**В: Поддерживает ли Aspose.Page сохранение цветового профиля при конвертации в PNG?**  
О: Вывод PNG сохраняет исходную цветовую информацию, но вы можете дополнительно настроить её через `ImageSaveOptions`.

**В: Можно ли преобразовать EPS в другие растровые форматы (JPEG, BMP)?**  
О: Конечно — просто измените `ImageSaveOptions` на нужный формат.

**В: Какой максимальный размер EPS‑файла поддерживается?**  
О: Aspose.Page работает с большими файлами, но потребление памяти растёт с увеличением разрешения изображения. Для очень больших документов рекомендуется обрабатывать страницы по отдельности.

**В: Как программно получить количество страниц в EPS‑файле?**  
О: Используйте `document.PagesCount` после загрузки `PsDocument`.

## FAQ's

### Q1: Как получить лицензию с измерением для Aspose.Page для .NET?

A1: Перейдите на [purchase.aspose.com](https://purchase.aspose.com/buy), чтобы приобрести действительную лицензию.

### Q2: Где найти документацию по Aspose.Page для .NET?

A2: Обратитесь к [Aspose.Page .NET](https://reference.aspose.com/page/net/) для полной документации.

### Q3: Есть ли форум для обсуждения Aspose.Page и поддержки?

A3: Да, посетите [forum](https://forum.aspose.com/c/page/39), чтобы общаться с сообществом и получать помощь.

### Q4: Можно ли попробовать Aspose.Page для .NET перед покупкой?

A4: Конечно! Получите бесплатную пробную версию по ссылке [here](https://releases.aspose.com/).

### Q5: Как получить временную лицензию для Aspose.Page для .NET?

A5: Перейдите на [temporary license/](https://purchase.aspose.com/temporary-license/), чтобы получить временную лицензию.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}