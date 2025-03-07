---
title: Aggiungi glifo riempito con immagine e immagine estranea con Aspose.Page .NET
linktitle: Aggiungi glifo riempito con immagine e immagine estranea
second_title: API Aspose.Page .NET
description: Sblocca la potenza dell'elaborazione dei documenti in .NET con Aspose.Page. Aggiungi glifi pieni di immagini senza sforzo. Migliora le immagini e semplifica il flusso di lavoro.
weight: 11
url: /it/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi glifo riempito con immagine e immagine estranea con Aspose.Page .NET

## introduzione

Nel mondo dello sviluppo .NET, Aspose.Page si distingue come un potente toolkit per la gestione delle attività di elaborazione dei documenti. Questo tutorial ti guiderà attraverso il processo di aggiunta di glifi pieni di immagini e di incorporazione di immagini straniere utilizzando Aspose.Page per .NET. Al termine di questa guida avrai acquisito una conoscenza approfondita di come migliorare le capacità di elaborazione dei documenti.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

-  Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/page/net/).

- Ambiente di sviluppo: configura un ambiente di sviluppo .NET funzionante con Visual Studio o qualsiasi altro IDE preferito.

- Directory dei documenti: crea una directory in cui archivierai i tuoi documenti. Negli esempi di codice questa verrà definita "Directory dei documenti".

## Importa spazi dei nomi

Nella tua applicazione .NET, inizia importando gli spazi dei nomi necessari per accedere alle classi e ai metodi forniti da Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Passaggio 1: crea il primo documento XPS

Inizia creando il primo documento XPS utilizzando Aspose.Page. Questo documento servirà come base per l'aggiunta di glifi pieni di immagini.

```csharp
// Inizio ex:1
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";

// Crea il primo documento XPS
XpsDocument doc1 = new XpsDocument();
```

## Passaggio 2: aggiungi glifi al primo documento

Aggiungi glifi al primo documento, specificando carattere, dimensione, stile e posizione.

```csharp
// Aggiungi glifi al primo documento
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Passaggio 3: riempi i glifi con un pennello immagine

Riempi i glifi con un pennello immagine, utilizzando un'immagine dalla directory dei dati.

```csharp
// Riempi i glifi con un pennello immagine
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Passaggio 4: crea il secondo documento XPS

Ora crea il secondo documento XPS che incorporerà i glifi del primo documento.

```csharp
// Crea il secondo documento XPS
XpsDocument doc2 = new XpsDocument();
```

## Passaggio 5: aggiungi glifi con il carattere del primo documento

Aggiungi glifi al secondo documento, utilizzando il carattere del primo documento.

```csharp
// Aggiungi glifi con il carattere dal primo documento al secondo documento
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Passaggio 6: crea un pennello immagine dal riempimento del primo documento

Crea un pennello immagine dal riempimento del primo documento e usalo per riempire i glifi nel secondo documento.

```csharp
// Crea un pennello immagine dal riempimento del primo documento e riempi i glifi nel secondo documento
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Passaggio 7: salvare i documenti

Salva sia il primo che il secondo documento XPS.

```csharp
// Salva il primo documento XPS
doc1.Save(dataDir + "out1.xps");

// Salva il secondo documento XPS
doc2.Save(dataDir + "out2.xps");
// Fine Estesa:1
```

## Conclusione

Congratulazioni! Hai aggiunto con successo glifi pieni di immagini e incorporato immagini straniere utilizzando Aspose.Page per .NET. Questo tutorial fornisce una base per migliorare le capacità di elaborazione dei documenti, aprendo nuove possibilità per documenti creativi e visivamente accattivanti.

## Domande frequenti

### Q1: Posso utilizzare formati immagine diversi per riempire i glifi?

A1: Sì, Aspose.Page supporta vari formati di immagine. Garantisci la compatibilità con il formato immagine scelto.

### Q2: Come posso personalizzare ulteriormente l'aspetto dei glifi?

A2: esplorare la documentazione di Aspose.Page per proprietà e metodi aggiuntivi per ottimizzare l'aspetto dei glifi.

### Q3: Aspose.Page è adatto alla gestione di set di documenti di grandi dimensioni?

A3: Aspose.Page è progettato per gestire in modo efficiente sia set di documenti piccoli che grandi.

### Q4: Posso applicare stili diversi ai singoli glifi?

R4: Sì, puoi personalizzare gli stili per ciascun glifo in modo indipendente, garantendo un elevato livello di flessibilità.

### Q5: Quali sono i vantaggi dell'utilizzo di Aspose.Page rispetto ad altri strumenti di elaborazione dei documenti?

R5: Aspose.Page offre un set completo di funzionalità, prestazioni eccellenti e documentazione estesa, rendendolo la scelta preferita da molti sviluppatori.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
