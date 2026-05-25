---
date: 2026-01-20
description: Aggiungi facilmente i numeri di pagina al PDF mentre unisci documenti
  XPS in PDF di alta qualità usando Aspose.Page per .NET. Segui la nostra guida passo‑passo
  per convertire XPS in PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Aggiungi numeri di pagina al PDF – Unisci XPS in PDF con Aspose.Page
url: /it/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere numeri di pagina PDF – Unire XPS in PDF usando Aspose.Page

## Introduzione

Se hai bisogno di **aggiungere numeri di pagina PDF** durante l'unione di file XPS, Aspose.Page per .NET rende il processo indolore. In questo tutorial ti guideremo passo passo attraverso un esempio completo, pronto per la produzione, che converte un documento XPS in un PDF di alta qualità, ti consente di controllare la compressione delle immagini e inserisce automaticamente i numeri di pagina nel PDF finale. Alla fine avrai uno snippet riutilizzabile da inserire in qualsiasi progetto C#.

## Risposte rapide
- **Posso aggiungere numeri di pagina durante l'unione di XPS in PDF?** Sì – la proprietà `PdfSaveOptions.PageNumbers` fa esattamente questo.  
- **Quale libreria gestisce la conversione?** Aspose.Page per .NET.  
- **Ho bisogno di una licenza per l'uso in produzione?** È necessaria una licenza valida di Aspose.Page; è disponibile una licenza temporanea per i test.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6+.  
- **È possibile ottenere immagini ad alta qualità?** Assolutamente – impostare `JpegQualityLevel` a 100 e scegliere `PdfImageCompression.Jpeg`.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

- Aspose.Page per .NET: Assicurati di avere la libreria Aspose.Page installata. Puoi scaricarla da [here](https://releases.aspose.com/page/net/).
- File di documento: Avere il documento XPS (`input.xps`) pronto nella directory specificata.

## Importare gli spazi dei nomi

Nel tuo progetto .NET, includi gli spazi dei nomi necessari per lavorare con Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Questo passaggio garantisce l'accesso alle classi e ai metodi richiesti per la conversione del documento.

## Come aggiungere numeri di pagina PDF durante l'unione di documenti XPS

La collezione `PdfSaveOptions.PageNumbers` ti consente di specificare esattamente quali pagine (o intervalli di pagine) devono comparire nel PDF di output. Popolandola con i numeri di pagina desiderati, Aspose.Page inserisce automaticamente la numerazione corretta.

### Passo 1: Inizializzare gli stream

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Questo passaggio prevede la configurazione degli stream di input e output per i file XPS e PDF. Assicurati che i percorsi e i nomi dei file siano corretti.

### Passo 2: Caricare il documento XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Qui carichiamo il documento XPS nell'oggetto `XpsDocument`, preparandolo per l'elaborazione successiva.

### Passo 3: Inizializzare le opzioni di salvataggio (unire XPS in PDF)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Personalizza l'oggetto `PdfSaveOptions` in base alle tue preferenze, specificando parametri come la compressione delle immagini, la compressione del testo e i **numeri di pagina** che vuoi far apparire nel PDF finale. Impostare `JpegQualityLevel` a 100 garantisce **immagini PDF ad alta qualità**.

### Passo 4: Creare il dispositivo di rendering

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

Il `PdfDevice` è lo strumento responsabile del rendering del documento XPS in formato PDF.

### Passo 5: Salvare il documento (C# XPS in PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Infine, salva il documento usando il dispositivo di rendering e le opzioni specificate. Il PDF di output conterrà le pagine selezionate con i numeri di pagina aggiunti automaticamente.

## Perché utilizzare Aspose.Page per questa conversione?

- **Affidabilità** – Gestisce funzionalità XPS complesse senza perdita di fedeltà.  
- **Prestazioni** – L'elaborazione basata su stream evita di caricare interi file in memoria.  
- **Flessibilità** – Controllo dettagliato su qualità dell'immagine, compressione e numerazione delle pagine.  
- **Cross‑platform** – Funziona su Windows, Linux e macOS con .NET Core.

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Il PDF di output è vuoto** | Verifica che il percorso del file XPS sia corretto e che il file non sia corrotto. |
| **I numeri di pagina non compaiono** | Assicurati che `PageNumbers` sia impostato sugli indici di pagina basati su zero corretti (ad esempio, `new int[] {1,2,6}`). |
| **Immagini a bassa qualità** | Aumenta `JpegQualityLevel` e scegli `PdfImageCompression.Jpeg`. |
| **File XPS di grandi dimensioni causano pressione sulla memoria** | Elabora l'XPS in blocchi più piccoli o aumenta il limite di memoria dell'applicazione. |

## Domande frequenti

### Q1: Posso unire più file XPS in un unico PDF?

A1: Sì, puoi. Basta regolare il parametro `PageNumbers` in `PdfSaveOptions` per includere le pagine desiderate da diversi file XPS, oppure caricare ogni XPS sequenzialmente e chiamare `document.Save` sullo stesso `PdfDevice`.

### Q2: È disponibile una licenza temporanea per Aspose.Page per .NET?

A2: Sì, puoi ottenere una licenza temporanea [here](https://purchase.aspose.com/temporary-license/) per scopi di test.

### Q3: Ci sono limitazioni sulla dimensione dei file quando si utilizza Aspose.Page per la conversione dei documenti?

A3: Aspose.Page per .NET non impone limitazioni rigide sulla dimensione dei file, ma le prestazioni ottimali si ottengono con file di dimensioni ragionevoli. Per documenti XPS molto grandi, considera di elaborarli in stream per ridurre il consumo di memoria.

### Q4: Posso personalizzare ulteriormente il PDF di output, ad esempio aggiungendo filigrane o annotazioni?

A4: Sì, Aspose.Page per .NET offre ampie funzionalità per la manipolazione dei PDF. Dopo la conversione, puoi utilizzare la libreria Aspose.PDF per aggiungere filigrane, annotazioni o altri miglioramenti.

### Q5: Aspose.Page per .NET supporta lo sviluppo cross‑platform?

A5: Sì, Aspose.Page per .NET è progettato per funzionare senza problemi su varie piattaforme, inclusi Windows, Linux e macOS, quando viene utilizzato con .NET Core o .NET 5/6.

---

**Ultimo aggiornamento:** 2026-01-20  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}