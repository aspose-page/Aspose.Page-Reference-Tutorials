---
date: 2026-06-30
description: Scopri come creare un documento XPS .NET e aggiungere glifi riempiti
  con immagine o immagini esterne utilizzando Aspose.Page per .NET in pochi semplici
  passaggi.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Aggiungi glifo riempito con immagine e immagine esterna
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Crea documento XPS .NET – Aggiungi glifo riempito con immagine e immagine esterna
  con Aspose.Page
url: /it/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento XPS .NET – Aggiungi glifo riempito con immagine e immagine esterna con Aspose.Page

## Introduzione

Nello sviluppo .NET, le attività di **create XPS document .NET** sono comuni quando è necessario avere grafica di alta qualità e indipendente dalla risoluzione. Aspose.Page per .NET rende tutto semplice e consente di arricchire i file XPS con glifi riempiti con immagini o di importare immagini da un altro documento XPS. Alla fine di questo tutorial saprai come creare due documenti XPS, riempire i glifi con immagini e riutilizzare quelle immagini tra i documenti—perfetto per generare fatture, certificati o qualsiasi output ricco di elementi visivi.

## Risposte rapide

- **Cosa supporta Aspose.Page?** Oltre 25 formati immagine e la possibilità di elaborare file XPS fino a 500 MB senza caricare l'intera memoria.  
- **Quante righe di codice servono per aggiungere un glifo riempito con immagine?** Solo due righe: creare un `ImageBrush` e assegnarlo a un `Glyph`.  
- **È necessaria una licenza per la produzione?** Sì, una licenza commerciale rimuove i filigrane di valutazione.  
- **Quali versioni .NET sono compatibili?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso riutilizzare i font da un altro XPS?** Assolutamente – è possibile importare la collezione di font dal primo documento al secondo.

## Come creare un documento XPS usando Aspose.Page .NET?

Carica la libreria Aspose.Page, istanzia un `XpsDocument`, aggiungi una pagina e chiama `Save` – questo è il flusso di lavoro completo in tre istruzioni concise. L'API gestisce automaticamente le dimensioni della pagina, DPI e la gestione delle risorse, quindi non è necessario gestire manualmente le strutture XPS a basso livello. Questo approccio scala da un volantino di una pagina a cataloghi di centinaia di pagine.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Aspose.Page for .NET** – scaricalo da [qui](https://releases.aspose.com/page/net/).  
- **Un IDE .NET** – Visual Studio, Rider o VS Code con l'estensione C#.  
- **Una cartella per i tuoi documenti** – la chiameremo **Your Document Directory** nei frammenti di codice.

## Importa spazi dei nomi

Lo spazio dei nomi `Aspose.Page.XPS` fornisce le classi principali dei documenti XPS, mentre `Aspose.Page.XPS.XpsModel` contiene elementi modello come glifi e pennelli. Importali all'inizio del tuo file:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Che cos'è un glifo riempito con immagine?

Un glifo è una forma vettoriale che può essere renderizzata con un colore solido, un gradiente o un pennello immagine. Quando applichi un `ImageBrush`, l'interno del glifo viene dipinto con l'immagine fornita, consentendo effetti visivi complessi senza rasterizzare l'intera pagina.

## Passo 1: Crea il primo documento XPS

`XpsDocument` rappresenta un pacchetto XPS ed è il punto di ingresso per creare e salvare file XPS. Inizia creando il primo documento XPS che ospiterà i glifi riempiti con immagini.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Passo 2: Aggiungi glifi al primo documento

`XpsGlyphs` definisce una collezione di glifi (caratteri di testo) che possono essere posizionati su una pagina. Aggiungi glifi al primo documento, specificando il font, la dimensione, lo stile e la posizione.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Passo 3: Riempire i glifi con un pennello immagine

`ImageBrush` dipinge un'area con un'immagine, consentendo a motivi o foto di riempire forme. Riempire i glifi con un pennello immagine, utilizzando un'immagine dalla tua directory dei dati.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Passo 4: Crea il secondo documento XPS

`XpsDocument` è usato per creare un nuovo file XPS che può contenere pagine, risorse e contenuti. Ora, crea il secondo documento XPS che incorporerà i glifi dal primo documento.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Passo 5: Aggiungi glifi con il font dal primo documento

`Font` rappresenta un tipo di carattere usato per renderizzare il testo in un documento XPS. Aggiungi glifi al secondo documento, usando il font estratto dal primo documento. Condividendo la collezione di font, mantieni le dimensioni del file ridotte e garantisci coerenza visiva.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Passo 6: Crea un pennello immagine dal riempimento del primo documento

`ImageBrush` può essere creato da un riempimento esistente per riutilizzare la stessa immagine tra documenti. Crea un pennello immagine dal riempimento del primo documento e usalo per riempire i glifi nel secondo documento. Questa tecnica di “immagine esterna” consente di riutilizzare le grafiche senza duplicare il file sorgente.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Passo 7: Salva i documenti

`Save` scrive il pacchetto XPS su un file, incorporando tutte le risorse. Salva sia il primo che il secondo documento XPS nella cartella di output. Il metodo `Save` scrive il pacchetto XPS, incorporando tutte le risorse e preservando i glifi riempiti con immagini.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Problemi comuni e soluzioni

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Immagine non visualizzata all'interno del glifo** | Il `ImageBrush` è stato creato con un URI errato o la dimensione dell'immagine supera i limiti del glifo. | Verifica il percorso dell'immagine e, facoltativamente, imposta `ImageBrush.Stretch = Stretch.Uniform`. |
| **Font mancanti nel secondo documento** | Le risorse dei font non sono state esportate dal primo XPS. | Usa `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` prima di aggiungere i glifi. |
| **Rallentamento delle prestazioni su file di grandi dimensioni** | Caricamento di immagini grandi in memoria per ogni glifo. | Riutilizza una singola istanza di `ImageBrush` per tutti i glifi, oppure riduci la risoluzione dell'immagine prima dell'uso. |

## Domande frequenti

### Q1: Posso usare diversi formati immagine per riempire i glifi?

A1: Sì, Aspose.Page supporta PNG, JPEG, BMP, GIF, TIFF e altri—oltre 25 formati in totale.

### Q2: Come posso personalizzare ulteriormente l'aspetto dei glifi?

A2: Esplora proprietà come `Glyph.Stroke`, `Glyph.FillOpacity` e `Glyph.Transform` per regolare i contorni, la trasparenza e la rotazione.

### Q3: Aspose.Page è adatto per gestire grandi insiemi di documenti?

A3: Assolutamente. La libreria elabora file XPS di centinaia di pagine usando lo streaming, mantenendo l'uso di memoria sotto i 100 MB anche per documenti di 500 pagine.

### Q4: Posso applicare stili diversi a glifi individuali?

A4: Sì, ogni istanza di `Glyph` ha le proprie proprietà `Fill`, `Stroke` e `Transform`, consentendo la stilizzazione per glifo.

### Q5: Quali sono i vantaggi di usare Aspose.Page rispetto ad altri strumenti XPS?

A5: Aspose.Page supporta più di 25 formati immagine, elabora file fino a 500 MB senza caricare l'intera memoria e fornisce un'API 100 % .NET‑native—eliminando la necessità di interop COM o strumenti esterni.

---

**Ultimo aggiornamento:** 2026-06-30  
**Testato con:** Aspose.Page 24.11 for .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Crea documento XPS – Aspose.Page per .NET](/page/net/document-creation/)
- [Aggiungi immagine al documento XPS con Aspose.Page per .NET](/page/net/image-management/add-image-to-xps-document/)
- [Aggiungi clone di glifo e cambia colore con Aspose.Page per .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}