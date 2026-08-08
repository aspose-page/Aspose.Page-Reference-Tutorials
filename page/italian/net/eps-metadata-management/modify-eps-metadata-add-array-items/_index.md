---
date: 2026-08-08
description: Scopri come aggiungere elementi di array ai metadati EPS utilizzando
  Aspose.Page EPS metadata. Questa guida passo‑passo per .NET mostra come aggiungere
  elementi di array e leggere i file EPS in modo efficiente.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Aggiungi elementi di array
og_description: Scopri come aggiungere elementi di array ai metadati EPS utilizzando
  Aspose.Page EPS metadata. Segui questo conciso tutorial .NET per leggere i file
  EPS e gestire i metadati in modo efficiente.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Aggiungi elementi di array con Aspose.Page EPS metadata in .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Aggiungi elementi di array con Aspose.Page EPS metadata in .NET
url: /it/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere elementi di array con i metadati EPS di Aspose.Page in .NET

## Introduzione

In questo tutorial imparerai come aggiungere elementi di array ai metadati EPS utilizzando **Aspose.Page EPS metadata**. Che tu debba arricchire un file EPS con titoli aggiuntivi, autori o tag personalizzati, Aspose.Page rende il compito semplice per qualsiasi sviluppatore .NET. Ti guideremo passo dopo passo, dall’apertura dello stream EPS alla persistenza del pacchetto XMP aggiornato, così potrai integrare la gestione dei metadati nelle tue applicazioni con sicurezza.

## Risposte rapide
- **Cosa consente di fare Aspose.Page EPS metadata?** Consente di leggere e scrivere array di metadati XMP all'interno dei file EPS da .NET.  
- **Quale classe rappresenta un documento EPS?** `PsDocument` è la classe principale per caricare e salvare il contenuto EPS.  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Posso modificare i metadati senza alterare la grafica EPS?** Sì, solo il pacchetto XMP viene modificato, lasciando intatto il contenuto della pagina.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Che cos'è Aspose.Page EPS metadata?
Aspose.Page EPS metadata è un blocco informativo basato su XMP incorporato all'interno di un file EPS. Memorizza proprietà descrittive come titoli, autori, parole chiave e tag personalizzati secondo lo standard ISO 16684‑1. I metadati possono essere accessi e modificati programmaticamente tramite l'API Aspose.Page, consentendo la gestione automatizzata dei documenti e l'ottimizzazione della ricerca.

## Perché modificare i metadati EPS?
Aspose.Page può elaborare **oltre 30 campi di metadati** e gestire file EPS fino a **200 MB** senza caricare l'intero documento in memoria, riducendo l'uso della CPU fino al 40 % rispetto all'analisi completa del file. L'aggiornamento dei metadati migliora la ricercabilità, la conformità e l'automazione dei flussi di lavoro a valle.

## Prerequisiti

- Conoscenze di base della programmazione .NET.  
- Aspose.Page per .NET installato – scaricalo da [download Aspose.Page per .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (o qualsiasi IDE compatibile con .NET) per eseguire il codice di esempio.  

## Come aggiungere elementi di array ai metadati EPS?
Per aggiungere elementi di array, prima carica il file EPS in un `PsDocument`, quindi recupera il suo pacchetto XMP usando `GetXmpMetadata()`. Usa il metodo `AddArrayItem()` sull'array XMP desiderato, come `dc:title` o `dc:creator`, per aggiungere nuovi valori. Infine, chiama `Save()` per scrivere i metadati aggiornati nel file mantenendo invariato il contenuto grafico.

### Passo 1: inizializzare lo stream di input del file eps
`PsDocument` rappresenta un documento EPS e fornisce metodi per accedere al suo contenuto. Il codice seguente apre il file EPS come stream e crea un'istanza `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Passo 2: ottenere i metadati xmp
`GetXmpMetadata()` recupera il pacchetto XMP incorporato nel file EPS. Se non esiste alcun pacchetto, l'API ne genera uno nuovo basandosi sui commenti PostScript esistenti.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Passo 3: modificare i valori dei metadati xmp
`AddArrayItem()` aggiunge un nuovo valore a un array XMP esistente senza sovrascrivere le altre voci. Usalo per aggiungere titoli, autori o tag personalizzati ai metadati.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Passo 4: salvare il file eps con i metadati xmp modificati
`Save()` scrive il pacchetto XMP modificato nuovamente nel file EPS preservando il contenuto PostScript originale. Specifica il percorso di output per creare un nuovo file o sovrascrivere la sorgente.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Problemi comuni e risoluzione dei problemi

- **Null XMP packet** – Se `GetXmpMetadata()` restituisce `null`, assicurati che il file EPS contenga almeno un blocco di commenti; altrimenti, crea manualmente una nuova istanza `XmpMetadata`.  
- **Encoding issues** – Usa UTF‑8 quando aggiungi valori stringa per evitare corruzioni dei caratteri in lingue non ASCII.  
- **Large files** – Per file EPS superiori a 150 MB, considera lo streaming dell'input tramite `FileStream` con un buffer per mantenere basso l'uso di memoria.

## Domande frequenti

**Q: Aspose.Page è compatibile con tutti gli ambienti .NET?**  
A: Sì, Aspose.Page funziona su .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6/7, fornendo un comportamento API coerente su Windows, Linux e macOS.

**Q: Posso usare Aspose.Page gratuitamente?**  
A: Puoi valutare la libreria con una versione di prova gratuita scaricabile dalla [pagina di acquisto Aspose](https://purchase.aspose.com/buy). È necessaria una licenza commerciale per le distribuzioni in produzione.

**Q: Sono disponibili licenze temporanee per Aspose.Page?**  
A: Le licenze temporanee possono essere ottenute dalla [pagina di licenza temporanea](https://purchase.aspose.com/temporary-license/) per progetti a breve termine o periodi di valutazione.

**Q: Dove posso trovare supporto della community per Aspose.Page?**  
A: Partecipa alla discussione sul [forum Aspose.Page](https://forum.aspose.com/c/page/39) per porre domande e condividere soluzioni con altri sviluppatori.

**Q: Qual è l'ultima versione di Aspose.Page per .NET?**  
A: Consulta la [documentazione](https://reference.aspose.com/page/net/) ufficiale per le note di rilascio più recenti e i link di download.

---

**Ultimo aggiornamento:** 2026-08-08  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Tutorial correlati

- [Modifica elementi di array con Aspose.Page per .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Aggiungi proprietà semplici con Aspose.Page per .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Aggiungi namespace con Aspose.Page per .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}