---
title: Unisci documenti XPS in PDF con Aspose.Page per .NET
linktitle: Unisci documenti XPS in PDF
second_title: API Aspose.Page .NET
description: Unisci facilmente documenti XPS in PDF di alta qualità utilizzando Aspose.Page per .NET. Segui la nostra guida passo passo per un'esperienza di conversione dei documenti fluida.
type: docs
weight: 11
url: /it/net/document-merging/merge-xps-documents-into-pdf/
---
## introduzione

Nel panorama in continua evoluzione dell'elaborazione dei documenti, Aspose.Page per .NET emerge come un potente strumento per unire perfettamente documenti XPS in formato PDF. Questo tutorial ti guiderà attraverso il processo, suddividendo ogni passaggio per garantire un'esecuzione fluida ed efficace.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

-  Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/page/net/).

- File di documenti: disporre del documento XPS (`input.xps`) pronto nella directory specificata.

## Importa spazi dei nomi

Nel tuo progetto .NET, includi gli spazi dei nomi necessari per lavorare con Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Questo passaggio garantisce l'accesso alle classi e ai metodi richiesti per la conversione del documento.

## Passaggio 1: inizializza i flussi

```csharp
// Inizio ex:3
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
// Inizializza il flusso di output PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Inizializza il flusso di input XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// Fine Estesa:3
```

Questo passaggio prevede la configurazione dei flussi di input e output per i file XPS e PDF. Assicurarsi che vengano utilizzati i percorsi e i nomi file corretti.

## Passaggio 2: caricare il documento XPS

```csharp
// Inizio ex:4
// Carica il documento XPS dal flusso
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// oppure caricare il documento XPS direttamente dal file. Quindi non è necessario xpsStream.
//Documento XpsDocument = new XpsDocument(inputFileName, new XpsLoadOptions());
// Fine Estesa:4
```

 Qui, carichiamo il documento XPS nel file`XpsDocument` oggetto, preparandolo per ulteriori elaborazioni.

## Passaggio 3: inizializzare le opzioni di salvataggio

```csharp
// Inizio ex:5
// Inizializza l'oggetto opzioni con i parametri necessari.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// Fine Estesa:5
```

 Personalizza il`PdfSaveOptions` oggetto in base alle tue preferenze, specificando parametri come compressione delle immagini, compressione del testo e numeri di pagina.

## Passaggio 4: crea il dispositivo di rendering

```csharp
// Inizio ex:6
// Crea dispositivo di rendering per il formato PDF
PdfDevice device = new PdfDevice(pdfStream);
// Fine Estesa:6
```

 IL`PdfDevice` è lo strumento responsabile del rendering del documento XPS in formato PDF.

## Passaggio 5: salva il documento

```csharp
// Inizio ex:7
document.Save(device, options);
// Fine Estesa:7
```

Infine, salva il documento utilizzando il dispositivo di rendering e le opzioni specificate.

## Conclusione

Congratulazioni! Hai unito con successo documenti XPS in PDF utilizzando Aspose.Page per .NET. Questo processo continuo garantisce la preservazione della qualità e della formattazione del documento.

## Domande frequenti

### Q1: Posso unire più file XPS in un unico PDF?

 A1: Sì, puoi. Basta regolare il`PageNumbers` parametro nel`PdfSaveOptions` per includere le pagine desiderate da diversi file XPS.

### Q2: È disponibile una licenza temporanea per Aspose.Page per .NET?

 R2: Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) a scopo di test.

### Q3: Esistono limitazioni sulla dimensione del file quando si utilizza Aspose.Page per la conversione dei documenti?

A3: Aspose.Page per .NET non impone limitazioni rigorose sulla dimensione del file, ma si ottengono prestazioni ottimali con dimensioni di file ragionevoli.

### Q4: Posso personalizzare ulteriormente il PDF di output, ad esempio aggiungendo filigrane o annotazioni?

A4: Sì, Aspose.Page per .NET fornisce funzionalità estese per la manipolazione dei PDF. Controlla la documentazione per le opzioni di personalizzazione avanzate.

### Q5: Aspose.Page per .NET supporta lo sviluppo multipiattaforma?

A5: Sì, Aspose.Page per .NET è progettato per funzionare perfettamente su varie piattaforme.