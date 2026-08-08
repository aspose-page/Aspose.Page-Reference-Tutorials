---
date: 2026-03-26
description: Dowiedz się, jak tworzyć dokumenty PostScript w .NET i dodawać przezroczysty
  obraz przy użyciu Aspose.Page. Ten przewodnik krok po kroku obejmuje wymagania wstępne,
  kod oraz wskazówki.
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: Utwórz dokument PostScript w .NET z przezroczystym obrazem (Aspose.Page)
url: /pl/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument PostScript .NET z przezroczystym obrazem (Aspose.Page)

## Introduction

W tym samouczku dowiesz się, **jak utworzyć dokument PostScript .NET** i osadzić przezroczysty PNG przy użyciu Aspose.Page dla .NET. Dodawanie przezroczystych obrazów pozwala tworzyć bogatszą, warstwową grafikę — idealną do znaków wodnych, nakładek lub makiet UI wewnątrz pliku PS. Przejdziemy krok po kroku, od konfiguracji środowiska po renderowanie zarówno nieprzezroczystych, jak i przezroczystych obrazów.

## Quick Answers
- **What does Aspose.Page do?** Dostarcza w pełni funkcjonalne API do generowania, edytowania i renderowania dokumentów PostScript (PS) i XPS w .NET.  
- **Can I add transparent PNGs?** Tak — użyj `DrawTransparentImage`, aby kontrolować krycie.  
- **Which .NET versions are supported?** Wszystkie najnowsze .NET Framework, .NET Core oraz wydania .NET 5/6.  
- **Do I need a license?** Darmowa wersja próbna działa do oceny; licencja jest wymagana w produkcji.  
- **How long does implementation take?** Około 10‑15 minut dla podstawowego przykładu.

## Prerequisites

Before we dive in, make sure you have:

- **Aspose.Page for .NET** – download it from the [download link](https://releases.aspose.com/page/net/).  
- Folder, w którym przechowasz dokument PS oraz obraz, który chcesz osadzić.  
- Przezroczysty PNG (np. `mask1.png`), który będzie użyty jako warstwa przezroczysta.

## Import Namespaces

First, import the namespaces that contain the classes we’ll need. This gives us access to the PS document model, graphics utilities, and basic .NET drawing types.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Document Directory

Define the path where the source image and the output PS file will live. Replace the placeholder with the actual path on your machine.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

We’ll write the generated PS content to a file stream. This stream is later passed to the `PsDocument` constructor.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## Step 3: Set Save Options and Background Color

Configure `PsSaveOptions` to define how the file is saved. Setting a background color is useful when you want a solid canvas behind transparent elements.

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## Step 4: Create a New 1‑Paged PS Document

Create the document using the stream and options defined above. The `false` flag tells Aspose.Page not to automatically close the stream.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Write Graphics Save and Translate

Before drawing, we save the current graphics state and translate the origin so that our images appear at the desired location on the page.

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## How to add transparent image to a PostScript document

### Step 6: Add Opaque RGB Image

First we add the same PNG as a normal opaque image. This demonstrates the visual difference when we later apply transparency.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### Step 7: Add Transparent Image

Now we use `DrawTransparentImage` to render the PNG with an opacity value. The third parameter (`255`) represents full opacity; lower values increase transparency. This is where we **set image transparency .NET**.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **Pro tip:** To make the image 50 % transparent, pass `128` instead of `255`.

## Step 8: Write Graphics Restore and Close Page

After drawing, restore the previous graphics state and close the page to finalize the content.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Step 9: Save the Document

Finally, persist the PS file to disk.

```csharp
document.Save();
```

By following these steps you have **created a PostScript document .NET** that contains both an opaque and a transparent image, showcasing how to **draw transparent image C#** with Aspose.Page.

## Why use Aspose.Page for transparency effects?

- **Full control** over graphics state, matrices, and opacity levels.  
- **No external dependencies**—everything runs inside pure .NET code.  
- **Cross‑platform** support lets you generate PS files on Windows, Linux, or macOS.

## Common Pitfalls & Troubleshooting

| Problem | Rozwiązanie |
|-------|----------|
| Obraz jest w pełni nieprzezroczysty mimo użycia `DrawTransparentImage` | Upewnij się, że wartość alfa (trzeci argument) jest mniejsza niż `255`. |
| Plik PS wyświetla pustą stronę | Sprawdź, czy ustawiono kolor tła i czy ścieżka strumienia jest prawidłowa. |
| Wyjątek “File not found” | Ponownie sprawdź `dataDir` oraz czy `mask1.png` istnieje w tym folderze. |

## Frequently Asked Questions

**Q: Can I use other image formats besides PNG for transparency?**  
A: Tak — Aspose.Page obsługuje PNG, GIF i TIFF do renderowania przezroczystości.

**Q: Is Aspose.Page compatible with the latest .NET framework?**  
A: Absolutnie. Biblioteka jest regularnie aktualizowana pod .NET 6, .NET 7 i nowsze wersje.

**Q: Can I apply transparency to an existing PS document?**  
A: Tak. Otwórz dokument przy pomocy `PsDocument`, dodaj nową stronę lub zmodyfikuj istniejącą, a następnie użyj tego samego podejścia `DrawTransparentImage`.

**Q: What advantages does Aspose.Page offer over generic graphics libraries?**  
A: Jest specjalnie zaprojektowany dla PS/XPS, oferując precyzyjną kontrolę nad grafiką wektorową, czcionkami i obsługą obrazów bez potrzeby pełnego silnika renderującego.

**Q: Are there limits to the transparency level I can set?**  
A: Nie. Możesz określić dowolną wartość alfa od `0` (całkowicie przezroczysty) do `255` (w pełni nieprzezroczysty).

## Conclusion

We’ve demonstrated how to **create a PostScript document .NET** and embed both opaque and transparent images using Aspose.Page. This technique opens the door to sophisticated document layouts, watermarking, and layered graphics—all generated programmatically from C#.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}