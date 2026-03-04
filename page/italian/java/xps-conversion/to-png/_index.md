---
date: 2025-12-23
description: Converti senza sforzo **XPS in PNG** in Java usando Aspose.Page. Questa
  guida mostra come renderizzare XPS in file immagine con una soluzione affidabile
  e orientata agli sviluppatori.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Converti XPS in PNG in Java
url: /it/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertire XPS in PNG in Java

## Introduzione
Nel dinamico mondo dello sviluppo software, la necessità di **convertire XPS in PNG** (XML Paper Specification in Portable Network Graphics) si presenta frequentemente. Per eseguire questo compito senza problemi in Java, Aspose.Page fornisce una soluzione potente. In questo tutorial, illustreremo il processo di conversione da XPS a PNG usando Aspose.Page per Java.

## Risposte Rapide
- **Quale libreria gestisce la conversione?** Aspose.Page for Java  
- **Quali formati sono coinvolti?** XPS (origine) → PNG (output)  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza commerciale  
- **Posso impostare la risoluzione dell'immagine?** Sì, usando `PngSaveOptions.setResolution()`  
- **È possibile selezionare pagine specifiche?** Assolutamente – fornire i numeri di pagina nell'oggetto delle opzioni  

## Perché convertire XPS in PNG?
Il rendering di XPS in file immagine è utile quando è necessario visualizzare documenti sul web, incorporarli in report o generare miniature per l'anteprima. PNG offre compressione senza perdita e ampio supporto nei browser, rendendolo una scelta ideale per rappresentazioni visive ad alta qualità del contenuto XPS.

## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti configurati:
1. Java Development Kit (JDK): Assicurati di avere il JDK installato sul tuo sistema.  
2. Aspose.Page per Java: Scarica e installa la libreria Aspose.Page. Puoi trovare il link per il download [qui](https://releases.aspose.com/page/java/).  
3. Integrated Development Environment (IDE): Scegli un IDE compatibile con Java come IntelliJ IDEA o Eclipse.  

## Come convertire XPS in PNG in Java
Di seguito è una guida passo‑passo che spiega **come convertire XPS** in immagini PNG, includendo snippet di codice che puoi copiare direttamente nel tuo progetto.

### Importare i pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per utilizzare le funzionalità di Aspose.Page. Aggiungi le seguenti istruzioni di import all'inizio del tuo file Java:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Passo 1: Impostare la directory del documento
Definisci la cartella che contiene il tuo file XPS di origine e dove verranno salvati i file PNG.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Passo 2: Caricare il documento XPS
Crea un'istanza `XpsDocument` che carica il file XPS di origine.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Passo 3: Inizializzare le opzioni
Configura le opzioni di output PNG. Qui puoi impostare l'anti-aliasing, la risoluzione e specificare quali pagine renderizzare.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Passo 4: Creare il dispositivo di rendering
Crea un `ImageDevice` che conterrà i dati dell'immagine renderizzata.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Passo 5: Salvare e iterare
Renderizza il documento XPS, quindi scrivi ogni array di byte PNG generato su un file su disco.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Seguendo questi passaggi, puoi facilmente **renderizzare XPS in file immagine** in formato PNG usando Aspose.Page per Java.

## Conclusione
In conclusione, Aspose.Page per Java semplifica il processo di conversione da XPS a PNG, fornendo agli sviluppatori uno strumento affidabile ed efficiente. Integra questa libreria nei tuoi progetti Java per semplificare le attività di manipolazione dei documenti.

## Domande Frequenti Aggiuntive

**Q: Posso convertire solo pagine selezionate di un file XPS?**  
A: Assolutamente. Usa il metodo `setPageNumbers` in `PngSaveOptions` per specificare le pagine che desideri renderizzare.

**Q: Quale risoluzione dell'immagine è consigliata per PNG ad alta qualità?**  
A: Una risoluzione di 300 dpi è un buon equilibrio tra qualità e dimensione del file, ma puoi regolarla tramite `options.setResolution()`.

**Q: L'API supporta la conversione multithread per documenti di grandi dimensioni?**  
A: Sì, puoi invocare la logica di conversione in thread paralleli, ognuno gestendo una pagina diversa o una partizione del documento.

**Q: Come gestire l'uso della memoria quando si convertono file XPS molto grandi?**  
A: Processa le pagine in modo sequenziale e rilascia il `FileOutputStream` dopo ogni scrittura, come mostrato nel codice di esempio.

**Q: È possibile aggiungere metadati personalizzati ai file PNG generati?**  
A: Sebbene `PngSaveOptions` non esponga direttamente i campi dei metadati, puoi post‑processare il PNG usando librerie di immagini standard per incorporare i metadati.

---

**Ultimo aggiornamento:** 2025-12-23  
**Testato con:** Aspose.Page for Java 24.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}