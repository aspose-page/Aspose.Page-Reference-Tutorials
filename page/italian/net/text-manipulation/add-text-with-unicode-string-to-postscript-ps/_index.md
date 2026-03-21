---
date: 2026-03-21
description: Scopri come creare documenti PostScript in C# con testo Unicode usando
  Aspose.Page per .NET – un modo rapido per migliorare la manipolazione dei documenti.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Crea documento PostScript in C# con testo Unicode – Aspose.Page
url: /it/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere Testo con Stringa Unicode a PostScript (PS) con Aspose.Page

## Introduzione

Se hai bisogno di **create a PostScript document C#** e incorporare caratteri Unicode, Aspose.Page per .NET rende il processo semplice. In questo tutorial percorreremo un esempio completo e pratico che mostra come aggiungere testo giapponese (o qualsiasi stringa Unicode) a un file PS, scegliere un font personalizzato e salvare il risultato. Alla fine, avrai uno snippet riutilizzabile da inserire in qualsiasi progetto C#.

## Risposte Rapide
- **Di cosa tratta questo tutorial?** Aggiungere testo Unicode a un file PostScript usando Aspose.Page in C#.
- **Quale libreria è necessaria?** Aspose.Page per .NET (ultima versione).
- **Ho bisogno di un font speciale?** Qualsiasi font TrueType/OpenType che supporti l'intervallo Unicode desiderato, ad esempio *Arial Unicode MS*.
- **Quante righe di codice?** Circa 30 righe, suddivise in passaggi chiari.
- **È necessaria una licenza?** Una licenza temporanea funziona per la valutazione; è necessaria una licenza completa per la produzione.

## Cos'è “create postscript document c#”?

Creare un documento PostScript in C# significa generare programmaticamente un file .ps che segue le specifiche del linguaggio PostScript. Aspose.Page astrae i dettagli di basso livello, permettendoti di concentrarti sul contenuto come testo, grafica e font.

## Perché usare Aspose.Page per testo Unicode?
- **Full Unicode support** – renderizza caratteri di qualsiasi lingua senza codifica manuale.
- **Device‑independent** – lo stesso codice funziona per output PS, EPS e PDF.
- **No external dependencies** – la libreria gestisce il caricamento dei font e la mappatura dei glifi internamente.

## Prerequisiti

- Familiarità di base con C# e lo sviluppo .NET.
- Libreria Aspose.Page per .NET installata. Puoi scaricarla dalla [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Una cartella contenente i font che intendi usare (ad esempio *Arial Unicode MS*).

## Importare Namespace

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Passo 1: Configurare la Directory del Documento e la Cartella dei Font

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Passo 2: Creare lo Stream di Output per il Documento PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Passo 3: Aggiungere Testo Unicode con Font Personalizzato

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Passo 4: Chiudere la Pagina Corrente

```csharp
document.ClosePage();
```

## Passo 5: Finalizzare e Salvare il Documento

```csharp
document.Save();
```

## Problemi Comuni e Soluzioni

- **Font not found** – Assicurati che il percorso `AdditionalFontsFolders` punti alla cartella contenente i file .ttf/.otf e che il nome del font corrisponda esattamente.
- **Garbage characters** – Verifica che la stringa di origine sia codificata come UTF‑8 nel tuo file sorgente C# (usa `#pragma warning disable 1591` se necessario).
- **File not created** – Controlla i permessi di scrittura su `dataDir` e che lo stream sia correttamente smaltito (il blocco `using` gestisce questo).

## Domande Frequenti

**Q: Posso usare Aspose.Page per .NET con altri linguaggi di programmazione?**  
A: Aspose.Page è progettato principalmente per .NET, ma esistono equivalenti Java disponibili.

**Q: Come ottengo una licenza temporanea per Aspose.Page per .NET?**  
A: Visita [Temporary License](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea.

**Q: Esiste un forum della community per le discussioni su Aspose.Page?**  
A: Sì, visita il [Aspose.Page forum](https://forum.aspose.com/c/page/39) per il supporto della community.

**Q: Quali formati può gestire Aspose.Page per .NET?**  
A: Aspose.Page supporta vari formati, tra cui XPS, PS, EPS, PDF e altri.

**Q: Posso personalizzare l'aspetto del testo aggiunto?**  
A: Sì, puoi personalizzare il font, la dimensione, il colore e altre proprietà del testo in Aspose.Page.

## Conclusione

In questo tutorial abbiamo dimostrato come **create a PostScript document C#** e incorporare testo Unicode usando Aspose.Page. Seguendo i passaggi sopra, potrai integrare rapidamente il rendering di testo multilingue in qualsiasi applicazione .NET, avendo pieno controllo sulla generazione e sul layout del documento.

---

**Ultimo aggiornamento:** 2026-03-21  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}