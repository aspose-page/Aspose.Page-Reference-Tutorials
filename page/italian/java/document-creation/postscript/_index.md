---
date: 2026-06-20
description: Scopri come impostare la dimensione della pagina A4, creare file PostScript
  in Java e aggiungere font personalizzati usando Aspose.Page. Prova la versione di
  prova gratuita oggi!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Crea documento in Java con PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Come impostare la dimensione della pagina A4 e creare PostScript in Java con
  Aspose.Page
url: /it/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare le dimensioni della pagina A4 e creare PostScript in Java con Aspose.Page

## Introduzione
Se hai bisogno di **impostare le dimensioni della pagina a4** durante la generazione di file PostScript da Java, Aspose.Page offre un'API veloce e affidabile che nasconde i dettagli di basso livello. In questo tutorial percorreremo l'intero flusso di lavoro—creazione di un documento PostScript, configurazione delle dimensioni della pagina A4 e **aggiunta di font personalizzati** quando necessario. Alla fine avrai a disposizione uno snippet di codice pronto all'uso da inserire in qualsiasi progetto Java.

## Risposte rapide
- **Quale libreria crea PostScript in Java?** Aspose.Page for Java.  
- **Quale dimensione di pagina è l'obiettivo di questa guida?** A4 (210 mm × 297 mm).  
- **Posso incorporare i miei font?** Sì – imposta la cartella dei font aggiuntivi nelle opzioni di salvataggio.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale; è disponibile una versione di prova.  
- **Quali versioni di Java sono supportate?** Java 8 e successive.

## Come impostare le dimensioni della pagina a4 e creare postscript in Java
Carica la libreria Aspose.Page, configura `PsSaveOptions` con le costanti A4 e scrivi il documento su file – il tutto in meno di dieci righe di codice. Questo approccio diretto garantisce le dimensioni corrette della pagina e ti consente di aggiungere font personalizzati senza configurazioni aggiuntive.

## Cos'è la dimensione postscript a4?
La dimensione PostScript A4 è lo standard ISO 216 (210 mm × 297 mm) espresso nel linguaggio di descrizione della pagina PostScript. Definisce l'area stampabile che stampanti e visualizzatori interpretano, garantendo un layout coerente su tutte le piattaforme. Poiché PostScript descrive il contenuto della pagina in modo indipendente dal dispositivo, l'uso della dimensione A4 assicura che il documento appaia identico su qualsiasi stampante o visualizzatore compatibile A4 in tutto il mondo.

## Perché usare Aspose.Page per impostare la dimensione della pagina postscript?
Aspose.Page supporta **oltre 30 operatori PostScript** e può generare file fino a **500 MB** senza caricare l'intero documento in memoria. Questo ti offre un controllo preciso sulle dimensioni della pagina gestendo carichi di lavoro di grandi dimensioni in modo efficiente. La libreria astrae anche la sintassi complessa di PostScript, gestisce automaticamente le risorse e fornisce streaming ad alte prestazioni, rendendola ideale sia per volantini a pagina singola sia per report multi‑pagina complessi.

## Come aggiungere font personalizzati in Java
Incorporare i propri caratteri garantisce che il documento generato abbia esattamente l'aspetto previsto su qualsiasi stampante o visualizzatore, e Aspose.Page scopre automaticamente i font collocati nella cartella specificata. Registrando una cartella di font aggiuntiva, puoi utilizzare qualsiasi font TrueType o OpenType, evitare sostituzioni di fallback e mantenere la coerenza del brand su tutti i dispositivi di output.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Una buona conoscenza della programmazione Java.  
- Aspose.Page for Java installato. Puoi scaricarlo [qui](https://releases.aspose.com/page/java/).  
- Una cartella denominata `necessary_fonts` (o qualsiasi nome preferisci) che contenga i font personalizzati da incorporare.

## Importare i pacchetti
Nel tuo progetto Java, importa le classi necessarie di Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Ora suddividiamo l'esempio in passaggi chiari e numerati.

### Passo 1: Impostare la directory del documento
La costante `OUTPUT_DIR` indica alla libreria dove scrivere il file generato.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Passo 2: Definire la cartella dei font
`FONTS_FOLDER` punta alla directory che contiene i tuoi font TrueType o OpenType personalizzati.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Passo 3: Creare lo stream di output per il documento PostScript
`FileOutputStream` apre uno stream che riceverà l'output finale PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Passo 4: Creare le opzioni di salvataggio con dimensione A4
`PsSaveOptions` ti consente di specificare la dimensione della pagina di destinazione.  
**Definizione:** `PsPageSize` è un'enumerazione che contiene costanti di dimensioni standard come A4, Letter e Legal.  
Impostare `options.setPageSize(PsPageSize.A4)` configura il documento per le dimensioni standard A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Passo 5: Impostare i margini della pagina e aggiungere la cartella dei font personalizzati
`options.setMargins(0, 0, 0, 0)` rimuove tutti i margini per una pagina a piena estensione, e `options.setAdditionalFontsFolder(FONTS_FOLDER)` registra i tuoi font personalizzati.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Passo 6: Creare un documento PS multipagina o a pagina singola
`PsDocument document = new PsDocument(outputStream, options)` crea il documento. `PsDocument` rappresenta un documento PostScript che può contenere una o più pagine. Imposta `multiPaged` a `true` per output multipagina.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Passo 7: Chiudere la pagina corrente e salvare il documento
Chiamare `document.close()` finalizza il file e scrive l'output **PostScript A4 size** su disco.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Problemi comuni e suggerimenti
- **Il font non appare?** Verifica che il file del font sia in formato TrueType o OpenType supportato e che `FONTS_FOLDER` termini con una barra (`/`).  
- **I margini sono ancora visibili?** Chiama `options.setMargins(...)` **prima** di costruire il `PsDocument`.  
- **L'output multipagina appare vuoto?** Ricorda di invocare `document.newPage()` per ogni pagina aggiuntiva necessaria.

## Domande frequenti

**D: Posso usare font personalizzati nel mio documento PostScript?**  
**R:** Sì, imposta la cartella dei font aggiuntivi nelle opzioni di salvataggio (vedi Passo 5) e Aspose.Page incorporerà automaticamente i font.

**D: È disponibile una versione di prova per Aspose.Page per Java?**  
**R:** Sì, puoi ottenere una prova gratuita [qui](https://releases.aspose.com/).

**D: Come posso accedere alla documentazione completa dell'API?**  
**R:** Consulta la documentazione [qui](https://reference.aspose.com/page/java/).

**D: Dove posso acquistare una licenza per Aspose.Page per Java?**  
**R:** Puoi acquistare una licenza [qui](https://purchase.aspose.com/buy).

**D: Dove posso chiedere aiuto alla community?**  
**R:** Visita il forum Aspose.Page [forum](https://forum.aspose.com/c/page/39).

**D: Posso generare file PostScript multipagina?**  
**R:** Assolutamente—imposta `multiPaged` a `true` nel Passo 6 e chiama `document.newPage()` per ogni pagina extra.

## Conclusione
Seguendo questi passaggi ora sai **come impostare le dimensioni della pagina a4** e creare file **PostScript** in Java con Aspose.Page, oltre a poter **aggiungere font personalizzati java** e controllare le opzioni di dimensione della pagina. Aspose.Page gestisce le operazioni più complesse, così puoi concentrarti sul contenuto dei tuoi documenti.

---

**Ultimo aggiornamento:** 2026-06-20  
**Testato con:** Aspose.Page for Java 24.11  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Tutorial Aspose.Page Java – impostare dimensioni pagina personalizzate aggiungendo pagine in PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Come aggiungere testo in PostScript con Aspose.Page per Java](/page/java/postscript-text-manipulation/)
- [Tutorial Aspose Page Java – Convertire PostScript in PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```