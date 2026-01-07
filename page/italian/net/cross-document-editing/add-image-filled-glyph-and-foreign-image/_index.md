---
date: 2026-01-07
description: Scopri come creare documenti XPS in .NET usando Aspose.Page. Questa guida
  mostra come aggiungere glifi riempiti con immagini e immagini esterne per visuali
  di documento più ricche.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Creare documento XPS .NET con Aspose.Page – Glifo riempito con immagine e immagine
  esterna
url: /it/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea XPS document .NET con Aspose.Page – Glifo riempito con immagine e immagine esterna

## Introduction

Se hai bisogno di **create XPS document .NET** applicazioni che appaiano rifinite e professionali, Aspose.Page ti offre gli strumenti per incorporare immagini direttamente nei glifi e riutilizzare risorse grafiche tra i documenti. In questo tutorial vedremo come creare due file XPS, riempire i glifi con un pennello immagine e poi riutilizzare quel pennello in un secondo documento. Alla fine comprenderai perché questo approccio consente di risparmiare memoria, semplificare lo styling e aprire possibilità creative per report, fatture o qualsiasi contenuto stampabile.

## Quick Answers
- **Di cosa tratta questo tutorial?** Aggiungere glifi riempiti con immagine e riutilizzarli nei documenti XPS con Aspose.Page per .NET.  
- **Qual è la parola chiave principale mirata?** `create xps document .net`.  
- **Prerequisiti?** Ambiente di sviluppo .NET, Aspose.Page for .NET e una cartella per i tuoi file XPS.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un prototipo funzionante.  
- **Posso usare altri formati immagine?** Sì – qualsiasi formato supportato da `System.Drawing.Image` di .NET.

## Prerequisites

Prima di immergerti nel codice, assicurati di avere quanto segue pronto:

- **Aspose.Page for .NET** – scarica l'ultima libreria da [here](https://releases.aspose.com/page/net/).  
- **Ambiente di sviluppo** – Visual Studio 2022 (o qualsiasi IDE che supporti .NET 6+).  
- **Directory dei documenti** – crea una cartella sul tuo computer che conterrà le immagini di input e i file XPS generati; la chiameremo **Your Document Directory** negli esempi.

## Import Namespaces

Inizia includendo gli spazi dei nomi necessari per lavorare con gli oggetti XPS e le utility di disegno.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step‑by‑Step Guide

### Step 1: Create the First XPS Document

Passo 1: Crea il primo documento XPS

Iniziamo istanziando un documento XPS vuoto che ospiterà il glifo riempito con immagine.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Step 2: Add Glyphs to the First Document

Passo 2: Aggiungi glifi al primo documento

Successivamente, aggiungi un glifo (un carattere di testo) che più tardi riempiremo con un pennello immagine.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 3: Fill Glyphs with an Image Brush

Passo 3: Riempire i glifi con un pennello immagine

Qui creiamo un `ImageBrush` da un file TIFF situato nella nostra directory dei dati e lo applichiamo al glifo. Il pennello è impostato in modalità tile in modo che l'immagine si ripeta se l'area del glifo supera le dimensioni dell'immagine.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Step 4: Create the Second XPS Document

Passo 4: Crea il secondo documento XPS

Ora creiamo un secondo documento XPS che riutilizzerà lo stile del glifo e il pennello immagine dal primo.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Step 5: Add Glyphs with the Font from the First Document

Passo 5: Aggiungi glifi con il font dal primo documento

Aggiungiamo un glifo al secondo documento, riutilizzando lo stesso oggetto font del primo documento. Questo garantisce coerenza visiva tra entrambi i file.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Step 6: Create an Image Brush from the Fill of the First Document

Passo 6: Crea un pennello immagine dal riempimento del primo documento

Invece di caricare nuovamente l'immagine, cloniamo il pennello da `glyphs1` e lo assegniamo a `glyphs2`. Questo dimostra come sia possibile **create XPS document .NET** flussi di lavoro che condividono risorse in modo efficiente.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Step 7: Save the Documents

Passo 7: Salva i documenti

Infine, salva entrambi i file XPS su disco. Ora puoi aprirli con qualsiasi visualizzatore XPS per vedere l'effetto del glifo riempito con immagine.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Why use image‑filled glyphs when you create XPS document .NET?

Perché usare glifi riempiti con immagine quando crei XPS document .NET?

- **Impatto visivo** – Trasforma il testo semplice in elementi ricchi di grafica senza rasterizzare l'intera pagina.  
- **Riutilizzo delle risorse** – Condividi pennelli e font tra più documenti, riducendo l'impronta di memoria.  
- **Flessibilità** – Tile, stretch o ruota il pennello immagine per ottenere pattern personalizzati o branding.

## Common Issues & Tips

Problemi comuni e consigli

- **Errori di percorso file** – Assicurati che `dataDir` termini con un separatore di percorso (`\` o `/`) appropriato per il tuo OS.  
- **Formati immagine non supportati** – Aspose.Page funziona al meglio con TIFF, PNG e JPEG. Converti altri formati prima dell'uso.  
- **TileMode non applicato** – Verifica di effettuare il cast a `XpsImageBrush` prima di impostare `TileMode`; altrimenti la proprietà viene ignorata.

## Frequently Asked Questions

Domande frequenti

### Q1: Can I use different image formats for filling glyphs?

**A:** Sì, Aspose.Page supporta TIFF, PNG, JPEG, BMP e GIF. Basta fornire l'estensione file corretta nella chiamata `CreateImageBrush`.

### Q2: How can I customize the appearance of glyphs further?

**A:** Esplora proprietà aggiuntive su `XpsGlyphs` come `Opacity`, `RenderTransform` e `Stroke` per perfezionare il rendering.

### Q3: Is Aspose.Page suitable for handling large document sets?

**A:** Assolutamente. La libreria è ottimizzata per scenari ad alte prestazioni e può elaborare migliaia di file XPS in lavori batch.

### Q4: Can I apply different styles to individual glyphs?

**A:** Sì. Ogni istanza di `XpsGlyphs` può avere il proprio riempimento, contorno e trasformazione, offrendoti un controllo granulare.

### Q5: What are the benefits of using Aspose.Page over other document processing tools?

**A:** Aspose.Page offre un'API completa, senza licenza, per la creazione, manipolazione e conversione di XPS, con documentazione estesa e supporto 24/7.

---

**Ultimo aggiornamento:** 2026-01-07  
**Testato con:** Aspose.Page 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}