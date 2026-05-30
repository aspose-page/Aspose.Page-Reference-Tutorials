---
date: 2026-01-18
description: Impara a creare documenti PostScript in .NET e aggiungere rettangoli
  usando Aspose.Page per .NET. Guida passo‑passo con esempi di codice.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Crea documento PostScript .NET – Aggiungi rettangolo con Aspose.Page
url: /it/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi un rettangolo a PostScript (PS) con Aspose.Page per .NET

## Introduzione

Se stai cercando di **creare documento postscript .net**, Aspose.Page fornisce una soluzione potente per gestire i file PostScript. In questo tutorial, ti guideremo nell'aggiungere rettangoli a un documento PostScript usando Aspose.Page per .NET, fornendoti una solida base per la generazione di grafica più ricca.

## Risposte rapide
- **Quale libreria mi serve?** Aspose.Page for .NET.
- **Posso creare un documento PostScript da zero?** Sì – l'API consente di costruire file PS programmaticamente.
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita funziona per i test; è richiesta una licenza per la produzione.
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti per forme di base.

## Che cosa significa creare un documento postscript .net?
Creare un documento PostScript in .NET significa generare programmaticamente un file .ps che descrive il contenuto della pagina — testo, grafica o forme — usando l'API Aspose.Page. Questo approccio è ideale per la generazione di grafica lato server, la creazione automatizzata di report o qualsiasi scenario in cui è necessario un controllo preciso sul formato di output.

## Perché usare Aspose.Page per .NET?
- **Controllo completo sulla grafica** – disegna forme, imposta colori e applica tratti senza occuparsi della sintassi PS a basso livello.
- **Cross‑platform** – funziona su runtime Windows, Linux e macOS.
- **Nessuna dipendenza esterna** – la libreria gestisce internamente tutta la generazione PS.
- **Documentazione ricca & esempi** – inizia a lavorare rapidamente.

## Prerequisiti

- **Libreria Aspose.Page per .NET** – scarica e installa da [qui](https://releases.aspose.com/page/net/).
- **Ambiente di sviluppo** – Visual Studio, VS Code, o qualsiasi IDE compatibile con .NET.

## Importa gli spazi dei nomi

Prima di iniziare a scrivere codice, importa gli spazi dei nomi che espongono le classi necessarie:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ora suddividiamo l'esempio in passaggi chiari e numerati.

## Passo 1: Configura la directory del documento

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` con la cartella in cui desideri salvare il file PS risultante.

## Passo 2: Crea lo stream di output per il documento PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Questo stream punta a **AddRectangle_outPS.ps**. Sentiti libero di rinominare il file o cambiare la posizione secondo necessità.

## Passo 3: Imposta le opzioni di salvataggio e crea il documento PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Qui indichiamo ad Aspose.Page di utilizzare una dimensione di pagina A4 e di creare un documento a pagina singola.

## Passo 4: Aggiungi un rettangolo riempito

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definiamo un rettangolo a (250, 100) con larghezza 150 e altezza 100, impostiamo un pennello arancione e riempiamo la forma.

## Passo 5: Aggiungi un rettangolo contornato

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Un secondo rettangolo è creato più in basso nella pagina, questa volta con un tratto rosso di 3 punti.

## Passo 6: Chiudi la pagina e salva il documento

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Chiudere la pagina finalizza il disegno, e `Save()` scrive il file PS su disco.

## Problemi comuni e suggerimenti

- **Percorso file errato** – Assicurati che `dataDir` termini con un separatore di percorso (`\\` o `/`) o utilizza `Path.Combine`.
- **Licenza mancante** – In un ambiente di produzione, applica la tua licenza Aspose prima di creare il documento per evitare filigrane di valutazione.
- **Visibilità del colore** – Se il rettangolo appare vuoto, verifica che i colori del pennello o della penna contrastino con lo sfondo della pagina.

## Domande frequenti

**D:** Posso personalizzare i colori dei rettangoli?  
**R:** Assolutamente. Cambia i valori `Color.Orange` o `Color.Red` nei costruttori `SolidBrush` e `Pen` con qualsiasi `System.Drawing.Color` preferisci.

**D:** Aspose.Page è compatibile con altri formati di documento?  
**R:** Sì. Oltre a PostScript, Aspose.Page supporta anche la generazione di XPS ed EPS.

**D:** Come posso aggiungere testo allo stesso documento?  
**R:** Usa la classe `TextFragment` per posizionare il testo alle coordinate desiderate, quindi chiama `document.Draw(textFragment)`.

**D:** Dove posso trovare esempi aggiuntivi e la documentazione completa dell'API?  
**R:** Esplora la documentazione [qui](https://reference.aspose.com/page/net/) e unisciti alla community sul [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**D:** Posso provare Aspose.Page prima di acquistarlo?  
**R:** Sì, scarica una prova gratuita [qui](https://releases.aspose.com/). Per una valutazione estesa, considera una [licenza temporanea](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-01-18  
**Testato con:** Aspose.Page 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}