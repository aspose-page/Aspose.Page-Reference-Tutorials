---
date: 2026-01-10
description: Converti facilmente XPS in PDF in .NET con Aspose.Page. Scarica la libreria,
  esplora la documentazione e ottieni una prova gratuita.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Converti XPS in PDF con Aspose.Page per .NET
url: /it/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertire XPS in PDF con Aspose.Page per .NET

## Introduzione

In questo tutorial imparerai **come convertire XPS in PDF** utilizzando la libreria Aspose.Page per .NET. Convertire XPS in PDF è una necessità comune quando devi condividere documenti XPS con utenti che hanno solo lettori PDF, o quando vuoi incorporare contenuti XPS in flussi di lavoro PDF più ampi. Ti guideremo passo passo, spiegheremo perché ogni impostazione è importante e ti mostreremo come perfezionare l'output — ad esempio impostando la qualità JPEG e applicando la compressione delle immagini PDF.

## Risposte rapide
- **Qual è la libreria migliore per la conversione da XPS a PDF?** Aspose.Page per .NET
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza commerciale; è disponibile una versione di prova gratuita.
- **Posso controllare la qualità dell'immagine?** Assolutamente — usa `JpegQualityLevel` e `PdfImageCompression`.
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **È possibile convertire più file XPS in un unico PDF?** Sì, iterando sui file e unendo i risultati.

## Prerequisiti

Prima di intraprendere questo percorso di conversione, assicurati di avere i seguenti prerequisiti:

- **Aspose.Page per .NET Library** – Assicurati di aver installato la libreria Aspose.Page per .NET nel tuo ambiente di sviluppo. Puoi scaricarla dalla [documentazione di Aspose.Page](https://reference.aspose.com/page/net/).
- **Ambiente di sviluppo** – Configura un ambiente di sviluppo .NET con Visual Studio o qualsiasi altro IDE compatibile.
- **Documento XPS** – Prepara il documento XPS che desideri convertire in PDF. Può trattarsi del tuo file XPS di esempio memorizzato in una directory designata.

## Importare gli spazi dei nomi

Prima di immergerti nel codice, importiamo lo spazio dei nomi necessario per rendere accessibili le funzionalità di Aspose.Page per .NET nel nostro progetto:

```csharp
using Aspose.Page.XPS;
```

## Guida passo‑passo

### Passo 1: Inizializzare la directory del documento

Definisci la cartella che contiene il tuo file XPS di origine e dove verrà salvato il PDF risultante.

```csharp
string dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con il percorso assoluto o relativo alla cartella che contiene il tuo documento XPS.

### Passo 2: Aprire gli stream per l'output PDF e l'input XPS

Utilizziamo due stream di file — uno per leggere il file XPS e un altro per scrivere il PDF generato.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Suggerimento:** Assicurati che i percorsi siano corretti e che l'applicazione abbia i permessi di lettura/scrittura sulla cartella di destinazione.

### Passo 3: Caricare il documento XPS

Crea un'istanza `XpsDocument` dallo stream XPS. L'oggetto `XpsLoadOptions` ti consente di specificare le preferenze di caricamento, ma le impostazioni predefinite funzionano nella maggior parte degli scenari.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Passo 4: Configurare le opzioni di salvataggio PDF

Qui impostiamo le preferenze di output PDF. Nota l'uso della **compressione delle immagini PDF** (`PdfImageCompression.Jpeg`) e della **qualità JPEG** (`JpegQualityLevel = 100`). Queste impostazioni influiscono direttamente sulla dimensione del file e sulla fedeltà visiva.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Controlla la qualità delle immagini JPEG incorporate nel PDF (valori più alti = migliore qualità, file più grande).
- **`ImageCompression`** – Sceglie l'algoritmo di compressione; JPEG è ideale per immagini fotografiche.
- **`TextCompression`** – La compressione Flate riduce le dimensioni del PDF senza perdere la qualità del testo.
- **`PageNumbers`** – Consente di **salvare XPS come PDF** solo per le pagine selezionate.

### Passo 5: Creare un dispositivo di rendering PDF

Il `PdfDevice` funge da destinazione di rendering che scrive i dati PDF nello stream aperto in precedenza.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Passo 6: Salvare il documento in PDF

Infine, invoca il metodo `Save`, passando il dispositivo di rendering e le opzioni configurate.

```csharp
document.Save(device, options);
```

Quando il codice termina l'esecuzione, `XPStoPDF_out.pdf` apparirà nella directory specificata, contenente le pagine convertite con le impostazioni di compressione e qualità definite.

## Perché convertire XPS in PDF?

- **Accessibilità universale** – I visualizzatori PDF sono installati su praticamente tutti i dispositivi, mentre i lettori XPS sono rari.
- **Preservare il layout** – Il PDF mantiene esattamente il layout visivo, i font e la grafica dell'XPS originale.
- **Ulteriore elaborazione** – Una volta in PDF, puoi unire, annotare o firmare digitalmente il documento usando altre librerie Aspose.

## Casi d'uso comuni

- **Reportistica aziendale** – Genera report XPS da sistemi legacy e convertili in PDF per la distribuzione.
- **Archiviazione** – Conserva i documenti come PDF per la preservazione a lungo termine, mantenendo la possibilità di crearli da sorgenti XPS.
- **Servizi web** – Offri un endpoint API che accetta upload XPS e restituisce file PDF al volo.

## Risoluzione dei problemi e consigli

- **File non trovato** – Verifica nuovamente il percorso `dataDir` e assicurati che il nome del file XPS corrisponda esattamente.
- **Errori di permesso** – Esegui Visual Studio come amministratore o concedi i permessi di scrittura alla cartella di output.
- **PDF di grandi dimensioni** – Se il PDF risultante è troppo grande, riduci `JpegQualityLevel` o passa `ImageCompression` a `PdfImageCompression.Zip`.

## FAQ

### Q1: Posso convertire più file XPS in un unico PDF usando Aspose.Page per .NET?

A1: Sì, puoi iterare su più file XPS e seguire gli stessi passaggi per unirli in un unico PDF.

### Q2: Esistono altri formati di output supportati da Aspose.Page per .NET?

A2: Sì, Aspose.Page per .NET supporta vari formati di output, tra cui TIFF, JPEG, PNG e altri.

### Q3: Come posso personalizzare l'aspetto del documento PDF convertito?

A3: Puoi modificare i parametri dell'oggetto opzioni, come la compressione delle immagini e la compressione del testo, per ottenere l'aspetto desiderato.

### Q4: È disponibile una versione di prova per Aspose.Page per .NET?

A4: Sì, puoi esplorare le funzionalità di Aspose.Page per .NET ottenendo una prova gratuita da [qui](https://releases.aspose.com/).

### Q5: Dove posso ottenere supporto dalla community per Aspose.Page per .NET?

A5: Visita il [forum di Aspose.Page](https://forum.aspose.com/c/page/39) per discussioni e supporto della community.

## Domande frequenti (AI‑Friendly)

**Q: Come impostare la qualità JPEG quando si converte XPS in PDF?**  
A: Usa la proprietà `JpegQualityLevel` all'interno di `PdfSaveOptions`. Impostandola a 100 ottieni la massima qualità.

**Q: Cosa significa “pdf image compression” in questo contesto?**  
A: Si riferisce all'opzione `ImageCompression`, che determina come le immagini vengono compresse all'interno del PDF (ad es., JPEG, Zip).

**Q: Posso generare programmaticamente un PDF senza una sorgente XPS?**  
A: Sì, Aspose.Page supporta anche **c# generate pdf** direttamente da comandi di disegno, ma ciò è fuori dal campo di questo tutorial.

**Q: Esiste un modo per convertire XPS in PDF senza perdere la grafica vettoriale?**  
A: La conversione mantiene i dati vettoriali; basta evitare la rasterizzazione delle immagini mantenendo `ImageCompression` impostato su JPEG o Zip secondo necessità.

**Q: La libreria supporta .NET Core?**  
A: Assolutamente – Aspose.Page per .NET funziona con .NET Core, .NET 5, .NET 6 e versioni successive.

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Page 24.11 per .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}