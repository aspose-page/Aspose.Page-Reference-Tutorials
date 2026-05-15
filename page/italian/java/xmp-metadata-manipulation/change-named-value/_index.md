---
date: 2026-05-15
description: Scopri come modificare i metadati XMP e come cambiare i valori XMP nei
  file EPS con Aspose.Page for Java – una guida chiara passo‑passo.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Cambia valore denominato in XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Come modificare XMP – Cambia valore denominato in XMP usando Java
url: /it/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# come modificare xmp – Modificare il valore denominato in XMP usando Java

## Risposte rapide
- **Cosa copre questo tutorial?** Cambiare un valore XMP denominato in un file EPS con Aspose.Page per Java.  
- **Quale versione della libreria è necessaria?** Qualsiasi versione recente di Aspose.Page per Java (l'API è stabile da diversi anni).  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per la produzione; una prova gratuita funziona per i test.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per uno sviluppatore familiare con Java I/O.  
- **Posso usarlo con altri formati di file?** L'API XMP è disponibile anche per PDF, SVG e altri formati supportati da Aspose.Page.

## Cos'è il metadato XMP?
XMP (Extensible Metadata Platform) è un formato XML standardizzato per incorporare metadati ricchi — come creatore, titolo e proprietà personalizzate — direttamente all'interno dei file. Nei documenti EPS, XMP vive accanto ai tradizionali commenti PostScript, consentendo alle applicazioni di leggere e modificare i metadati senza alterare il contenuto visivo.

## Perché usare Aspose.Page per Java per modificare XMP?
Aspose.Page ti offre **controllo completo su più di 150 proprietà dello schema XMP** e funziona in modo coerente su formati EPS, PDF e SVG. Elabora file fino a **500 MB** senza caricare l'intero documento in memoria e include una validazione integrata che garantisce che l'EPS risultante rimanga conforme agli standard. Non sono richiesti parser XML esterni né librerie native.

## Introduzione
Aspose.Page per Java è una libreria robusta che facilita la manipolazione e l'elaborazione dei file EPS. Quando si tratta di gestire i metadati XMP all'interno di questi file, Aspose.Page offre agli sviluppatori un set completo di funzionalità. In questo tutorial ci concentreremo sul cambiare un valore denominato in XMP, fornendo una guida chiara e concisa per gli sviluppatori che desiderano potenziare le loro capacità di elaborazione dei documenti.

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1. **Ambiente di sviluppo Java** – Un JDK (8 o superiore) e un IDE o uno strumento di build (Maven/Gradle).  
2. **Libreria Aspose.Page per Java** – Scarica e integra la libreria Aspose.Page per Java nel tuo progetto. Puoi trovare la libreria e la documentazione dettagliata [qui](https://reference.aspose.com/page/java/).  
3. **File EPS di esempio** – Disponi di un file EPS di esempio pronto per la sperimentazione. Se non ne hai uno, usa il file di esempio fornito chiamato **"xmp4.eps."**

## Importa pacchetti
Le istruzioni `import` importano le classi essenziali di Aspose.Page nello spazio dei nomi.

La classe `PsDocument` è l'oggetto principale di Aspose.Page che rappresenta un documento EPS in memoria.  
La classe `XmpMetadata` fornisce l'accesso al pacchetto XMP incorporato nel file EPS.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Come modificare i metadati XMP?
Carica il file EPS, recupera il suo pacchetto XMP, modifica la proprietà desiderata e salva il documento — il tutto in poche righe semplici. Questo approccio funziona per qualsiasi valore XMP denominato, sia che si tratti di un campo standard Dublin Core sia di uno spazio dei nomi personalizzato da te definito.

## Passo 1: Inizializza lo stream del file EPS di input
`FileInputStream` apre uno stream di sola lettura verso il file EPS di origine, consentendo ad Aspose.Page di ingerire il documento senza bloccare il file system.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Passo 2: Inizializza PsDocument
`PsDocument` è l'oggetto primario che incapsula il contenuto EPS e fornisce accesso ai suoi metadati, pagine e risorse.

```java
PsDocument document = new PsDocument(psStream);
```

## Passo 3: Ottieni i metadati XMP
`XmpMetadata` rappresenta il pacchetto XMP all'interno del file EPS e offre metodi per leggere, modificare o eliminare singole proprietà.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Passo 4: Imposta un nuovo valore in XMP
`setProperty` imposta il valore di una proprietà XMP specificata nel pacchetto di metadati.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Passo 5: Inizializza lo stream del file EPS di output
`FileOutputStream` crea uno stream scrivibile per salvare il file EPS modificato.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Passo 6: Salva il documento con i metadati XMP modificati
`save` scrive il `PsDocument` in memoria, includendo l'XMP aggiornato, nello stream di output.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Passo 7: Chiudi lo stream di input EPS
`close` rilascia il handle del file e libera le risorse associate allo stream di input.

```java
// Close input EPS stream
psStream.close();
```

## Problemi comuni e soluzioni
- **FileNotFoundException** – Verifica che `dataDir` punti alla cartella corretta e che `xmp4.eps` esista.  
- **LicenseException** – Se visualizzi errori di licenza, assicurati che un file di licenza valido di Aspose.Page sia caricato prima di creare `PsDocument`.  
- **Metadata Not Updated** – Dopo il salvataggio, apri l'EPS risultante in un visualizzatore di metadati (ad es., Adobe Bridge) per confermare che il nuovo valore sia presente.

## Domande frequenti
**D: Posso usare Aspose.Page per Java con altri linguaggi di programmazione?**  
R: Aspose.Page supporta principalmente Java, ma Aspose offre librerie equivalenti per .NET, C++ e Python che espongono capacità simili di manipolazione XMP.

**D: È disponibile una versione di prova gratuita per Aspose.Page per Java?**  
R: Sì, puoi provare una versione di prova gratuita di Aspose.Page per Java [qui](https://releases.aspose.com/).

**D: Dove posso trovare supporto aggiuntivo e discussioni su Aspose.Page per Java?**  
R: Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per supporto della community e discussioni.

**D: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
R: Puoi acquisire una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso acquistare Aspose.Page per Java?**  
R: Per acquistare Aspose.Page per Java, visita la [pagina di acquisto](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-05-15  
**Testato con:** Aspose.Page per Java (ultima versione)  
**Autore:** Aspose

## Tutorial correlati

- [Come leggere i metadati XMP usando Java – Guida Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Tutorial Aspose Page Java – Aggiungere metadati XMP ai file EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Modificare i valori in XMP usando Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}