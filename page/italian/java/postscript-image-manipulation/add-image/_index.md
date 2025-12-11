---
date: 2025-12-09
description: Scopri come creare documenti PostScript in Java e traslare e ruotare
  le immagini usando Aspose.Page per una manipolazione fluida delle immagini.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Creare documento PostScript in Java – Aggiungere immagine in PostScript Java
url: /it/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento PostScript Java – Aggiungi immagine in PostScript Java

## Introduzione
In questo tutorial, imparerai come **creare un documento PostScript Java** e incorporare immagini usando la libreria Aspose.Page per Java. Ti guideremo passo passo, dalla configurazione del documento all'applicazione di trasformazioni come le operazioni di **traslazione e rotazione dell'immagine**. Alla fine, sarai in grado di generare file PostScript ricchi programmaticamente e personalizzare il posizionamento delle immagini per adattarlo alle tue esigenze di layout.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java  
- **Posso aggiungere più immagini?** Sì – ripeti i passaggi di trasformazione e disegno  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita funziona per i test; è necessaria una licenza per la produzione  
- **Quale versione di Java è supportata?** Java 8 e successive  
- **La rotazione delle immagini è supportata?** Assolutamente – usa `AffineTransform.rotate()`

## Che cosa significa creare un documento PostScript in Java?
Un documento PostScript è un file di linguaggio di descrizione di pagina che descrive testo, grafica e immagini. Usando Aspose.Page, puoi generare questi file programmaticamente in Java, ottenendo il pieno controllo sul layout, sullo stato grafico e sulla gestione delle immagini senza necessità di un interprete PostScript.

## Perché usare Aspose.Page per la manipolazione delle immagini?
- **API di alto livello:** Semplifica i comandi PostScript complessi.  
- **Cross‑platform:** Funziona su qualsiasi OS che supporta Java.  
- **Controllo completo dello stato grafico:** Salva, ripristina, trasla, scala e ruota facilmente la grafica.  
- **Nessuna dipendenza esterna:** Gestisce il caricamento e la conversione delle immagini internamente.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere:

- Java Development Kit (JDK) installato sul tuo sistema.  
- Libreria Aspose.Page per Java. Puoi scaricarla [qui](https://releases.aspose.com/page/java/).  
- Una conoscenza di base della programmazione Java.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java. Usa il seguente frammento di codice come riferimento:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Passo 1: Scrivi il salvataggio della grafica
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

## Passo 2: Trasla e trasforma (trasla e ruota immagine)
Successivamente, trasla il documento e crea un oggetto `BufferedImage` dal file immagine. Applica una serie di trasformazioni come scaling e rotazione usando `AffineTransform`. È qui che avviene l'operazione di **traslazione e rotazione dell'immagine**.

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

## Passo 3: Aggiungi immagine al documento
Ora, aggiungi l'immagine trasformata al documento.

```java
document.drawImage(image, transform, null);
```

## Passo 4: Scrivi il ripristino della grafica
Dopo aver aggiunto l'immagine, scrivi il ripristino della grafica per finalizzare le modifiche apportate.

```java
document.writeGraphicsRestore();
```

## Passo 5: Chiudi la pagina corrente e salva
Chiudi la pagina corrente e salva il documento.

```java
document.closePage();
document.save();
```

Puoi ripetere questi passaggi per aggiungere più immagini o personalizzare le trasformazioni in base alle tue esigenze.

## Problemi comuni e soluzioni
- **FileNotFoundException:** Assicurati che il percorso `dataDir` termini con un separatore di file (`/` o `\\`) e che il nome del file immagine corrisponda esattamente.  
- **ImageIO.read returns null:** Verifica che il formato dell'immagine sia supportato (ad esempio, JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` si aspetta radianti. Converti i gradi in radianti (`Math.toRadians(degrees)`) se necessario.

## Domande frequenti

**D: Posso usare Aspose.Page per Java con altri linguaggi di programmazione?**  
R: Aspose.Page supporta principalmente Java, ma sono disponibili versioni per altri linguaggi di programmazione.

**D: È disponibile una versione di prova gratuita per Aspose.Page per Java?**  
R: Sì, puoi accedere alla versione di prova gratuita [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
R: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso trovare supporto della community e discussioni relative ad Aspose.Page per Java?**  
R: Visita il [Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto della community.

**D: Ci sono risorse aggiuntive per l'acquisto di Aspose.Page per Java?**  
R: Puoi acquistare la libreria [qui](https://purchase.aspose.com/buy).

## Conclusione
Congratulazioni! Hai imparato con successo come **creare un documento PostScript Java** e incorporare immagini usando Aspose.Page per Java. Esplora la [documentazione](https://reference.aspose.com/page/java/) per funzionalità più avanzate, come grafica vettoriale, rendering del testo e dimensioni di pagina personalizzate.

---

**Ultimo aggiornamento:** 2025-12-09  
**Testato con:** Aspose.Page for Java 23.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}