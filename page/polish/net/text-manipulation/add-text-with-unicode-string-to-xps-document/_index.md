---
date: 2026-03-21
description: Dowiedz się, jak dodać tekst Unicode do dokumentu XPS przy użyciu Aspose.Page
  dla .NET. Ten przewodnik pokazuje, jak utworzyć dokument XPS w C# oraz dodać tekst
  z ciągami Unicode przy użyciu Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Jak dodać tekst Unicode do dokumentu XPS przy użyciu Aspose.Page
url: /pl/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać tekst Unicode do dokumentu XPS przy użyciu Aspose.Page

## Introduction

Jeśli potrzebujesz **how to add unicode** znaków do pliku XPS, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię krok po kroku przez dokładne kroki potrzebne do **create XPS document C#**‑style przy użyciu Aspose.Page dla .NET i pokażemy możliwości **aspose page add text** z ciągiem Unicode. Po zakończeniu będziesz mieć w pełni funkcjonalny dokument XPS wyświetlający tekst Unicode od prawej do lewej (RTL) poprawnie.

## Quick Answers
- **Co obejmuje samouczek?** Dodawanie tekstu Unicode do dokumentu XPS przy użyciu Aspose.Page dla .NET.  
- **Jakiego języka użyto?** C# (kompatybilny z .NET Framework i .NET Core).  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić czcionkę lub rozmiar?** Tak – w przykładzie użyto Arial 20 pt, ale działa każda zainstalowana czcionka.  
- **Czy obsługa RTL jest włączona?** Ustawienie `BidiLevel = 1` włącza renderowanie od prawej do lewej dla ciągów Unicode.

## What is “how to add unicode” in XPS?

Dodawanie tekstu Unicode oznacza wstawianie znaków z dowolnego języka — arabskiego, hebrajskiego, chińskiego itd. — do dokumentu XPS. Klasa `XpsGlyphs` Aspose.Page obsługuje niskopoziomowe rozmieszczanie glifów, a właściwość `BidiLevel` kontroluje kierunek tekstu dla skryptów RTL.

## Why use Aspose.Page to add text?

- **Pełna integracja z .NET** – działa z .NET Framework, .NET Core, .NET 5/6+.  
- **Brak zewnętrznych zależności** – czysty kod zarządzany, bez interfejsu COM.  
- **Bogate wsparcie typografii** – czcionki, style, kolory i tekst dwukierunkowy.  
- **Wysoka wydajność** – szybko tworzy i zapisuje pliki XPS, idealne do generowania po stronie serwera.

## Prerequisites

- Podstawowa znajomość C# i programowania w .NET.  
- Visual Studio (dowolna aktualna wersja).  
- Aspose.Page for .NET library – download it from [here](https://releases.aspose.com/page/net/).

## Import Namespaces

Najpierw zaimportuj przestrzenie nazw, które dają dostęp do modelu XPS i narzędzi rysunkowych.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set up the Document – create XPS document C#

Utwórz nowy dokument XPS, który będzie zawierał tekst Unicode.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Step 2: Add Unicode Text – aspose page add text

Teraz dodajemy rzeczywisty ciąg Unicode. W tym przykładzie używamy czcionki Arial, rozmiaru 20, i pozycjonujemy tekst w (400 f, 200 f). `BidiLevel` równy 1 informuje renderer, aby traktował ciąg jako od prawej do lewej.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Step 3: Save the Document

Na koniec zapisujemy plik XPS na dysku.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Gratulacje! Pomyślnie dodałeś **how to add unicode** tekst do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Common Issues and Solutions

| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| Tekst wyświetla się jako zniekształcony | Czcionka nie obsługuje zakresu Unicode | Użyj czcionki zawierającej wymagane glify (np. Arial Unicode MS). |
| Tekst RTL nadal wyświetla się od lewej do prawej | `BidiLevel` nie ustawiono lub ustawiono na 0 | Upewnij się, że `glyphs.BidiLevel = 1;` dla skryptów RTL. |
| Plik nie został zapisany | Nieprawidłowa ścieżka `dataDir` | Sprawdź, czy katalog istnieje i aplikacja ma uprawnienia do zapisu. |

## Frequently Asked Questions

**P: Czy Aspose.Page jest kompatybilny z najnowszymi frameworkami .NET?**  
O: Tak, Aspose.Page jest regularnie aktualizowany, aby wspierać .NET Framework, .NET Core oraz .NET 5/6+.

**P: Czy mogę dostosować styl i rozmiar czcionki przy dodawaniu tekstu?**  
O: Oczywiście! Metoda `AddGlyphs` pozwala określić dowolną rodzinę czcionek, rozmiar oraz `FontStyle`, którego potrzebujesz.

**P: Gdzie mogę znaleźć dodatkową dokumentację dla Aspose.Page?**  
O: Dokumentację znajdziesz [here](https://reference.aspose.com/page/net/), zawierającą szczegółowe informacje o API.

**P: Czy istnieją darmowe zasoby, aby rozpocząć pracę z Aspose.Page?**  
O: Tak, przeglądaj forum społecznościowe pod adresem [Aspose.Page forum](https://forum.aspose.com/c/page/39), gdzie znajdziesz wskazówki, przykłady i wsparcie od innych użytkowników.

**P: Czy dostępna jest wersja próbna przed zakupem?**  
O: Oczywiście! Pobierz darmową wersję próbną z [here](https://releases.aspose.com/), aby ocenić bibliotekę.

---

**Ostatnia aktualizacja:** 2026-03-21  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}