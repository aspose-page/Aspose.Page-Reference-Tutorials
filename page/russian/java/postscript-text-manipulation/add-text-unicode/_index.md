---
date: 2025-12-17
description: Узнайте, как добавить Unicode‑текст в Java PostScript с помощью Aspose.Page
  — пошаговое руководство по простому добавлению Unicode‑строк.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Как добавить Unicode‑текст в Java PostScript с помощью Aspose.Page
url: /ru/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить Unicode‑текст в Java PostScript с помощью Aspose.Page

## Introduction
Если вы задаётесь вопросом, **как добавить Unicode** символы в Java‑based PostScript (или XPS) рабочий процесс, вы попали в нужное место. В этом руководстве мы пройдём по точным шагам, необходимым для встраивания Unicode‑строк с помощью библиотеки Aspose.Page для Java. К концу руководства вы сможете вставлять любой язык‑специфичный текст — арабский, китайский, эмодзи, что угодно — непосредственно в ваш PostScript‑вывод.

## Quick Answers
- **Какая библиотека нужна?** Aspose.Page for Java  
- **Могу ли я добавить скрипты справа налево?** Да, установите уровень Bidi, как показано в коде  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия требуется для продакшн  
- **Какой IDE лучше всего подходит?** Любой Java IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **Код кроссплатформенный?** Абсолютно — работает на Windows, macOS или Linux

## What is “how to add Unicode” in the context of PostScript?
Что означает «как добавить Unicode» в контексте PostScript?  
Добавление Unicode означает вставку символов, представленных кодовыми точками за пределами базового диапазона ASCII. Aspose.Page абстрагирует детали низкоуровневого кодирования, позволяя сосредоточиться на содержимом текста и его визуальном размещении.

## Why use Aspose.Page for Unicode text?
- **Полная поддержка Unicode** — Обрабатывает сложные скрипты, лигатуры и языки справа налево.  
- **Отсутствие внешних зависимостей** — Нет необходимости вручную управлять файловыми шрифтами; API работает с системными шрифтами.  
- **Простой API** — Достаточно нескольких вызовов методов, чтобы отобразить многоязычный текст.

## Prerequisites
Прежде чем мы начнём, убедитесь, что у вас готовы следующие элементы:

1. **Java Development Kit (JDK)** — Любая современная версия (8 или новее).  
2. **Aspose.Page for Java** — Скачайте и установите библиотеку по [download link](https://releases.aspose.com/page/java/).  
3. **IDE по вашему выбору** — IntelliJ IDEA, Eclipse или любой другой Java IDE, который вам нравится.

## Import Packages
Добавьте необходимые классы Aspose.Page в ваш Java‑файл:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
Создайте новый Java‑проект, добавьте JAR‑файл Aspose.Page в путь сборки проекта и создайте папку, куда будет сохраняться сгенерированный XPS‑файл. Эта папка позже будет использоваться как `dataDir`.

## Step 2: Initialize XPS Document
Создайте пустой XPS‑документ, который будет содержать контент:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
Теперь действительно добавим Unicode‑строку. Пример ниже записывает обратную фразу «AVAJ rof SPX.esopsA», которая содержит только ASCII‑символы, но вы можете заменить её любой Unicode‑строкой (например, арабским «مرحبا» или китайским «你好»).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Совет:** Чтобы правильно отобразить языки справа налево, установите `glyphs.setBidiLevel(1);`. Для языков слева направо эту строку можно опустить.

## Step 4: Save the Document
Сохраните XPS‑файл на диск:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

После запуска программы откройте сгенерированный `AddEncodingText_out.xps` в любом XPS‑просмотрщике, чтобы увидеть отрисованный Unicode‑текст в указанных координатах.

## Common Issues and Solutions
| Проблема | Причина | Решение |
|----------|----------|----------|
| Текст отображается в виде квадратов | Шрифт не найден или не поддерживает символы | Используйте шрифт, включающий необходимые глифы (например, “Arial Unicode MS”) |
| Текст справа налево отображается слева направо | Не установлен уровень Bidi | Вызовите `glyphs.setBidiLevel(1);` |
| Файл не сохранён | Путь `dataDir` недействителен или отсутствуют права записи | Убедитесь, что каталог существует и приложение имеет права записи |

## Frequently Asked Questions
### Могу ли я использовать Aspose.Page для Java с другими языками программирования?
Aspose.Page в основном разработан для Java, но Aspose предоставляет библиотеки для различных языков программирования.

### Доступна ли бесплатная пробная версия?
Да, вы можете получить бесплатную пробную версию Aspose.Page [здесь](https://releases.aspose.com/).

### Где я могу найти поддержку и обсуждения по Aspose.Page?
Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки и обсуждений.

### Как получить временную лицензию для Aspose.Page?
Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

### Какие стили шрифтов доступны в Aspose.Page?
Aspose.Page поддерживает стили шрифтов такие как Regular, Bold, Italic и BoldItalic.

## Conclusion
Теперь вы освоили **как добавить Unicode** текст в Java PostScript (XPS) документ с помощью Aspose.Page. Эта возможность открывает двери к многоязычной отчётности, интернационализированным счетам и любым сценариям, где требуются символы за пределами ASCII. Не стесняйтесь исследовать дополнительные возможности, такие как вращение текста, обрезка путей или встраивание пользовательских шрифтов — детали доступны в официальной [документации](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

---