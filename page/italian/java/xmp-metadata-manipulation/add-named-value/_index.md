---
date: 2026-09-19
description: Scopri come aggiungere valori nominati XMP ai file EPS usando Aspose.Page
  per Java – una guida passo‑passo con esempi di codice.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Aggiungi valore nominato in XMP usando Java
og_description: Come aggiungere valori nominati XMP ai file EPS usando Aspose.Page
  per Java. Segui questa guida concisa per inserire metadati personalizzati in pochi
  minuti.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Come aggiungere un valore nominato XMP nei file EPS usando Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Come aggiungere un valore nominato XMP nei file EPS usando Java
url: /it/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere valore denominato nei metadati XMP usando Java

## Introduzione
Nello sviluppo Java moderno, imparare **come aggiungere XMP** nei metadati all'interno dei file EPS è essenziale per preservare la provenienza dei documenti e migliorare la ricercabilità. Con **Aspose.Page for Java**, è possibile inserire facilmente valori denominati personalizzati nel pacchetto XMP. Questo tutorial ti guida attraverso i passaggi esatti—completi di snippet di codice—così potrai iniziare ad aggiungere metadati XMP ai tuoi documenti EPS oggi.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java (Aspose)  
- **Quale tipo di file è l'obiettivo?** File EPS contenenti metadati XMP  
- **Caso d'uso principale?** Aggiungere valori denominati personalizzati (ad esempio, limiti di dimensione della pagina) a XMP  
- **Prerequisiti?** JDK 8+ e la libreria Aspose.Page for Java  
- **Tempo tipico di implementazione?** 5–10 minuti una volta configurata la libreria  

## Cos'è Aspose?
Aspose è l'abbreviazione di Aspose, una suite di API che consentono agli sviluppatori di creare, modificare, convertire e renderizzare una vasta gamma di formati di documento senza richiedere software esterno. Il componente Aspose.Page for Java si concentra specificamente sull'elaborazione di PostScript ed EPS, fornendo accesso programmatico al contenuto della pagina, alla grafica e ai metadati come XMP.

## Perché aggiungere valori denominati ai metadati XMP?
I valori denominati ti consentono di memorizzare coppie chiave‑valore arbitrarie direttamente all'interno del pacchetto XMP, rendendole immediatamente leggibili dagli strumenti a valle. Questo migliora la compatibilità con i motori di ricerca, abilita l'automazione dei flussi di lavoro e soddisfa i requisiti di conformità incorporando informazioni normative senza alterare il contenuto visivo.

## Perché è importante
Aggiungere valori denominati a XMP ti permette di memorizzare coppie chiave‑valore arbitrarie che possono essere lette senza analizzare l'intero file EPS. Questa capacità è particolarmente preziosa nelle pipeline di pubblicazione automatizzate, nei sistemi di gestione delle risorse digitali e nei flussi di lavoro guidati dalla conformità, dove i metadati guidano le azioni a valle.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- **Java Development Kit (JDK):** Un JDK recente (8 o superiore) installato sulla tua macchina.  
- **Aspose.Page for Java Library:** Scaricala dalla pagina ufficiale [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Aggiungi il JAR al classpath del tuo progetto.  
- **Un file EPS** che contiene già i metadati XMP o che li avrà generati automaticamente.

## Importare i pacchetti
Inizia importando i pacchetti Java necessari. Queste importazioni ti danno accesso a flussi di file, al modello di documento EPS e alle classi di gestione XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Come aggiungere un valore denominato XMP nei file EPS usando Java
Per aggiungere un valore denominato, carica il file EPS con un `FileInputStream`, recupera o crea il suo oggetto `XmpMetadata`, inserisci il `NamedValue` desiderato nello spazio dei nomi appropriato, quindi scrivi il documento modificato utilizzando un `FileOutputStream`. Aspose.Page gestisce automaticamente la creazione del pacchetto XMP se mancante, garantendo che i nuovi metadati vengano incorporati correttamente.

### Passo 1: Inizializzare lo stream del file EPS di input
**FileInputStream** è una classe I/O Java che legge byte grezzi da un file. Carica il file EPS di origine in un `FileInputStream`. Questo stream fornisce il documento all'API di Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Suggerimento:** Mantieni la variabile `dataDir` configurabile in modo che lo stesso codice funzioni in diversi ambienti.

### Passo 2: Ottenere i metadati XMP
**XmpMetadata** rappresenta il pacchetto XMP associato a un documento EPS. Recupera il pacchetto XMP esistente; se il file EPS non ne contiene uno, Aspose crea un nuovo oggetto XMP popolato dai commenti PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Passo 3: Aggiungere valore denominato
**NamedValue** è una coppia chiave‑valore memorizzata all'interno dello spazio dei nomi dei metadati XMP. Inserisci un valore denominato personalizzato nella struttura XMP. In questo esempio aggiungiamo una nuova chiave nello spazio dei nomi `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Perché è importante:** I valori denominati ti consentono di memorizzare coppie chiave‑valore arbitrarie che le applicazioni a valle possono leggere senza analizzare l'intero documento.

### Passo 4: Inizializzare lo stream del file EPS di output
**FileOutputStream** è una classe I/O Java che scrive byte grezzi su un file. Prepara un `FileOutputStream` dove verrà salvato l'EPS modificato.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Passo 5: Salvare il documento
Il metodo `save` persiste le modifiche. Scrive il pacchetto XMP aggiornato nuovamente nel file EPS, garantendo che il nuovo valore denominato diventi parte dei metadati del documento.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Passo 6: Chiudere lo stream del file EPS di input
Chiudere il gestore del file originale previene perdite di risorse e garantisce che il file non sia bloccato per operazioni successive.

```java
psStream.close();
```

Seguendo questi sei passaggi, hai aggiunto con successo **un valore denominato nei metadati XMP** usando **Aspose.Page for Java**.

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| `NullPointerException` on `xmp` | Il file EPS non contiene XMP e Aspose non è riuscito a generarne uno | Assicurati che l'EPS contenga almeno un commento PS o crea manualmente una nuova istanza `XmpMetadata`. |
| Il file di output è vuoto | Stream di output non svuotato/chiuso | Verifica che `outPsStream.close()` sia chiamato in un blocco `finally` (come mostrato). |
| Errore di chiave duplicata | Stesso valore denominato aggiunto due volte | Verifica se la chiave esiste già con `xmp.containsNamedValue(...)` prima di aggiungerla. |

## Domande frequenti

**Q: Posso usare Aspose.Page for Java con altre librerie Java?**  
A: Sì, Aspose.Page for Java è progettato per funzionare senza problemi con altre librerie Java, offrendo flessibilità nel tuo ambiente di sviluppo.

**Q: È disponibile una versione di prova gratuita per Aspose.Page for Java?**  
A: Sì, puoi accedere a una prova gratuita di Aspose.Page for Java nella [pagina di rilascio di Aspose](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per Aspose.Page for Java?**  
A: Visita la [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea per Aspose.Page for Java.

**Q: Dove posso trovare altri tutorial ed esempi per Aspose.Page for Java?**  
A: Esplora la [documentazione](https://reference.aspose.com/page/java/) per tutorial ed esempi completi.

**Q: Aspose.Page for Java è adatto a progetti su larga scala?**  
A: Assolutamente, Aspose.Page for Java è progettato per gestire progetti su larga scala in modo efficiente, fornendo robuste capacità di manipolazione dei documenti.

## Conclusione
In questa guida abbiamo dimostrato come **Aspose.Page for Java** renda semplice **aggiungere valori denominati ai metadati XMP** nei file EPS. Con i passaggi sopra, puoi arricchire i tuoi documenti con metadati personalizzati, migliorare la ricercabilità e abilitare un'elaborazione a valle più intelligente.

---

**Last Updated:** 2026-09-19  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Tutorial correlati

- [Come aggiungere lo spazio dei nomi XMP nei file EPS usando Aspose.Page – Tutorial Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Aggiungere metadati XMP ai file EPS usando Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Leggere XMP usando Aspose.Page – Guida Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}