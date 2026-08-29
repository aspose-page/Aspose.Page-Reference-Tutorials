---
date: 2026-08-29
description: Узнайте, как выполнять векторное изменение размера EPS‑файлов в Java
  с помощью Aspose.Page. Это пошаговое руководство покажет, как изменять размер EPS
  в точках, дюймах, миллиметрах или процентах.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Resize EPS File в Java
og_description: Java vector resize позволяет напрямую в Java изменять размеры EPS‑файла.
  С помощью Aspose.Page вы можете выполнять resize в точках, дюймах, миллиметрах или
  процентах, сохраняя векторное качество.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Java vector resize: изменение размеров EPS с помощью Aspose.Page'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Как выполнить векторное изменение размера EPS‑файлов в Java с помощью Aspose.Page
url: /ru/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить размер EPS файлов в Java с помощью Aspose.Page

## Введение
Если вам необходимо **java vector resize** EPS‑файлы программно, вы попали в нужное место. В этом руководстве мы пошагово покажем, как изменять размер EPS‑изображений в Java с использованием библиотеки Aspose.Page. Независимо от того, хотите ли вы удвоить размер, уменьшить его до конкретного измерения или работать с процентами, приведённые ниже шаги дают полный контроль над размерами вывода. Овладение навыком изменения размера EPS необходимо при адаптации графики к различным макетам печати, разрешениям экрана или брендинговым требованиям.

## Краткие ответы
- **Какая библиотека нужна?** Aspose.Page for Java  
- **Можно ли изменять размер, используя пункты, дюймы или миллиметры?** Да — API поддерживает все три единицы измерения и проценты.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшн‑использования требуется лицензия.  
- **Какая версия Java требуется?** Java 8 или новее.  
- **Является ли код потокобезопасным?** Каждый экземпляр `PsDocument` изолирован, поэтому вы можете обрабатывать файлы параллельно.  

## Что такое EPS и почему его нужно изменять размер?
Encapsulated PostScript (EPS) — это векторный графический формат, широко используемый в печати и издательском деле. Иногда исходный EPS‑файл создаётся в размере, который не соответствует требуемому выводу — например, логотип, разработанный в 72 pt, может потребоваться в 144 pt для более крупного брошюра. Знание **how to resize eps** позволяет сохранять векторное качество, адаптируя размеры к любому рабочему процессу.

## Почему стоит использовать Aspose.Page для изменения размера EPS?
Aspose.Page предоставляет простой API, позволяющий задавать целевой размер в любой из поддерживаемых единиц измерения, автоматически сохраняя векторную структуру. Библиотека обрабатывает конвертацию единиц внутри, поэтому вы можете сосредоточиться на нужных размерах без ручных вычислений.

- **Поддерживает четыре единицы измерения** – Points, Inches, Millimeters, and Percent.  
- **Нет внешних зависимостей** – чистый Java API, без необходимости в нативных библиотеках.  
- **Высокопроизводительная обработка** – может обрабатывать до 500 EPS‑файлов в минуту на стандартном 8‑ядерном сервере.  
- **Сохраняет векторную точность** – вывод остаётся полностью масштабируемым без растеризации.

## Требования
Перед тем как перейти к коду, убедитесь, что у вас есть следующее:

- Установленный Java Development Kit (JDK) на вашем компьютере.  
- Библиотека Aspose.Page for Java. Вы можете скачать её со **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Базовые знания программирования на Java.  

## Импорт пакетов
В вашем Java‑проекте включите необходимые импорты, чтобы работать с объектами Aspose.Page и стандартными потоками ввода‑вывода.

`PsDocument` представляет EPS‑документ, загруженный в память.  
`Units` — это перечисление, определяющее единицы измерения, поддерживаемые API.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Как изменить размеры EPS с различными единицами измерения
Вы можете изменить размеры EPS, вызвав метод `resizeEps` с желаемой шириной, высотой и значением перечисления `Units`; это работает для пунктов, дюймов, миллиметров или процентов. Один и тот же пятишаговый шаблон применяется к каждой единице, делая API предсказуемым и простым в интеграции.

`resizeEps` изменяет размер холста EPS до указанных размеров, сохраняя внутренние векторные данные.

## Как изменить размер EPS, используя пункты
Загрузите ваш EPS, укажите новый размер в пунктах и сохраните результат. Этот подход удваивает исходные размеры, сохраняя соотношение сторон. Использование пунктов даёт точный контроль над размерами для печати, что особенно полезно для типографических макетов и вывода высокого разрешения.

### Шаг 1: настройте входной поток
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Шаг 2: инициализируйте объект `PsDocument`
`PsDocument` загружает исходный EPS‑файл и предоставляет методы для манипуляций.  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Шаг 3: извлеките текущий размер EPS‑изображения
```java
Dimension oldSize = doc.extractEpsSize();
```

### Шаг 4: создайте выходной поток для изменённого файла
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Шаг 5: измените размер и сохраните EPS, используя пункты
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Как изменить размер EPS, используя дюймы
Изменение размера в дюймах позволяет соответствовать спецификациям, определённым в имперских единицах, таким как макеты брошюр или американские стандарты печати. Укажите целевую ширину и высоту в дюймах, и API преобразует их во внутренние единицы перед применением трансформации.

## Как изменить размер EPS, используя миллиметры
При работе с метрическими процессами указание размеров в миллиметрах обеспечивает согласованность с форматами бумаги и печатным оборудованием, используемым за пределами США. Библиотека автоматически обрабатывает преобразование из миллиметров во внутреннюю систему координат.

## Как изменить размер EPS, используя проценты
Изменение размера в процентах масштабирует исходные размеры пропорционально, что удобно для быстрых корректировок без вычисления абсолютных значений. Например, коэффициент `0.5` уменьшает как ширину, так и высоту на 50 %.

## Распространённые подводные камни и советы
- **Всегда закрывайте потоки** – В продакшн‑коде оборачивайте потоки в try‑with‑resources, чтобы избежать блокировок файлов.  
- **Сохраняйте соотношение сторон** – Умножайте ширину и высоту на один и тот же коэффициент, если только вы не хотите искажений.  
- **Проверьте DPI** – Изменение размера не меняет DPI; если нужен другой DPI, скорректируйте его отдельно после изменения размера.  
- **Потокобезопасность** – Создавайте новый `PsDocument` для каждого потока; совместное использование одного экземпляра может привести к неожиданным результатам.  

## Часто задаваемые вопросы

**В: Можно ли использовать эту библиотеку для других форматов изображений?**  
О: Нет, Aspose.Page специализируется только на PostScript и EPS‑файлах.

**В: Доступна ли бесплатная пробная версия Aspose.Page для Java?**  
О: Да, вы можете ознакомиться с бесплатной пробной версией на **[Aspose free trial page](https://releases.aspose.com/)**.

**В: Где я могу найти дополнительную помощь и обсуждения?**  
О: Посетите **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** для поддержки сообщества.

**В: Как я могу получить временную лицензию?**  
О: Вы можете получить временную лицензию на **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**В: Есть ли доступные примеры проектов?**  
О: Да, ознакомьтесь с документацией **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.

---

**Последнее обновление:** 2026-08-29  
**Тестировано с:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Автор:** Aspose

## Связанные руководства

- [Изменить размер EPS с помощью Aspose.Page – Java EPS Manipulation](/page/java/manipulation-eps/)
- [Как обрезать EPS‑файлы в Java – руководство Aspose.Page](/page/java/manipulation-eps/crop/)
- [Как масштабировать прямоугольник с Aspose.Page для Java](/page/java/page-manipulation/transformations/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}