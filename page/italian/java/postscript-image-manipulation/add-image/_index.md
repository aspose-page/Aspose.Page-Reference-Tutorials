---
date: 2026-02-15
description: Scopri come creare documenti PostScript Java e generare file di documenti
  PostScript con traslazione e rotazione delle immagini utilizzando Aspose.Page per
  Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Crea PostScript Java – Aggiungi immagine in PostScript Java
url: /it/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea PostScript Java – Aggiungi Immagine in Java PostScript

## Introduzione
In questo tutorial imparerai a **creare postscript java** documenti e incorporare immagini usando la libreria Aspose.Page per Java. Ti guideremo passo passo, dall'inizializzazione di un nuovo file PostScript all'applicazione delle trasformazioni **translate and rotate image**. Alla fine, sarai in grado di generare file PostScript in modo programmatico e controllare il posizionamento delle immagini con precisione pixel‑perfect—ideale per report automatici, flussi di stampa o qualsiasi scenario in cui è necessario **generate postscript document** da Java.

## Risposte Rapide
- **Quale libreria è necessaria?** Aspose.Page per Java  
- **Posso aggiungere più immagini?** Sì – ripeti i passaggi di trasformazione e disegno  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è richiesta una licenza per la produzione  
- **Quale versione di Java è supportata?** Java 8 e successive  
- **È supportata la rotazione dell'immagine?** Assolutamente – usa `AffineTransform.rotate()`  

## Che cosa è create postscript java?
Un'operazione **create postscript java** produce un file di descrizione di pagina PostScript che codifica testo, grafica vettoriale e immagini raster. Con Aspose.Page puoi costruire questi file direttamente dal codice Java, ottenendo il pieno controllo programmatico su layout, scaling e rotazione senza bisogno di un interprete PostScript separato.

## Perché usare Aspose.Page per la manipolazione delle immagini?
- **API di alto livello:** Astrae i comandi PostScript a basso livello in semplici metodi Java.  
- **Cross‑platform:** Funziona su qualsiasi OS che supporta Java.  
- **Controllo completo dello stato grafico:** Salva, ripristina, trasla, scala e ruota la grafica a piacere.  
- **Nessuna dipendenza esterna:** Gestisce il caricamento delle immagini, la conversione di formato e l'incorporamento internamente.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

- Java Development Kit (JDK) installato sul tuo sistema.  
- Libreria Aspose.Page per Java. Puoi scaricarla [qui](https://releases.aspose.com/page/java/).  
- Una conoscenza di base della programmazione Java.  

## Importare i Pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java. Usa il seguente snippet di codice come riferimento:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Passo 1: Scrivi il Salvataggio della Grafica
Il primo passo consiste nello scrivere il salvataggio della grafica nel documento. Questo garantisce che eventuali trasformazioni o modifiche successive possano essere annullate se necessario.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Passo 2: Trasla e Trasforma (translate and rotate image)
Successivamente, trasla il documento e crea un oggetto `BufferedImage` dal file immagine. Applica una serie di trasformazioni come scaling e rotazione usando `AffineTransform`. È qui che avviene l'operazione **translate and rotate image**.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Passo 3: Aggiungi l'Immagine al Documento
Ora, aggiungi l'immagine trasformata al documento.

```java
document.drawImage(image, transform, null);
```

## Passo 4: Scrivi il Ripristino della Grafica
Dopo aver aggiunto l'immagine, scrivi il ripristino della grafica per finalizzare le modifiche apportate.

```java
document.writeGraphicsRestore();
```

## Passo 5: Chiudi la Pagina Corrente e Salva
Chiudi la pagina corrente e salva il documento.

```java
document.closePage();
document.save();
```

Puoi ripetere questi passaggi per aggiungere più immagini o personalizzare le trasformazioni in base alle tue esigenze.

## Problemi Comuni e Soluzioni
- **FileNotFoundException:** Assicurati che il percorso `dataDir` termini con un separatore di file (`/` o `\\`) e che il nome del file immagine corrisponda esattamente.  
- **ImageIO.read restituisce null:** Verifica che il formato dell'immagine sia supportato (ad esempio JPEG, PNG).  
- **Angolo di rotazione errato:** `AffineTransform.rotate` si aspetta radianti. Converte i gradi in radianti (`Math.toRadians(degrees)`) se necessario.  

## Domande Frequenti

**D: Posso usare Aspose.Page per Java con altri linguaggi di programmazione?**  
R: Aspose.Page supporta principalmente Java, ma sono disponibili versioni per altri linguaggi di programmazione.

**D: È disponibile una prova gratuita per Aspose.Page per Java?**  
R: Sì, puoi accedere alla prova gratuita [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
R: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso trovare supporto della community e discussioni relative a Aspose.Page per Java?**  
R: Visita il [Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto della community.

**D: Ci sono risorse aggiuntive per l'acquisto di Aspose.Page per Java?**  
R: Puoi acquistare la libreria [qui](https://purchase.aspose.com/buy).

## Conclusione
Congratulazioni! Hai appreso con successo come **creare postscript java** documenti e incorporare immagini usando Aspose.Page per Java. Esplora la [documentazione](https://reference.aspose.com/page/java/) per funzionalità più avanzate, come grafica vettoriale, rendering del testo e dimensioni di pagina personalizzate.

---

**Ultimo aggiornamento:** 2026-02-15  
**Testato con:** Aspose.Page per Java 23.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}