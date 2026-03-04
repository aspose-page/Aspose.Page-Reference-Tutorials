---
date: 2025-12-20
description: Scopri come creare metadati XMP EPS nei file EPS usando Aspose.Page per
  Java. Guida passo passo per aggiungere proprietà XMP semplici programmaticamente.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Come creare EPS con metadati XMP usando Java
url: /it/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere Proprietà Semplici in XMP usando Java

## Introduzione
Nei flussi di lavoro moderni per i documenti, poter **creare file EPS con metadati XMP** in modo programmatico ti dà il pieno controllo su come le tue grafiche sono descritte, ricercate e archiviate. Con Aspose.Page per Java puoi leggere, modificare e scrivere pacchetti XMP all'interno di documenti EPS senza uscire dall'ecosistema Java. In questo tutorial ti guideremo passo passo per aggiungere semplici proprietà XMP a un file EPS, così potrai arricchire le tue grafiche con metadati personalizzati in modo rapido e affidabile.

## Risposte Rapide
- **Cosa significa “creare xmp metadata eps”?** Aggiungere un pacchetto XMP (metadati basati su XML) a un file EPS.  
- **Quale libreria è necessaria?** Aspose.Page per Java (scaricabile dal sito Aspose).  
- **È necessaria una licenza per i test?** Una versione di prova gratuita funziona per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Quante righe di codice?** Meno di 30 righe di Java più alcune istruzioni di import.  
- **Posso aggiungere altri tipi di dati?** Sì – date, interi, double, stringhe e persino array sono supportati.

## Cos'è creare xmp metadata eps?
XMP (Extensible Metadata Platform) è uno standard per incorporare metadati ricchi all'interno dei file. Quando **crei XMP metadata EPS**, inserisci un pacchetto XML dentro un documento EPS (Encapsulated PostScript), consentendo alle applicazioni successive di leggere autore, data di creazione, tag personalizzati e molto altro.

## Perché aggiungere metadati XMP ai file EPS?
- **Indicizzabilità:** Consente l'indicizzazione automatica da parte dei sistemi DAM.  
- **Conformità:** Memorizza informazioni legali o di licenza direttamente nel file.  
- **Automazione:** Permette alle pipeline successive di prendere decisioni basate sui dati incorporati.  
- **Portabilità:** I metadati viaggiano con l'EPS, garantendo coerenza su tutte le piattaforme.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Conoscenze di base della programmazione Java.  
- Libreria Aspose.Page per Java installata. Puoi scaricarla **[qui](https://releases.aspose.com/page/java/)**.  
- Un file EPS di esempio contenente metadati. Se non ne hai uno, usa il file **`xmp3.eps`** fornito.

## Importare i Pacchetti
Per prima cosa, importa le classi necessarie. Gli import rimangono esattamente come nell'esempio originale:

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
Apriamo il file EPS, creiamo un'istanza di `PsDocument` e recuperiamo (o creiamo) il pacchetto XMP.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Passo 2: Aggiungere una proprietà Data
Aggiungere una data è semplice: crea un oggetto `Date` e inseriscilo nella mappa XMP.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Passo 3: Aggiungere una proprietà Intero
Puoi memorizzare identificatori numerici o versioni usando un valore intero.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Passo 4: Aggiungere una proprietà Double
I numeri in virgola mobile sono utili per misurazioni o valutazioni.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Passo 5: Aggiungere una proprietà Stringa
Tag testuali personalizzati (ad es., codici progetto) vengono salvati come stringhe.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Passo 6: Salvare il file EPS aggiornato
Dopo aver aggiunto tutte le proprietà, scrivi il documento nuovamente su disco.

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
Chiudi sempre lo stream di input per evitare perdite di handle di file.

```java
// Close input EPS stream
psStream.close();
```

## Problemi Comuni e Soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Metadati XMP nulli** | Il file EPS non conteneva alcun pacchetto XMP e la libreria non ha potuto inferire i commenti PS. | Assicurati che l'EPS di origine contenga almeno un commento PS (es., `%%Creator`). La libreria genererà automaticamente un pacchetto XMP minimale. |
| **Discrepanza del fuso orario** | Le date appaiono spostate quando aperte in un'altra applicazione. | Imposta `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` prima di creare l'oggetto `Date`, come mostrato nel Passo 2. |
| **Eccezione di licenza** | Il runtime lancia `LicenseException`. | Applica una licenza valida di Aspose.Page prima di usare l'API, oppure esegui in modalità trial per la valutazione. |

## Conclusione
Seguendo questi passaggi ora sai come **creare file EPS con metadati XMP** usando Aspose.Page per Java. Aggiungere proprietà semplici come date, interi, double e stringhe è diretto, e i file EPS risultanti contengono metadati ricchi e ricercabili che avvantaggiano qualsiasi workflow successivo.

## Domande Frequenti
### Posso usare Aspose.Page per Java con altri linguaggi di programmazione?
Aspose.Page supporta principalmente Java, ma esistono versioni disponibili per altri linguaggi come .NET.

### È disponibile una versione di prova gratuita per Aspose.Page per Java?
Sì, puoi esplorare le funzionalità di Aspose.Page ottenendo una prova gratuita [qui](https://releases.aspose.com/).

### Dove posso trovare la documentazione dettagliata per Aspose.Page per Java?
La documentazione è disponibile [qui](https://reference.aspose.com/page/java/).

### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
Una licenza temporanea può essere acquisita [qui](https://purchase.aspose.com/temporary-license/).

### Dove posso acquistare Aspose.Page per Java?
Puoi acquistare il prodotto [qui](https://purchase.aspose.com/buy).

---

**Ultimo aggiornamento:** 2025-12-20  
**Testato con:** Aspose.Page per Java 24.11 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}