---
date: 2025-12-28
description: Узнайте, как создать XPS‑документ в Java с помощью Aspose.Page и легко
  добавить мозаичное изображение с помощью этого пошагового руководства.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Как создать XPS‑документ с мозаичным изображением в Java
url: /ru/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание XPS Document и добавление Tiled Image в Java

## Introduction
В современном Java‑разработке возможность **создать XPS документ** программно является ценным навыком, особенно когда нужно обогатить его графикой, такой как мозаичные изображения. Aspose.Page for Java упрощает этот процесс, позволяя сосредоточиться на визуальном дизайне, а не на низкоуровневой работе с файлами. В этом руководстве вы узнаете, как именно создать XPS документ, **добавить мозаичное изображение**, и сохранить результат, используя понятные пошаговые примеры кода.

## Quick Answers
- **Что делает Aspose.Page?** Предоставляет высокоуровневый API для создания и манипулирования XPS документами в Java.  
- **Могу ли я замостить изображение?** Да — используйте `XpsImageBrush` с `XpsTileMode.Tile`.  
- **Нужна ли лицензия?** Для использования в продакшене требуется временная или коммерческая лицензия.  
- **Какая версия Java поддерживается?** Совместима с любой JDK 8+.  
- **Сколько времени занимает реализация?** Около 10–15 минут для базового сценария с мозаичным изображением.

## What is “create XPS document”?
Что такое «создание XPS документа»?  
Файл XPS (XML Paper Specification) — это формат фиксированного макета, похожий на PDF. Программное создание XPS документа позволяет генерировать печатные, независимые от устройства файлы непосредственно из Java‑кода.

## Why add a tiled image?
Почему добавлять мозаичное изображение?  
Мозаичное изображение повторяет графику по определённой области, что идеально подходит для фоновых изображений, водяных знаков или заполнения узорами. С помощью `XpsTileMode.Tile` из Aspose.Page это можно реализовать всего несколькими строками кода.

## Prerequisites
1. **Java Development Kit (JDK)** — установлен JDK 8 или новее.  
2. **Aspose.Page for Java** — загрузите с [веб‑сайта](https://releases.aspose.com/page/java/).  
3. **Записываемый каталог** — куда будет сохранён сгенерированный XPS файл.

## Import Packages
В вашем Java‑проекте импортируйте необходимые классы:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Project
Шаг 1: Настройте ваш проект  
Добавьте JAR‑файлы Aspose.Page в classpath вашего проекта и убедитесь, что операторы импорта компилируются без ошибок.

### Step 2: Create XPS Document
Шаг 2: Создайте XPS Document  
Создайте новый объект `XpsDocument`. Это основной контейнер, который будет содержать все страницы, пути и ресурсы.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Step 3: Define the Tiled Image Path
Шаг 3: Определите путь к мозаичному изображению  
Поместите изображение, которое вы хотите замостить (например, `R08LN_NN.jpg`), в каталог, указанный в `dataDir`. Это изображение будет использоваться в качестве шаблона кисти.

### Step 4: Add Tiled Image
Шаг 4: Добавьте мозаичное изображение  
Создайте прямоугольный путь и заполните его `XpsImageBrush`. Установив режим мозаики в `Tile`, изображение будет повторяться по всему прямоугольнику.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Step 5: Save the Document
Шаг 5: Сохраните документ  
Сохраните XPS‑файл на диск. Выходной файл будет содержать мозаичное изображение, которое вы только что определили.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Повторяйте эти шаги каждый раз, когда нужно **добавить мозаичное изображение** на другие страницы или формы в том же XPS документе.

## Common Issues and Solutions
Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| Изображение не отображается | Убедитесь, что путь к файлу (`dataDir + "R08LN_NN.jpg"`) правильный и изображение доступно. |
| Шаблон мозаики выглядит растянутым | Отрегулируйте значения исходного и конечного `Rectangle2D`, чтобы контролировать размер мозаики. |
| Прозрачность не действует | Убедитесь, что непрозрачность кисти установлена **после** конфигурации режима мозаики. |

## Frequently Asked Questions

### Is Aspose.Page compatible with all Java versions?
Совместима ли Aspose.Page со всеми версиями Java?  
Aspose.Page разработана для работы с различными версиями Java. Проверьте совместимость в документации [здесь](https://reference.aspose.com/page/java/).

### Can I use Aspose.Page for commercial projects?
Могу ли я использовать Aspose.Page в коммерческих проектах?  
Да, Aspose.Page предлагает коммерческие лицензии. Приобрести их можно [здесь](https://purchase.aspose.com/buy).

### Is there a free trial available?
Доступна ли бесплатная пробная версия?  
Да, изучите возможности Aspose.Page с бесплатной пробной версией [здесь](https://releases.aspose.com/).

### Where can I find community support and discussions?
Где я могу найти поддержку сообщества и обсуждения?  
Взаимодействуйте с сообществом Aspose.Page на [форуме](https://forum.aspose.com/c/page/39).

### How can I obtain a temporary license for Aspose.Page?
Как получить временную лицензию для Aspose.Page?  
Получить временную лицензию можно [здесь](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2025-12-28  
**Тестировано с:** Aspose.Page for Java 24.12 (latest)  
**Автор:** Aspose