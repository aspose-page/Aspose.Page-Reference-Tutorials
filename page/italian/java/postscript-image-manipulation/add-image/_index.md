---
date: 2026-08-23
description: Scopri come utilizzare aspose.page image manipulation java per incorporare
  e ruotare immagini nei file PostScript con chiari esempi Java.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Aggiungi immagine in Java PostScript
og_description: Scopri come utilizzare aspose.page image manipulation java per incorporare
  e ruotare immagini nei file PostScript, con esempi di codice Java passo‑passo.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Come usare aspose.page image manipulation java per aggiungere un'immagine
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Come usare aspose.page image manipulation java per aggiungere un'immagine
url: /it/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare aspose.page image manipulation java per aggiungere un'immagine

## Introduzione
In questo tutorial imparerai a **utilizzare aspose.page image manipulation java** per creare file PostScript, incorporare immagini raster e applicare trasformazioni di traslazione e rotazione. Alla fine della guida sarai in grado di generare output PostScript pixel‑perfect da Java—ideale per report automatizzati, pipeline di stampa o qualsiasi flusso di lavoro che richieda un posizionamento preciso delle immagini all'interno di un documento PostScript.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page per Java  
- **Posso aggiungere più immagini?** Sì – ripeti i passaggi di trasformazione e disegno per ciascuna immagine  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza per la produzione  
- **Quale versione di Java è supportata?** Java 8 e successive  
- **È supportata la rotazione delle immagini?** Assolutamente – usa `AffineTransform.rotate()`  

## Che cos'è aspose.page image manipulation java?
`aspose.page image manipulation java` è l'API Aspose.Page che consente di costruire, modificare e renderizzare documenti PostScript da codice Java, includendo il pieno controllo su posizionamento, scalatura e rotazione delle immagini. Con questa API eviti la sintassi PostScript di basso livello e lasci che la libreria gestisca internamente la conversione del formato e l'incorporamento.

## Perché usare aspose.page per la manipolazione delle immagini?
Aspose.Page fornisce **oltre 50 formati immagine** (inclusi JPEG, PNG, BMP, TIFF) e può incorporarli in PostScript senza caricare l'intero documento in memoria, consentendo l'elaborazione di file con centinaia di pagine mantenendo l'uso di memoria sotto i 100 MB su un server tipico. L'API di alto livello astrae comandi PostScript complessi, così scrivi codice Java conciso invece di operatori PS grezzi.

## Prerequisiti
- Java Development Kit (JDK) 8 o successivo installato.  
- Libreria Aspose.Page per Java – scaricala dalla **[pagina di download di Aspose.Page per Java](https://releases.aspose.com/page/java/)**.  
- Familiarità di base con la sintassi Java e la programmazione orientata agli oggetti.

## Che cos'è create postscript java?
Creare un file PostScript da Java significa generare programmaticamente un documento `.ps` che descrive layout di pagina, grafica vettoriale e immagini raster usando il linguaggio PostScript. Aspose.Page traduce le tue chiamate Java in istruzioni PostScript valide, permettendoti di produrre file pronti per la stampa senza un interprete PostScript separato.

## Come aggiungere un'immagine con traslazione e rotazione passo dopo passo

Carica la tua immagine, applica un `AffineTransform` e disegnala sulla pagina. I passaggi seguenti descrivono la sequenza esatta da seguire.

### Passo 1: scrivi salvataggio grafico
Il salvataggio dello stato grafico isola le tue trasformazioni così da poterle ripristinare in seguito. Questo equivale all'operatore `gsave` in PostScript grezzo.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Passo 2: trasla e trasforma (trasla e ruota l'immagine)
Prima, crea un `BufferedImage` dal file sorgente, poi costruisci un `AffineTransform` che trasla l'immagine alle coordinate desiderate e la ruota attorno al suo centro. `AffineTransform.rotate` si aspetta un angolo in radianti, quindi converti i gradi con `Math.toRadians(degrees)`.

**AffineTransform** è una classe Java che rappresenta una trasformazione affine 2‑D come traslazione, rotazione, scalatura o shear.  
**BufferedImage** è una classe Java che memorizza un'immagine in memoria come raster di pixel.

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

### Passo 3: aggiungi immagine al documento
Dopo aver configurato la trasformazione, disegna l'immagine sulla pagina corrente. La libreria converte automaticamente il `BufferedImage` in un flusso immagine PostScript appropriato.

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

### Passo 4: scrivi ripristino grafico
Chiamare il ripristino (`grestore`) riporta lo stato grafico a quello precedente al salvataggio, assicurando che i comandi di disegno successivi non siano influenzati dalla trasformazione precedente.

```java
document.drawImage(image, transform, null);
```

### Passo 5: chiudi la pagina corrente e salva
Termina la pagina, chiudi il documento e scrivi il file di output su disco.

```java
document.writeGraphicsRestore();
```

Puoi ripetere la sequenza sopra per incorporare immagini aggiuntive, modificando le coordinate di traslazione e l'angolo di rotazione ogni volta.

## Problemi comuni e soluzioni
- **FileNotFoundException:** Verifica che `dataDir` termini con un separatore di file (`/` o `\\`) e che il nome del file immagine corrisponda esattamente.  
- **ImageIO.read restituisce null:** Assicurati che il formato dell'immagine sia tra quelli supportati (JPEG, PNG, BMP, GIF, TIFF).  
- **Angolo di rotazione errato:** `AffineTransform.rotate` lavora con radianti; usa `Math.toRadians(degrees)` per convertire da gradi.  
- **Picchi di memoria su pagine grandi:** Usa `Document.save` con `saveOptions.setCompress(true)` per ridurre l'impronta di memoria.

## Domande frequenti

**D: Posso usare Aspose.Page per Java con altri linguaggi di programmazione?**  
R: La libreria principale è solo per Java, ma Aspose fornisce API equivalenti per .NET, C++ e Python, ciascuna adattata alla propria piattaforma.

**D: È disponibile una versione di prova gratuita per Aspose.Page per Java?**  
R: Sì, puoi accedere alla prova gratuita nella **[pagina di prova gratuita di Aspose.Page](https://releases.aspose.com/)**.

**D: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
R: Puoi richiedere una licenza temporanea nella **[pagina di richiesta licenza temporanea](https://purchase.aspose.com/temporary-license/)**.

**D: Dove posso trovare supporto della community e discussioni relative a Aspose.Page per Java?**  
R: Visita il **[Forum Aspose.Page](https://forum.aspose.com/c/page/39)** per assistenza della community.

**D: Ci sono risorse aggiuntive per l'acquisto di Aspose.Page per Java?**  
R: Puoi acquistare la libreria nella **[pagina di acquisto di Aspose.Page](https://purchase.aspose.com/buy)**.

## Conclusione
Ora disponi di un esempio completo, end‑to‑end, di **aspose.page image manipulation java** che crea un file PostScript, trasla e ruota un'immagine e salva il risultato. Esplora la **[documentazione](https://reference.aspose.com/page/java/)** completa per scoprire funzionalità avanzate come grafica vettoriale, dimensioni di pagina personalizzate e rendering del testo.

---

**Ultimo aggiornamento:** 2026-08-23  
**Testato con:** Aspose.Page per Java 23.11  
**Autore:** Aspose  








```java
document.closePage();
document.save();
```

## Tutorial correlati

- [Come convertire PostScript in PDF usando Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Come aggiungere un gradiente: Gradiente diagonale in Java PostScript usando Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Come aggiungere un motivo a trama in Java PostScript con Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}