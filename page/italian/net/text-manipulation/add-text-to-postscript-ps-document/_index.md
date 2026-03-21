---
date: 2026-03-21
description: Scopri come compilare e aggiungere testo ai documenti PS utilizzando
  Aspose.Page per .NET. Guida passo‑passo con esempi di codice.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Come riempire il testo nei documenti PostScript (PS) con Aspose.Page
url: /it/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come riempire testo in documenti PostScript (PS) con Aspose.Page

## Introduzione

Se hai bisogno di **how to fill text** all'interno di un file PostScript (PS), Aspose.Page per .NET lo rende semplice. Che tu stia generando report, fatture o grafiche personalizzate, aggiungere e formattare il testo è un requisito fondamentale. In questo tutorial percorreremo l'intero processo—from setting up the environment to saving the final PS document—così potrai aggiungere testo ai file PS nelle tue applicazioni .NET con sicurezza.

## Risposte rapide
- **Che cosa significa “fill text”?** Renderizza i caratteri usando un pennello solido, dipingendo i glifi direttamente sulla pagina.  
- **Posso usare font personalizzati?** Sì—Aspose.Page supporta font personalizzati tramite la funzionalità `add custom font ps`.  
- **Come salvo il documento PS?** Chiama `document.Save()` dopo aver chiuso la pagina; questo scrive il file su disco (`save ps document`).  
- **È supportato “fill and stroke text”?** Assolutamente; usa `FillAndStrokeText` per applicare sia il riempimento che il contorno.  
- **Quali versioni di .NET sono richieste?** Qualsiasi .NET Framework 4.5+ o runtime .NET Core/5/6+.

## Che cos'è “how to fill text” in un documento PS?

Riempire il testo significa dipingere i caratteri con un colore solido (o pennello) senza contorno. In PostScript, è analogo all'operatore `fill`. Aspose.Page astrae questo in metodi facili da usare come `FillText` e `FillAndStrokeText`.

## Perché usare Aspose.Page per aggiungere custom font ps?

- **Supporto completo dei font** – i font di sistema e i font TrueType/OpenType esterni funzionano subito.  
- **Posizionamento preciso** – controlli le coordinate X/Y, la dimensione e lo stile.  
- **Stile ricco** – combina riempimenti, contorni e penne per effetti come “fill and stroke text”.  
- **Cross‑platform** – funziona su Windows, Linux e macOS con la stessa API.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Aspose.Page for .NET** – scarica la libreria dalla [documentazione Aspose.Page .NET](https://reference.aspose.com/page/net/).  
- **Document Directory** – una cartella sul tuo computer dove risiederanno i file PS di origine e di output (indicata come *Your Document Directory* nel codice).  
- **Fonts Folder** – una sotto‑cartella che contiene tutti i font personalizzati che intendi usare.

## Importa gli spazi dei nomi

First, import the required namespaces so the compiler knows where to find the classes we’ll use:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Guida passo‑passo

### Passo 1: Crea lo stream di output per il documento PS  

Apriamo un `FileStream` che conterrà il file PS generato, configuriamo `PsSaveOptions` per puntare alla nostra cartella di font personalizzati e istanziamo un `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Consiglio professionale:** Mantieni il blocco `using` per garantire che lo stream venga chiuso automaticamente, il che finalizza anche il file PS (`save ps document`).

### Passo 2: Riempire il testo con un font di sistema  

Qui dimostriamo l'operazione di base **how to fill text** usando il font integrato *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Passo 3: Riempire il testo con un font personalizzato  

Se ti serve un aspetto specifico, carica un font personalizzato dalla cartella dei font usando `ExternalFontCache.FetchDrFont`. Questo soddisfa il requisito **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Passo 4: Contornare (Stroke) il testo con un font di sistema  

Il contorno disegna la sagoma del glifo. Combinalo con un riempimento per ottenere l'effetto “fill and stroke”.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Perché è importante:** La chiamata `FillAndStrokeText` mostra come **fill and stroke text** in un unico passaggio, offrendoti un controllo tipografico più ricco.

### Passo 5: Contornare il testo con un font personalizzato  

La stessa tecnica di contorno funziona con qualsiasi font personalizzato che hai caricato.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Passo 6: Chiudere la pagina e salvare il documento  

Concludere è semplice: chiudi la pagina corrente e invoca `Save()` per scrivere il file PS su disco.

```csharp
document.ClosePage();
document.Save();
}
```

> **Risultato:** Troverai `AddText_outPS.ps` in *Your Document Directory*, contenente sia testo riempito che contornato renderizzato con font di sistema e personalizzati.

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Font personalizzato non trovato** | Verifica che il file del font (.ttf/.otf) esista nella cartella indicata da `AdditionalFontsFolders`. |
| **Il testo appare nella posizione sbagliata** | Regola le coordinate X/Y passate a `FillText`/`OutlineText`. Ricorda che PostScript usa i punti (1/72 di pollice). |
| **I colori appaiono diversi** | Assicurati di usare `SolidBrush` o `Pen` con i valori corretti di `Color`. |
| **Il documento non si salva** | Conferma che il blocco `using` termini senza eccezioni e che l'applicazione abbia i permessi di scrittura sulla cartella di destinazione. |

## Domande frequenti

**D: Posso usare Aspose.Page con altre librerie .NET?**  
R: Sì, Aspose.Page si integra perfettamente con altri componenti .NET, permettendoti di combinare librerie PDF, immagine o grafico nella stessa soluzione.

**D: I font personalizzati sono essenziali per questo processo?**  
R: Sebbene i font di sistema funzionino bene, i font personalizzati ti offrono piena libertà di design e sono utili quando è necessaria una tipografia specifica del brand.

**D: Aspose.Page è adatto per l'elaborazione di documenti su larga scala?**  
R: Assolutamente. La libreria è ottimizzata per scenari ad alto volume e può gestire migliaia di file PS in modo efficiente.

**D: Posso modificare la posizione del testo nel documento PS?**  
R: Certamente—basta cambiare i valori numerici X/Y nelle chiamate a `FillText` o `OutlineText`.

**D: Dove posso cercare assistenza per domande relative ad Aspose.Page?**  
R: Visita il [Forum Aspose.Page](https://forum.aspose.com/c/page/39) per entrare in contatto con la community e ottenere aiuto da esperti.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-03-21  
**Testato con:** Aspose.Page 24.11 for .NET  
**Autore:** Aspose