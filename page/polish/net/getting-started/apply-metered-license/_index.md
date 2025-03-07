---
title: Zastosuj licencję licznikową z Aspose.Page dla .NET
linktitle: Zastosuj licencję licznikową
second_title: Aspose.Page API .NET
description: Poznaj bezproblemową integrację Aspose.Page dla .NET dzięki temu przewodnikowi krok po kroku dotyczącemu stosowania licencji licznikowej. Bez wysiłku optymalizuj przetwarzanie dokumentów.
weight: 10
url: /pl/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zastosuj licencję licznikową z Aspose.Page dla .NET

## Wstęp

Odblokuj pełny potencjał Aspose.Page dla .NET poprzez zastosowanie licencji taryfowej. Ten samouczek poprowadzi Cię przez proces konfigurowania i stosowania licencji taryfowej, zapewniając płynne i zoptymalizowane wykorzystanie tej potężnej biblioteki .NET.

## Warunki wstępne

Zanim przejdziesz do kolejnych kroków, upewnij się, że spełnione są następujące wymagania wstępne:

-  Ważna licencja Aspose.Page dla .NET: Możesz ją uzyskać[zakup.aspose.com](https://purchase.aspose.com/buy).
-  Zainstalowana biblioteka Aspose.Page: zobacz[dokumentacja](https://reference.aspose.com/page/net/) w celu uzyskania instrukcji instalacji.
- Środowisko programistyczne .NET: Upewnij się, że na komputerze skonfigurowano działające środowisko .NET.

## Importuj przestrzenie nazw

W swoim projekcie .NET zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Page:

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

## Krok 1: Ustaw mierzone klucze publiczne i prywatne

 Zainicjuj`Aspose.Page.Metered` class i ustaw mierzone klucze publiczne i prywatne. Zastępować`<type public key here>` I`<type private key here>` z twoimi prawdziwymi kluczami.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Krok 2: Załaduj plik EPS i utwórz dokument

 Określ ścieżkę do pliku EPS i utwórz strumień, aby przeczytać jego zawartość. Następnie utwórz instancję`PsDocument` zajęcia ze strumienia.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Krok 3: Konwertuj EPS na obraz PNG

 Stworzyć`ImageDevice` do konwersji pliku EPS na obraz PNG. Zapisz plik EPS jako obraz, korzystając z`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Krok 4: Pobierz bajty obrazu

Pobierz bajty obrazu, gdzie każda tablica bajtów reprezentuje jedną stronę. W tym przypadku mamy jedną stronę.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Krok 5: Zapisz bajty obrazu do pliku

Zapisz bajty obrazu do pliku, zapewniając pomyślną konwersję z EPS do PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Krok 6: Sprawdź licencję taryfową

Sprawdź wizualnie, czy licencja licznikowa została pomyślnie zastosowana. Jeśli wynikowy obraz nie zawiera czerwonego komunikatu oceny, oznacza to, że licencja taryfowa została zastosowana bez żadnych problemów.

Teraz jesteś gotowy, aby wykorzystać pełne możliwości Aspose.Page dla .NET z licencją licznikową!

## Wniosek

Ten przewodnik krok po kroku wyposażył Cię w wiedzę niezbędną do bezproblemowego zastosowania licencji licznikowej przy użyciu Aspose.Page dla .NET. Zwiększ swoje możliwości przetwarzania dokumentów i poznaj szerokie funkcje oferowane przez tę potężną bibliotekę.

## Często zadawane pytania

### P1: Jak uzyskać licencję licznikową dla Aspose.Page dla .NET?

 Odpowiedź 1: Odwiedź[zakup.aspose.com](https://purchase.aspose.com/buy) nabyć ważną licencję.

### P2: Gdzie mogę znaleźć dokumentację Aspose.Page dla .NET?

 A2: Patrz[Aspose.Strona .NET](https://reference.aspose.com/page/net/) za obszerną dokumentację.

### P3: Czy istnieje forum do dyskusji i wsparcia Aspose.Page?

 A3: Tak, odwiedź[forum](https://forum.aspose.com/c/page/39) nawiązać kontakt ze społecznością i poprosić o pomoc.

### P4: Czy przed zakupem mogę wypróbować Aspose.Page dla .NET?

 A4: Absolutnie! Uzyskaj dostęp do bezpłatnego okresu próbnego pod adresem[Tutaj](https://releases.aspose.com/).

### P5: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?

 A5: Odwiedź[licencja tymczasowa/](https://purchase.aspose.com/temporary-license/) w celu uzyskania licencji tymczasowej.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
