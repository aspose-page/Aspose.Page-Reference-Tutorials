---
date: 2025-12-13
description: Узнайте, как добавить текст на страницу ASP в Java, установить стиль
  шрифта в Java и как добавить Unicode‑текст с помощью Aspose.Page. Следуйте нашему
  пошаговому руководству.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: 'страница asp: добавить текст – Unicode в Java PostScript'
url: /ru/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode в Java PostScript

## Введение
Если вам нужно **asp page add text** в рабочем процессе Java PostScript с сохранением Unicode‑символов, вы попали по адресу. В этом руководстве мы пройдем процесс добавления Unicode‑текста, установки стиля шрифта и сохранения результата с использованием **Aspose.Page for Java**. К концу вы поймёте, как установить font style java и как эффективно добавлять unicode‑текст в ваших проектах.

## Быстрые ответы
- **Какая библиотека может добавлять Unicode‑текст в Java PostScript?** Aspose.Page for Java.  
- **Какой основной метод добавляет текст?** `doc.addGlyphs(...)` с объектом `XpsGlyphs`.  
- **Нужен ли специальный шрифт для Unicode?** Любой TrueType/OpenType шрифт, поддерживающий необходимые кодовые точки (например, Arial).  
- **Можно ли изменить стиль шрифта?** Да, используя `XpsFontStyle` (Regular, Bold, Italic и т.д.).  
- **Требуется ли лицензия для продакшна?** Да, для использования не в пробном режиме необходима действительная лицензия Aspose.Page.

## Что такое asp page add text?
`asp page add text` относится к процессу вставки строк текста в документ PostScript или XPS с использованием API Aspose.Page. API абстрагирует низкоуровневые команды PostScript, позволяя работать с объектами высокого уровня, такими как `XpsGlyphs`.

## Почему использовать Aspose.Page для установки font style java и добавления Unicode‑текста?
- **Полная поддержка Unicode** – Обрабатывает скрипты справа налево и сложные глифы.  
- **Простой API** – Однострочные вызовы для добавления текста и применения стилей.  
- **Кроссплатформенный** – Работает в любой среде, совместимой с Java.  
- **Без внешних зависимостей** – Не требуется дополнительных движков рендеринга.

## Предварительные требования
Прежде чем приступить к руководству, убедитесь, что у вас есть следующие предварительные требования:

1. **Java Development Kit (JDK)** – Убедитесь, что Java установлена на вашем компьютере.  
2. **Aspose.Page for Java** – Скачайте и установите библиотеку Aspose.Page по [download link](https://releases.aspose.com/page/java/).  
3. **Integrated Development Environment (IDE)** – Выберите предпочитаемую Java‑IDE, например IntelliJ IDEA или Eclipse.

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые пакеты для Aspose.Page. Добавьте следующие строки в ваш код:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Шаг 1: Настройка проекта
Создайте новый Java‑проект в вашей IDE и настройте структуру проекта. Убедитесь, что библиотека Aspose.Page включена в зависимости проекта.

## Шаг 2: Инициализация XPS‑документа
Начните с инициализации нового XPS‑документа в вашем проекте:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Шаг 3: Добавление Unicode‑текста
Теперь добавим Unicode‑текст в ваш XPS‑документ с помощью библиотеки Aspose.Page. Используйте следующий фрагмент кода:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Этот фрагмент кода добавляет Unicode‑текст **"AVAJ rof SPX.esopsA"** в XPS‑документ по координатам (400, 200) с указанным шрифтом и стилем. Обратите внимание, как вызов `setBidiLevel(1)` включает рендеринг справа налево для корректного отображения Unicode.

## Шаг 4: Сохранение документа
Сохраните полученный XPS‑документ, используя следующий код:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Заключение
Поздравляем! Вы успешно **asp page add text** и установили стиль шрифта в сценарии Java PostScript с использованием Aspose.Page. Этот метод предоставляет тонкий контроль над рендерингом и стилизацией Unicode, что делает его идеальным для интернационализированныхов, счетов и графики.

Не стесняйтесь изучать дополнительные возможности Aspose.Page в [documentation](https://reference.aspose.com/page/java/).

## Часто задаваемые вопросы

**Q:** Могу ли я использовать Aspose.Page for Java с другими языками программирования?  
**A:** Aspose.Page в основном разработан для Java, но Aspose предоставляет библиотеки для различных языков программирования.

**Q:** Доступна ли бесплатная пробная версия?  
**A:** Да, вы можете получить бесплатную пробную версию Aspose.Page [здесь](https://releases.aspose.com/).

**Q:** Где я могу найти поддержку и обсуждения Aspose.Page?  
**A:** Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки и обсуждений.

**Q:** Как получить временную лицензию для Aspose.Page?  
**A:** Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

**Q:** Какие стили шрифтов доступны в Aspose.Page?  
**A:** Aspose.Page поддерживает стили шрифтов, такие как Regular, Bold, Italic и BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2025-12-13  
**Тестировано с:** Aspose.Page for Java (latest)  
**Автор:** Aspose  

---