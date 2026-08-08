---
date: 2026-06-30
description: Scopri come creare un documento postscript .NET e aggiungere rettangoli
  usando Aspose.Page per .NET. Guida passo‑passo con esempi di codice.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Aggiungi rettangolo a PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Crea documento PostScript .NET – Aggiungi rettangolo Aspose.Page
url: /it/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere un Rettangolo a PostScript (PS) con Aspose.Page per .NET

## Introduzione

Aspose.Page for .NET è una libreria che consente la creazione e la manipolazione di file PostScript, EPS e XPS in modo programmatico. Se stai cercando di **creare un documento postscript .net**, questo tutorial ti guida nell'aggiungere rettangoli a un documento PostScript usando Aspose.Page, fornendoti una solida base per la generazione di grafica più ricca.

## Risposte Rapide
- **Quale libreria è necessaria?** Aspose.Page per .NET.  
- **Posso creare un documento PostScript da zero?** Sì – l'API consente di costruire file PS programmaticamente.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è necessaria una licenza per la produzione.  
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti per forme di base.

## Cos'è la creazione di un documento postscript .net?
Creare un documento PostScript in .NET significa generare programmaticamente un file `.ps` che descrive il contenuto della pagina—testo, grafica o forme—utilizzando l'API Aspose.Page. Questo approccio è ideale per la generazione di grafica lato server, la creazione automatizzata di report o qualsiasi scenario in cui è necessario un controllo preciso sul formato di output.

## Perché usare Aspose.Page per .NET?
Aspose.Page supporta **oltre 30 primitive grafiche** e può generare file fino a **500 MB** senza caricare l'intero documento in memoria, offrendo rendering ad alte prestazioni su Windows, Linux e macOS. Ti offre pieno controllo su forme, colori e tratti, eliminando la necessità di scrivere codice PostScript a basso livello.

- **Controllo completo sulla grafica** – disegna forme, imposta colori e applica tratti senza occuparsi della sintassi PS a basso livello.  
- **Cross‑platform** – funziona su runtime Windows, Linux e macOS.  
- **Nessuna dipendenza esterna** – la libreria gestisce internamente tutta la generazione PS.  
- **Documentazione ricca & esempi** – inizia rapidamente.

## Prerequisiti

- **Libreria Aspose.Page per .NET** – scarica e installa da [qui](https://releases.aspose.com/page/net/).  
- **Ambiente di sviluppo** – Visual Studio, VS Code o qualsiasi IDE compatibile con .NET.

## Importare gli Spazi dei Nomi

Lo spazio dei nomi `Aspose.Page` espone le classi core di cui avrai bisogno, come `Document`, `Page`, `SolidBrush` e `Pen`. Importalo prima di iniziare a scrivere codice.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ora suddividiamo l'esempio in passaggi chiari e numerati.

## Passo 1: Configura la Cartella del Documento

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con la cartella in cui desideri salvare il file PS risultante.

## Passo 2: Crea lo Stream di Output per il Documento PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Questo stream punta a **AddRectangle_outPS.ps**. Sentiti libero di rinominare il file o modificare la posizione secondo necessità.

## Passo 3: Imposta le Opzioni di Salvataggio e Crea il Documento PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Qui indichiamo ad Aspose.Page di utilizzare una dimensione di pagina A4 e di creare un documento a pagina singola.

## Passo 4: Aggiungi un Rettangolo Riempito

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

## Passo 5: Aggiungi un Rettangolo Contornato

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Un secondo rettangolo viene creato più in basso nella pagina, questa volta con un tratto rosso di 3 punti.

## Passo 6: Chiudi la Pagina e Salva il Documento

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Chiudere la pagina finalizza il disegno, e `Save()` scrive il file PS su disco.

## Come creare un documento postscript .net?
`Document` è la classe principale che rappresenta un file PostScript in Aspose.Page. `SaveOptions` specifica impostazioni come la dimensione della pagina e il formato di output per il documento. Carica l'oggetto `Document`, configura `SaveOptions` per una pagina A4, disegna le tue forme con `SolidBrush` o `Pen`, quindi chiama `document.Save()` — l'intero flusso di lavoro richiede solo poche righe di codice e funziona su qualsiasi runtime .NET supportato. Questo modello ti consente di generare file PostScript pienamente conformi senza toccare la sintassi PS grezza.

## Come generare un file postscript
Usa la classe `SaveOptions` di Aspose.Page per specificare il formato di output come PostScript (`SaveFormat.PS`). La libreria trasmette il contenuto direttamente a un file o a uno stream di memoria, consentendoti di generare documenti di grandi dimensioni in modo efficiente senza un consumo eccessivo di memoria.

## Problemi Comuni & Suggerimenti

- **Percorso file errato** – Assicurati che `dataDir` termini con un separatore di percorso (`\\` o `/`) o utilizza `Path.Combine`.  
- **Licenza mancante** – In un ambiente di produzione, applica la tua licenza Aspose prima di creare il documento per evitare filigrane di valutazione.  
- **Visibilità del colore** – Se il rettangolo appare vuoto, verifica che i colori del pennello o della penna contrastino con lo sfondo della pagina.

## Domande Frequenti

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

**Ultimo Aggiornamento:** 2026-06-30  
**Testato Con:** Aspose.Page 24.12 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Correlati

- [Come Creare un Documento PostScript con Aspose.Page per .NET](/page/net/document-creation/create-postscript-document/)
- [Aggiungi Immagine a un Documento PostScript (PS) con Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Aggiungi Testo a un Documento PostScript (PS) con Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}