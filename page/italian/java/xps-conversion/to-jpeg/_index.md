---
date: 2025-12-23
description: Scopri come convertire XPS in JPEG in Java e scopri come convertire i
  file XPS in modo efficiente usando Aspose.Page. Una guida completa con istruzioni
  passo‑passo per un'integrazione senza problemi.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Come convertire XPS in JPEG in Java
url: /it/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come Convertire XPS in JPEG in Java

## Introduzione
In questo tutorial, **imparerai come convertire XPS in JPEG** usando la potente libreria Aspose.Page per Java. Convertire file XPS in formati immagine è una necessità comune quando è necessario visualizzare, anteporre o elaborare ulteriormente le pagine dei documenti in applicazioni web o desktop. Ti guideremo passo passo, spiegheremo perché ogni riga è importante e ti forniremo consigli pratici così potrai integrare la logica di conversione nei tuoi progetti con sicurezza.

## Risposte Rapide
- **Quale libreria gestisce la conversione?** Aspose.Page for Java  
- **Posso selezionare pagine specifiche?** Sì – usa `setPageNumbers` in `JpegSaveOptions`  
- **Quali impostazioni di qualità dell'immagine posso controllare?** Modalità di smoothing, risoluzione e impostazioni di qualità JPEG  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza commerciale (è disponibile una prova gratuita)  
- **Il codice è compatibile con Java 8?** Assolutamente – l'API funziona con Java 8 e versioni successive  

## Cos'è XPS e perché convertirlo in JPEG?
XPS (XML Paper Specification) è un formato di documento a layout fisso simile a PDF. Convertire XPS in JPEG è utile quando servono immagini raster per miniature, allegati email o quando si integra con sistemi che accettano solo file immagine. JPEG offre un buon equilibrio tra qualità visiva e dimensione del file, rendendolo ideale per anteprime basate sul web.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere quanto segue:

- **Ambiente di sviluppo Java** – JDK 8 o successivo installato e configurato.  
- **Aspose.Page per Java** – Scarica l'ultima libreria dal sito ufficiale [qui](https://releases.aspose.com/page/java/).  
- **Documento XPS di esempio** – Un file XPS che desideri trasformare in immagini JPEG.  

## Importare i Pacchetti
Inizia importando le classi necessarie nel tuo file sorgente Java:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Passo 1: Inizializzare i Percorsi e Caricare il Documento XPS
Imposta la directory che contiene il tuo file XPS di origine e crea un'istanza di `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Suggerimento professionale:** Usa `Paths.get()` da `java.nio.file` per gestire i percorsi in modo indipendente dalla piattaforma.

## Passo 2: Configurare le Opzioni di Salvataggio JPEG
Definisci come devono essere renderizzate le immagini JPEG — risoluzione, smoothing e quali pagine esportare:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` produce un output ad alta risoluzione adatto alla stampa.  
- `setPageNumbers` ti consente di scegliere solo le pagine necessarie, risparmiando tempo e memoria.

## Passo 3: Creare il Dispositivo di Rendering
`ImageDevice` cattura le pagine renderizzate come array di byte:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Passo 4: Renderizzare il Documento XPS in JPEG
Invoca il metodo `save`, passando il dispositivo e le opzioni che hai configurato:

```java
document.save(device, options);
```

A questo punto il `device` contiene un array bidimensionale dove ogni elemento rappresenta una pagina codificata in JPEG.

## Passo 5: Iterare sul Risultato e Scrivere i File
Scorri le pagine renderizzate e scrivi ogni array di byte in un file JPEG separato:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Ogni file sarà nominato `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, facilitando l'identificazione del documento di origine e del numero di pagina.

## Problemi Comuni e Risoluzione
| Sintomo | Causa Probabile | Soluzione |
|---------|-----------------|-----------|
| **File JPEG vuoti** | Stream di output non svuotato o chiuso correttamente | Assicurati che `imageStream.close()` sia chiamato all'interno del ciclo interno (come mostrato). |
| **Errori di out‑of‑memory** su file XPS grandi | Renderizzare tutte le pagine contemporaneamente consuma troppa RAM | Processa le pagine in batch più piccoli o aumenta l'heap JVM (`-Xmx`). |
| **Pagine mancanti** | `setPageNumbers` non include la pagina desiderata | Verifica che l'array dei numeri di pagina corrisponda agli indici reali delle pagine XPS (basati su 1). |

## Domande Frequenti

### Q: Aspose.Page è adatto per progetti commerciali?
A: Sì, Aspose.Page è un prodotto commerciale con opzioni di licenza disponibili. Controlla [qui](https://purchase.aspose.com/buy) per i dettagli.

### Q: Posso provare Aspose.Page prima di acquistarlo?
A: Sì, puoi ottenere una prova gratuita [qui](https://releases.aspose.com/).

### Q: Dove posso trovare la documentazione di Aspose.Page?
A: La documentazione è disponibile [qui](https://reference.aspose.com/page/java/).

### Q: Come posso ottenere supporto per Aspose.Page?
A: Visita il [Forum Aspose.Page](https://forum.aspose.com/c/page/39) per supporto basato sulla community.

### Q: È necessaria una licenza temporanea per i test?
A: Sì, puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

## Conclusione
Ora hai padroneggiato **come convertire XPS in JPEG** usando Aspose.Page per Java. Seguendo la guida passo passo, puoi integrare questa pipeline di conversione in qualsiasi applicazione Java — sia che si tratti di uno strumento desktop, di un servizio web o di un'utilità di elaborazione batch. Sentiti libero di sperimentare con diverse risoluzioni, selezioni di pagine e formati immagine per soddisfare le esigenze del tuo progetto.

---

**Ultimo aggiornamento:** 2025-12-23  
**Testato con:** Aspose.Page 24.11 for Java (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}