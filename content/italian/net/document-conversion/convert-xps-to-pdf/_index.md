---
title: Converti XPS in PDF con Aspose.Page per .NET
linktitle: Converti XPS in PDF
second_title: API Aspose.Page .NET
description: Converti facilmente XPS in PDF in .NET con Aspose.Page. Scarica la libreria, esplora la documentazione e ottieni una prova gratuita.
type: docs
weight: 11
url: /it/net/document-conversion/convert-xps-to-pdf/
---
## introduzione

In questo tutorial, approfondiremo il processo di conversione di documenti XPS (XML Paper Specifica) in PDF (Portable Document Format) utilizzando la potente libreria Aspose.Page per .NET. Aspose.Page per .NET fornisce un robusto set di funzionalità per lavorare con file XPS, consentendo agli sviluppatori di convertirli senza problemi in formato PDF con varie opzioni di personalizzazione.

## Prerequisiti

Prima di intraprendere questo percorso di conversione, assicurati di disporre dei seguenti prerequisiti:

-  Libreria Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page per .NET installata nel tuo ambiente di sviluppo. Puoi scaricarlo da[Documentazione Aspose.Page](https://reference.aspose.com/page/net/).

- Ambiente di sviluppo: configura un ambiente di sviluppo .NET con Visual Studio o qualsiasi altro IDE compatibile.

- Documento XPS: prepara il documento XPS che desideri convertire in PDF. Potrebbe trattarsi del file XPS di esempio archiviato in una directory designata.

## Importa spazi dei nomi

Prima di immergerci nel codice, importiamo gli spazi dei nomi necessari per rendere accessibili le funzionalità Aspose.Page per .NET nel nostro codice:

```csharp
using Aspose.Page.XPS;
```

## Passaggio 1: inizializzare la directory dei documenti

```csharp
string dataDir = "Your Document Directory";
```

Sostituisci "Directory dei documenti" con il percorso della directory contenente il documento XPS.

## Passaggio 2: inizializza i flussi PDF e XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Apri i flussi sia per il file PDF di output che per il file XPS di input. Assicurati di aver impostato i percorsi file appropriati.

## Passaggio 3: caricare il documento XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Caricare il documento XPS utilizzando la libreria Aspose.Page per .NET.

## Passaggio 4: inizializza le opzioni di salvataggio del PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Imposta le opzioni di salvataggio del PDF, inclusi parametri come il livello di qualità JPEG, la compressione delle immagini, la compressione del testo e i numeri di pagina specifici da includere.

## Passaggio 5: crea un dispositivo di rendering PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Creare un dispositivo di rendering per il formato PDF utilizzando la libreria Aspose.Page per .NET.

## Passaggio 6: salva il documento in PDF

```csharp
document.Save(device, options);
```

Salva il documento XPS in PDF utilizzando il dispositivo di rendering e le opzioni specificati.

## Conclusione

Congratulazioni! Hai convertito con successo un documento XPS in PDF utilizzando Aspose.Page per .NET. Questa versatile libreria fornisce agli sviluppatori un potente set di strumenti per gestire facilmente vari formati di documenti.

## Domande frequenti

### Q1: Posso convertire più file XPS in un singolo PDF utilizzando Aspose.Page per .NET?

R1: Sì, puoi scorrere più file XPS e seguire gli stessi passaggi per unirli in un unico PDF.

### Q2: Esistono altri formati di output supportati da Aspose.Page per .NET?

A2: Sì, Aspose.Page per .NET supporta vari formati di output, inclusi TIFF, JPEG, PNG e altri.

### Q3: Come posso personalizzare l'aspetto del documento PDF convertito?

R3: È possibile modificare i parametri dell'oggetto opzioni, come la compressione delle immagini e la compressione del testo, per ottenere l'aspetto desiderato.

### Q4: È disponibile una versione di prova per Aspose.Page per .NET?

 A4: Sì, puoi esplorare le funzionalità di Aspose.Page per .NET ottenendo una prova gratuita da[Qui](https://releases.aspose.com/).

### Q5: Dove posso ottenere il supporto della community per Aspose.Page per .NET?

 A5: Visita il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per discussioni e supporto della comunità.