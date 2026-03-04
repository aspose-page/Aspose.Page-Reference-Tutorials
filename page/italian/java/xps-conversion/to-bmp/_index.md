---
date: 2025-12-21
description: Scopri come impostare la risoluzione durante la conversione da XPS a
  BMP in Java usando Aspose.Page. Questa guida alla conversione di immagini Java garantisce
  risultati di alta qualità.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Come impostare la risoluzione durante la conversione da XPS a BMP in Java
url: /it/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti XPS in BMP in Java

## Introduzione
Benvenuti in questa guida passo‑a‑passo su **come impostare la risoluzione** quando si convertono file XPS (XML Paper Specifica) in formato BMP (Bitmap) in Java utilizzando Aspose.Page. Aspose.Page per Java è una libreria potente che offre funzionalità complete per lavorare con documenti XPS. In questo tutorial, vi guideremo attraverso il processo di conversione dei file XPS in immagini BMP senza sforzo.

## Risposte rapide
- **Quale libreria dovrei usare?** Aspose.Page per Java fornisce le funzionalità di conversione XPS→BMP più completa.
- **Posso controllare la qualità dell'immagine?** Sì – usa `BmpSaveOptions` per impostare la risoluzione e la modalità di smoothing.
- **Devo convertire solo pagine specifiche?** Assolutamente, `options.setPageNumbers()` ti permette di scegliere le pagine esatte.
- **È una vera conversione di immagini java?** L'API rende le pagine XPS direttamente in dati bitmap, quindi non sono necessari formati intermedi.
- **Quale versione di Java è supportata?** Tutte le versioni moderne di Java (8 e successive) sono compatibili.

## Qual è lo scopo dell'impostazione della risoluzione?
La risoluzione determina il numero di punti per pollice (DPI) nell'immagine BMP generata. Un DPI più alto produce immagini più nitide, fondamentale per la stampa o lavori grafici dettagliati. Regolare la risoluzione ti dà il pieno controllo sulla qualità dell'output del tuo flusso di lavoro **java convert xps**.

## Perché utilizzare Aspose.Page per la conversione XPS→BMP?
- **Alta fedeltà**: conserva la qualità vettoriale dell'XPS originale.
- **Fine‑grained control** – puoi impostare DPI, smoothing e persino selezionare pagine specifiche da convertire.
- **Nessuna dipendenza esterna** – puro Java, nessuna libreria nativa richiesta.
- **Scalable** – funziona sia per documenti a pagina singola sia per grandi file XPS multi‑pagina.

## Prerequisiti
Prima di immergerti nel processo di conversione, assicurati di avere i seguenti prerequisiti:
- **Java Development Environment** – Java 8o versioni successive installate sulla tua macchina.
- **Aspose.Page for Java Library** – Scarica e include la libreria Aspose.Page for Java nel tuo progetto. Puoi trovare la libreria [qui](https://releases.aspose.com/page/java/).
- **Sample XPS File** – Prepara un documento XPS di esempio che desideri convertire in BMP.

## Importa pacchetti
Includi i pacchetti Aspose.Page necessari nel tuo codice Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Come impostare la risoluzione per la conversione da XPS a BMP
Di seguito è riportata una breve guida numerata che mostra esattamente dove e come impostare la risoluzione, nonché come **convertire pagine specifiche**.

### Passaggio 1: Caricare il documento XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Passaggio 2: Inizializzare le opzioni (risoluzione e selezione pagina)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Passaggio 3: Creare un dispositivo di rendering
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Passaggio 4: Salvare il documento utilizzando le opzioni
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Passaggio 5: Scorrere le immagini renderizzate e scrivere i file
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Ripeti questi passaggi per qualsiasi ulteriore personalizzazione o modifica di cui potresti aver bisogno nel processo di conversione.

## Problemi e soluzioni comuni
| Problema | Soluzione |
|-------|----------|
| **Uscita BMP di bassa qualità** | Verificare che `options.setResolution()` sia impostato su un valore ≥300 DPI. |
| **Viene convertita solo una parte del documento** | Assicurati che `options.setPageNumbers()` include tutti gli indici della pagina desiderata. |
| **OutOfMemoryError su file XPS di grandi dimensioni** | Elabora il documento in partizioni più piccole o aumenta la dimensione dell'heap JVM (`-Xmx`). |
| **File non trovato** | Controlla nuovamente il percorso `dataDir` e verifica che il file XPS di input esista. |

## Domande frequenti
### D: Posso personalizzare la risoluzione delle immagini BMP?
R: Sì, puoi regolare la risoluzione modificando il parametro `options.setResolution()` nel codice.

### D: Aspose.Page è compatibile con diverse versioni di Java?
R: Sì, Aspose.Page supporta un'ampia gamma di versioni di Java. Assicurati di aver installato una versione compatibile.

### D: Come posso convertire i file XPS da un intervallo di pagine specifico?
R: Utilizza il metodo `options.setPageNumbers()` per specificare i numeri di pagina che desideri convertire.

### D: Aspose.Page supporta altri formati di output?
R: Sì, Aspose.Page supporta diversi formati di output. Consulta la documentazione per un elenco completo.

### D: Dove posso trovare ulteriore assistenza o supporto?
R: Visita il [Forum di Aspose.Page](https://forum.aspose.com/c/page/39) per supporto e discussioni della community.

---

**Ultimo aggiornamento:** 21/12/2025
**Testato con:** Aspose.Page per Java 24.12
**Autore:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}