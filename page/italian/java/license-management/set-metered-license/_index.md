---
date: 2025-12-03
description: Scopri come salvare EPS in PNG usando Aspose.Page per Java configurando
  una licenza a consumo. Guida passo‑passo con esempio di codice completo.
language: it
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Salva EPS come PNG con Aspose.Page Java (Licenza a consumo)
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva EPS come PNG con Aspose.Page Java (Licenza a consumo)

## Introduzione
Se hai bisogno di **salvare EPS come PNG** in un'applicazione Java e desideri un modo semplice per gestire la licenza, sei nel posto giusto. Questo tutorial ti guida nella configurazione di una licenza a consumo per Aspose.Page, nel caricamento di un file PostScript (EPS) e nella sua conversione in un'immagine PNG—tutto con passaggi chiari e concisi che puoi seguire subito.

## Risposte rapide
- **Cosa significa “salvare EPS come PNG”?** Converte un file EPS vettoriale in un'immagine raster PNG.  
- **Perché usare una licenza a consumo?** Ti consente di pagare solo per le pagine che elabori, ideale per carichi di lavoro variabili.  
- **È necessaria una connessione internet?** No, le chiavi a consumo vengono validate localmente.  
- **Quale versione di Java è richiesta?** Java 8 o superiore.  
- **Quanto tempo richiede la configurazione?** Circa 10 minuti per un'implementazione di base.

## Che cos'è “salvare EPS come PNG”?
Salvare EPS come PNG trasforma un documento Encapsulated PostScript scalabile in un formato bitmap ampiamente supportato. PNG conserva la trasparenza e offre compressione senza perdita, rendendolo ideale per grafiche web, miniature e anteprime di stampa.

## Perché usare Aspose.Page per questa attività?
- **Pure Java API** – nessuna dipendenza nativa.  
- **Alta fedeltà** – i grafici vettoriali vengono renderizzati con precisione.  
- **Licenza a consumo** – paghi solo per ciò che converti.  
- **Supporto per più formati di output** – PNG, JPEG, TIFF, ecc.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Conoscenze di base della programmazione Java.  
- Libreria Aspose.Page installata – scaricala da [here](https://releases.aspose.com/page/java/).  
- Chiavi pubbliche e private a consumo, ottenibili tramite il tuo account Aspose.

## Importa pacchetti
Per prima cosa, importa le classi necessarie. Mantieni il blocco di import esattamente come mostrato affinché il codice si compili senza modifiche.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Passo 1: Inizializza documento e formato immagine
Qui impostiamo le chiavi a consumo e definiamo il formato di output (PNG). Questa è la base per l'operazione di **salvare EPS come PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## Passo 2: Inizializza lo stream di input PostScript
Apri il file EPS che desideri convertire. Lo stream alimenta il documento in Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Passo 3: Verifica la licenza del documento
Verifica sempre che la licenza a consumo sia stata applicata correttamente prima di procedere con l'elaborazione.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Passo 4: Inizializza opzioni e dispositivo immagine
Crea l'oggetto delle opzioni che controlla le impostazioni di conversione e il dispositivo che riceverà l'immagine renderizzata.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Passo 5: Salva il file EPS come immagine
Questo è il cuore della chiamata **salvare EPS come PNG**. Il documento viene renderizzato nel dispositivo immagine usando le opzioni configurate.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Passo 6: Ottieni e salva i byte dell'immagine
Estrai i byte PNG dal dispositivo e scrivili su disco.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **License not recognized** | Le chiavi sono errate o posizionate nell'ordine sbagliato. | Ricontrolla le stringhe delle chiavi pubbliche/private e assicurati che `setMeteredKey` venga chiamato prima di qualsiasi elaborazione del documento. |
| **Output file is empty** | `device.getImagesBytes()` ha restituito `null`. | Verifica che il file EPS sia valido e che le `ImageSaveOptions` non siano impostate su una canvas di dimensione zero. |
| **OutOfMemoryError on large EPS** | Il rendering di file vettoriali di grandi dimensioni consuma molta memoria. | Elabora le pagine una alla volta o aumenta l'heap JVM (`-Xmx2g`). |

## Domande frequenti

**D: Come posso ottenere le chiavi pubbliche e private a consumo?**  
R: Puoi ottenere queste chiavi tramite il tuo account Aspose.

**D: La libreria Aspose.Page è gratuita?**  
R: Aspose.Page offre sia versioni di prova gratuite sia versioni a pagamento. Visita [here](https://releases.aspose.com/) per una prova gratuita.

**D: Posso usare Aspose.Page per progetti commerciali?**  
R: Sì, Aspose.Page offre licenze commerciali. Puoi acquistarle [here](https://purchase.aspose.com/buy).

**D: Dove posso trovare documentazione aggiuntiva?**  
R: Consulta la documentazione [here](https://reference.aspose.com/page/java/).

**D: Come posso ottenere licenze temporanee?**  
R: Le licenze temporanee possono essere ottenute [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
