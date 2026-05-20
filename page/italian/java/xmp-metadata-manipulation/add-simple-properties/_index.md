---
date: 2026-05-20
description: Scopri come aggiungere metadati XMP ai file EPS con Aspose.Page per Java.
  Guida passo‑passo per incorporare proprietà XMP semplici in modo programmatico.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Aggiungi proprietà semplici in XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Aggiungi metadati XMP ai file EPS usando Java
url: /it/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere metadati XMP ai file EPS usando Java

## Introduzione
Nelle moderne pipeline grafiche, la possibilità di **aggiungere metadati XMP** ai file EPS in modo programmatico ti offre il pieno controllo su come le tue illustrazioni vengono descritte, ricercate e archiviate. Con Aspose.Page per Java puoi leggere, modificare e scrivere pacchetti XMP all'interno dei documenti EPS senza uscire dall'ecosistema Java. In questo tutorial ti guideremo passo passo nell'aggiungere semplici proprietà XMP a un file EPS, così potrai arricchire le tue grafiche con metadati personalizzati in modo rapido e affidabile.

## Risposte rapide
- **Cosa significa “add XMP metadata to EPS”?** Incorporare un pacchetto XMP (metadati basati su XML) all'interno di un file EPS.  
- **Quale libreria è necessaria?** Aspose.Page per Java (scaricabile dal sito Aspose).  
- **È necessaria una licenza per i test?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Quante righe di codice?** Meno di 30 righe di Java più alcune istruzioni di import.  
- **Posso aggiungere altri tipi di dati?** Sì – sono supportati date, interi, double, stringhe e persino array.

## Come aggiungere metadati XMP ai file EPS usando Java?
Carica il file EPS con `new PsDocument("input.eps")`, recupera o crea il suo pacchetto XMP, inserisci le proprietà desiderate e poi salva il documento su disco – il tutto in meno di dieci righe di codice Java. Questo approccio ti consente di incorporare metadati ricercabili e conformi agli standard senza modificare manualmente il sorgente EPS.

## Cos'è il metadato XMP in EPS?
Il metadato XMP in EPS è un pacchetto XML che risiede all'interno del file EPS e memorizza informazioni come autore, data di creazione e tag personalizzati. L'incorporamento di questo pacchetto consente agli strumenti a valle di leggere e utilizzare i dati senza necessità di file aggiuntivi separati.

## Perché aggiungere metadati XMP ai file EPS?
L'incorporamento di metadati XMP rende le risorse EPS immediatamente ricercabili, garantisce la conformità memorizzando le informazioni di licenza all'interno del file, consente alle pipeline automatizzate di prendere decisioni basate sui tag incorporati e assicura che i metadati viaggino con la grafica su tutte le piattaforme. Aspose.Page può elaborare file fino a 500 MB senza caricare l'intero documento in memoria, offrendo prestazioni rapide per carichi di lavoro su larga scala.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Conoscenza di base della programmazione Java.  
- Libreria Aspose.Page per Java installata. Puoi scaricarla **[qui](https://releases.aspose.com/page/java/)**.  
- Un file EPS di esempio contenente metadati. Se non ne hai uno, sentiti libero di usare il file **`xmp3.eps`** fornito.

## Importare i pacchetti
Prima, importa le classi di cui avrai bisogno. Le istruzioni di import rimangono esattamente le stesse dell'esempio originale:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Passo 1: Caricare il documento EPS e ottenere i metadati XMP
La classe `PsDocument` rappresenta un file EPS e fornisce metodi per accedere al suo contenuto e ai metadati.  
L'oggetto `XmpMetadata` contiene il pacchetto XMP associato al documento.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Passo 2: Aggiungere una proprietà Date
La classe `Date` rappresenta un istante specifico nel tempo, con precisione al millisecondo.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Passo 3: Aggiungere una proprietà Integer
La classe `Integer` incapsula un valore primitivo `int` come oggetto.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Passo 4: Aggiungere una proprietà Double
La classe `Double` incapsula un valore primitivo `double` come oggetto.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Passo 5: Aggiungere una proprietà String
La classe `String` rappresenta una sequenza di caratteri.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Passo 6: Salvare il file EPS aggiornato
Il metodo `save` scrive il documento modificato su disco, preservando la struttura EPS.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Passo 7: Pulire le risorse
Chiudi sempre i flussi per evitare perdite di handle di file e assicurati che tutti i buffer vengano svuotati.

```java
// Close input EPS stream
psStream.close();
```

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Null XMP metadata** | Il file EPS non conteneva alcun pacchetto XMP e la libreria non è riuscita a dedurre i commenti PS. | Assicurati che l'EPS di origine contenga almeno un commento PS (ad esempio, `%%Creator`). La libreria genererà automaticamente un pacchetto XMP minimale. |
| **Time zone mismatch** | Le date appaiono spostate quando aperte in un'altra applicazione. | Imposta `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` prima di creare l'oggetto `Date`, come mostrato nel Passo 2. |
| **License exception** | Il runtime genera `LicenseException`. | Applica una licenza valida di Aspose.Page prima di utilizzare l'API, oppure esegui in modalità di prova per la valutazione. |

## Domande frequenti
**Q: Posso usare Aspose.Page per Java con altri linguaggi di programmazione?**  
A: Aspose.Page supporta principalmente Java, ma sono disponibili librerie equivalenti per .NET, C++ e Python.

**Q: È disponibile una versione di prova gratuita per Aspose.Page per Java?**  
A: Sì, puoi esplorare le funzionalità di Aspose.Page ottenendo una prova gratuita **[qui](https://releases.aspose.com/)**.

**Q: Dove posso trovare la documentazione dettagliata per Aspose.Page per Java?**  
A: La documentazione è disponibile **[qui](https://reference.aspose.com/page/java/)**.

**Q: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
A: Una licenza temporanea può essere acquisita **[qui](https://purchase.aspose.com/temporary-license/)**.

**Q: Dove posso acquistare Aspose.Page per Java?**  
A: Puoi acquistare il prodotto **[qui](https://purchase.aspose.com/buy)**.

---

**Ultimo aggiornamento:** 2026-05-20  
**Testato con:** Aspose.Page per Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come leggere i metadati XMP usando Java – Guida Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page tutorial XMP – Aggiungere Namespace in XMP usando Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Aggiungere elementi di array nei metadati XMP usando Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}