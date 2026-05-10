---
date: 2026-02-05
description: Scopri come salvare EPS in PNG usando Aspose.Page per Java configurando
  una licenza a consumo. Guida passo‑passo con esempio di codice completo.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Salva EPS come PNG con Aspose.Page Java (Licenza a consumo)
url: /it/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva EPS come PNG con Aspose.Page Java (Licenza a consumo)

## Introduzione
Se hai bisogno di **salvare EPS come PNG** in un'applicazione Java e desideri un modo semplice per gestire la licenza, sei nel posto giusto. Questo tutorial ti guida nella configurazione di una licenza a consumo per Aspose.Page, nel caricamento di un file PostScript (EPS) e nella sua conversione in un'immagine PNG—tutto con passaggi chiari e concisi che puoi seguire subito. Alla fine comprenderai anche come **renderizzare EPS in PNG** in modo efficiente e come scrivere codice **write PNG file Java** che funzioni in ambienti di produzione.

## Risposte rapide
- **Cosa significa “salvare EPS come PNG”?** Converte un file EPS vettoriale in un'immagine raster PNG.  
- **Perché usare una licenza a consumo?** Ti consente di pagare solo per le pagine che elabori, perfetto per carichi di lavoro variabili.  
- **È necessaria una connessione internet?** No, le chiavi a consumo vengono validate localmente.  
- **Quale versione di Java è richiesta?** Java 8 o superiore.  
- **Quanto tempo richiede l'installazione?** Circa 10 minuti per un'implementazione di base.  

## Cos'è “salvare EPS come PNG”?
Salvare EPS come PNG trasforma un documento Encapsulated PostScript scalabile in un formato bitmap ampiamente supportato. PNG mantiene la trasparenza e offre compressione senza perdita, rendendolo ideale per grafica web, miniature e anteprime di stampa.

## Perché renderizzare EPS in PNG con Aspose.Page?
- **Pure Java API** – nessuna dipendenza nativa, quindi può essere eseguita ovunque sia supportata la JVM.  
- **Rendering ad alta fedeltà** – i grafici vettoriali vengono rasterizzati con precisione, preservando la qualità delle linee.  
- **Licenza a consumo** – paghi solo per ciò che converti, mantenendo i costi prevedibili.  
- **Molteplici opzioni di output** – oltre a PNG puoi generare anche JPEG, TIFF e altro, offrendoti flessibilità per diversi progetti.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Conoscenze di base della programmazione Java.  
- Libreria Aspose.Page installata – scaricala da [here](https://releases.aspose.com/page/java/).  
- Chiavi pubbliche e private a consumo, ottenibili tramite il tuo account Aspose.

## Importare i pacchetti
Per prima cosa, importa le classi necessarie. Mantieni il blocco di import esattamente come mostrato affinché il codice compili senza modifiche.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Come salvare EPS come PNG usando Aspose.Page Java
Di seguito trovi la guida passo‑passo che combina licenza, caricamento, rendering e scrittura del file PNG finale.

### Passo 1: Inizializzare il documento e il formato immagine
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

### Passo 2: Inizializzare lo stream di input PostScript
Apri il file EPS che desideri convertire. Lo stream alimenta il documento in Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Passo 3: Verificare la licenza del documento
Controlla sempre che la licenza a consumo sia stata applicata correttamente prima dell'elaborazione.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Passo 4: Inizializzare le opzioni e il dispositivo immagine
Crea l'oggetto delle opzioni che controlla le impostazioni di conversione e il dispositivo che riceverà l'immagine renderizzata.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Passo 5: Salvare il file EPS come immagine
Questa è la chiamata centrale di **salvare EPS come PNG**. Il documento viene renderizzato nel dispositivo immagine usando le opzioni configurate.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Passo 6: Ottenere e salvare i byte dell'immagine
Estrai i byte PNG dal dispositivo e scrivili su disco. Questo passaggio dimostra come **write PNG file Java** in modo sicuro.

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
| **Licenza non riconosciuta** | Le chiavi sono errate o posizionate nell'ordine sbagliato. | Controlla le stringhe delle chiavi pubbliche/privati e assicurati che `setMeteredKey` venga chiamato prima di qualsiasi elaborazione del documento. |
| **Il file di output è vuoto** | `device.getImagesBytes()` ha restituito `null`. | Verifica che il file EPS sia valido e che le `ImageSaveOptions` non impostino una canvas di dimensioni zero. |
| **OutOfMemoryError su EPS grandi** | Il rendering di file vettoriali di grandi dimensioni consuma molta memoria. | Elabora le pagine una alla volta o aumenta l'heap JVM (`-Xmx2g`). |

## Domande frequenti

**D: Come ottengo le chiavi pubbliche e private a consumo?**  
R: Puoi ottenerle tramite il tuo account Aspose.

**D: La libreria Aspose.Page è gratuita?**  
R: Aspose.Page offre sia versioni di prova gratuite sia versioni a pagamento. Visita [here](https://releases.aspose.com/) per una prova gratuita.

**D: Posso usare Aspose.Page per progetti commerciali?**  
R: Sì, Aspose.Page offre licenze commerciali. Puoi acquistarle [here](https://purchase.aspose.com/buy).

**D: Dove posso trovare documentazione aggiuntiva?**  
R: Consulta la documentazione [here](https://reference.aspose.com/page/java/).

**D: Come posso ottenere licenze temporanee?**  
R: Le licenze temporanee sono disponibili [here](https://purchase.aspose.com/temporary-license/).

**D: Cosa fare se devo convertire file EPS multi‑pagina?**  
R: Itera su ogni pagina usando `device.getImagesBytes()` e scrivi ogni array di byte in un file PNG separato.

**D: Posso modificare la qualità o la profondità colore del PNG?**  
R: Sì, configura `ImageSaveOptions` (ad es., `options.setCompressionLevel(...)`) prima di chiamare `document.save(...)`.

---

**Ultimo aggiornamento:** 2025-12-03  
**Testato con:** Aspose.Page 24.12 per Java  
**Autore:** Aspose  

**Ultimo aggiornamento:** 2026-02-05  
**Testato con:** Aspose.Page 24.12 per Java (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}