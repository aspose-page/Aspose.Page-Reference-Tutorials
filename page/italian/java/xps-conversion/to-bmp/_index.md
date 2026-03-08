---
date: 2026-03-08
description: Scopri come convertire XPS in BMP in Java e impostare la risoluzione
  BMP utilizzando la libreria di conversione immagini Aspose.Page per Java. Questa
  guida copre output ad alta qualità e consigli per risparmiare memoria.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Converti XPS in BMP in Java – Imposta la risoluzione per un output di alta
  qualità
url: /it/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti XPS in BMP in Java

## Introduction
Benvenuti a questa guida passo‑per‑passo su come **convertire XPS in BMP** in Java e impostare la risoluzione per una qualità dell'immagine ottimale utilizzando Aspose.Page. Che stiate creando una pipeline di stampa, generando miniature o abbiate bisogno di grafica ad alta risoluzione, controllare i DPI vi offre la flessibilità per soddisfare qualsiasi requisito.

## Quick Answers
- **Quale libreria dovrei usare?** Aspose.Page per Java è la più completa **java image conversion library** per XPS → BMP.  
- **Posso controllare la qualità dell'immagine?** Sì – usa `BmpSaveOptions` per **impostare la risoluzione BMP** e la modalità di smoothing.  
- **Come evito OutOfMemoryError in Java quando elaboro file XPS di grandi dimensioni?** Renderizza le pagine in partizioni o aumenta l'heap JVM (`-Xmx`).  
- **Devo convertire solo pagine specifiche?** Assolutamente, `options.setPageNumbers()` ti consente di scegliere le pagine esatte.  
- **Quali versioni di Java sono supportate?** Tutte le versioni moderne di Java (8 e successive) funzionano senza problemi.

## What is the purpose of setting resolution?
La risoluzione determina il numero di punti per pollice (DPI) nell'immagine BMP generata. Un DPI più alto produce immagini più nitide, essenziali per la stampa o lavori grafici dettagliati. Regolare la risoluzione ti dà il pieno controllo sulla qualità dell'output del tuo **convert xps to bmp** workflow.

## Why use Aspose.Page for XPS → BMP conversion?
- **Alta fedeltà** – conserva la qualità vettoriale dell'XPS originale.  
- **Controllo granulare** – puoi impostare DPI, smoothing e persino selezionare pagine specifiche da convertire.  
- **Nessuna dipendenza esterna** – puro Java, nessuna libreria nativa richiesta.  
- **Scalabile** – funziona per documenti a pagina singola così come per grandi file XPS multi‑pagina.  

## Prerequisites
Prima di immergerti nel processo di conversione, assicurati di avere i seguenti requisiti:
- **Ambiente di sviluppo Java** – Java 8 o versioni successive installate sulla tua macchina.  
- **Libreria Aspose.Page per Java** – Scarica e includi la libreria Aspose.Page per Java nel tuo progetto. Puoi trovare la libreria [qui](https://releases.aspose.com/page/java/).  
- **File XPS di esempio** – Prepara un documento XPS di esempio che desideri convertire in BMP.

## Import Packages
Include the necessary Aspose.Page packages in your Java code:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## How to Set Resolution for XPS to BMP Conversion
Di seguito trovi una guida concisa e numerata che mostra esattamente dove e come impostare la risoluzione, oltre a come **convertire pagine specifiche**.

### Step 1: Load XPS Document
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Step 2: Initialize Options (Resolution & Page Selection)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Step 3: Create Rendering Device
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Step 4: Save Document Using Options
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Step 5: Iterate Through Rendered Images and Write Files
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

## How to Avoid OutOfMemoryError Java When Converting Large XPS Files
- **Elabora in partizioni** – L'esempio già renderizza il documento in partizioni (`device.getResult()`), riducendo la pressione sulla memoria.  
- **Aumenta l'heap JVM** – Usa il flag `-Xmx` (ad es., `-Xmx2g`) per allocare più memoria per documenti di grandi dimensioni.  
- **Rilascia le risorse** – Chiama `document.close()` quando hai finito per liberare le risorse native.

## Common Issues and Solutions
| Problema | Soluzione |
|----------|-----------|
| **Output BMP di bassa qualità** | Verifica che `options.setResolution()` sia impostato a un valore ≥ 300 DPI. |
| **Solo una parte del documento è convertita** | Assicurati che `options.setPageNumbers()` includa tutti gli indici di pagina desiderati. |
| **OutOfMemoryError su file XPS di grandi dimensioni** | Elabora il documento in partizioni più piccole o aumenta la dimensione dell'heap JVM (`-Xmx`). |
| **File non trovato** | Controlla nuovamente il percorso `dataDir` e che il file XPS di input esista. |

## Frequently Asked Questions
### Q: Posso personalizzare la risoluzione delle immagini BMP?
A: Sì, puoi regolare la risoluzione modificando il parametro `options.setResolution()` nel codice.

### Q: Aspose.Page è compatibile con diverse versioni di Java?
A: Sì, Aspose.Page supporta un'ampia gamma di versioni Java. Assicurati di avere una versione compatibile installata.

### Q: Come posso convertire file XPS da un intervallo di pagine specifico?
A: Usa il metodo `options.setPageNumbers()` per specificare i numeri di pagina che desideri convertire.

### Q: Ci sono altri formati di output supportati da Aspose.Page?
A: Sì, Aspose.Page supporta vari formati di output. Consulta la documentazione per un elenco completo.

### Q: Dove posso trovare ulteriore aiuto o supporto?
A: Visita il [Forum Aspose.Page](https://forum.aspose.com/c/page/39) per supporto della community e discussioni.

---

**Ultimo aggiornamento:** 2026-03-08  
**Testato con:** Aspose.Page for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}