---
date: 2026-07-19
description: Scopri come creare un documento XPS .NET e aggiungere un rettangolo usando
  Aspose.Page per .NET in una guida concisa passo‑passo.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Aggiungi rettangolo al documento XPS
og_description: Crea rapidamente un documento XPS .NET. Questo tutorial mostra come
  aggiungere un rettangolo a un file XPS usando Aspose.Page per .NET, con codice chiaro
  e consigli.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Crea documento XPS .NET – Aggiungi rettangolo con Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Crea documento XPS .NET – Aggiungi rettangolo con Aspose.Page
url: /it/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento XPS .NET – Aggiungi rettangolo con Aspose.Page

## Introduzione

In questo tutorial imparerai a **creare documento XPS .NET** e a disegnare un rettangolo al suo interno usando Aspose.Page per .NET. Che tu stia costruendo un motore di reporting, una fattura stampabile o un livello grafico personalizzato, la capacità di generare file XPS programmaticamente ti offre il pieno controllo sul layout e sulla fedeltà. Segui i passaggi qui sotto e avrai un file XPS pronto all'uso in pochi minuti.

## Risposte rapide
- **Qual è l'obiettivo principale?** Crea un documento XPS .NET e aggiungi una forma rettangolare.  
- **Quale libreria è necessaria?** Aspose.Page per .NET (scaricabile dal sito ufficiale).  
- **È necessaria una licenza per i test?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo richiede l'implementazione?** Circa 5‑10 minuti per un rettangolo di base.

## Cos'è Aspose.Page per .NET?
Aspose.Page per .NET è un'API ad alte prestazioni, completamente gestita, che consente agli sviluppatori di creare, modificare e renderizzare programmaticamente documenti XPS (XML Paper Specification) senza dipendere da componenti esterni. Offre un ricco modello di oggetti per disegnare forme, testo e immagini, e supporta funzionalità avanzate come la gestione del colore, la compressione e la conversione PDF, rendendola adatta a una vasta gamma di scenari di generazione di documenti.

## Perché usare Aspose.Page per creare documento XPS .NET?
Aspose.Page supporta **oltre 30 funzionalità XPS** — incluse grafiche vettoriali, layout del testo e gestione del colore — e può generare file fino a **500 MB** senza caricare l'intero documento in memoria. Questa capacità quantificata garantisce prestazioni fluide anche per lavori di stampa su larga scala.

## Prerequisiti

Prima di iniziare questo tutorial, assicurati di avere i seguenti prerequisiti pronti:

1. Libreria Aspose.Page per .NET: Assicurati di avere la libreria Aspose.Page per .NET installata nel tuo ambiente di sviluppo. Puoi scaricarla [qui](https://releases.aspose.com/page/net/).
2. Directory dei documenti: Configura una directory dove desideri archiviare i tuoi documenti XPS.

## Importa spazi dei nomi

Nella tua applicazione .NET, includi gli spazi dei nomi necessari per utilizzare le funzionalità di Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Come aggiungere un rettangolo a un documento XPS in .NET?

Carica il documento XPS, crea un oggetto `Graphics`, definisci un `RectangleF` con le dimensioni desiderate e chiama `DrawRectangle`. Questa sequenza disegna un rettangolo in una singola riga di codice e gestisce automaticamente il ridimensionamento DPI. Per pagine tipiche di formato A4, un rettangolo di 200 × 100 pt appare centrato senza calcoli aggiuntivi.

### Passo 1: Imposta la directory dei documenti

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Passo 2: Crea un nuovo documento XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Passo 3: Aggiungi un rettangolo

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Passo 4: Salva il documento

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Congratulazioni! Hai aggiunto con successo un rettangolo a un documento XPS usando Aspose.Page per .NET.

## Problemi comuni e suggerimenti

- **Font mancanti:** Assicurati che i font a cui fai riferimento siano installati sul server; altrimenti Aspose.Page sostituisce con un font predefinito, il che può alterare il layout.  
- **Documenti di grandi dimensioni:** Quando generi file più grandi di 200 MB, considera di chiamare `document.SaveOptions.Compress = true` per ridurre l'uso di memoria.  
- **Sistema di coordinate:** XPS utilizza punti (1/72 pollice). Ricorda di convertire i pixel in punti se lavori con dimensioni basate sullo schermo.

## Domande frequenti

**D: Aspose.Page è compatibile con tutte le applicazioni .NET?**  
R: Sì, Aspose.Page funziona senza problemi con applicazioni .NET desktop, web e cloud.

**D: Dove posso trovare la documentazione per Aspose.Page per .NET?**  
R: Il riferimento completo dell'API è disponibile [qui](https://reference.aspose.com/page/net/).

**D: Posso provare Aspose.Page per .NET gratuitamente prima di acquistare?**  
R: Sì, puoi ottenere una prova gratuita [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?**  
R: Visita [questo link](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea.

**D: Dove posso trovare supporto della community o porre domande relative ad Aspose.Page per .NET?**  
R: Visita il [forum di Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto della community.

---

**Ultimo aggiornamento:** 2026-07-19  
**Testato con:** Aspose.Page per .NET 24.9  
**Autore:** Aspose

## Tutorial correlati

- [Crea documento XPS con Aspose.Page per .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Disegnare forme](/page/net/drawing-shapes/)
- [Aggiungi testo al documento XPS con Aspose.Page per .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}