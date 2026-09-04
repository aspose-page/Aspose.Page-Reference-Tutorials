---
date: 2026-09-04
description: Scopri come creare un gradiente orizzontale java in un file PostScript
  usando Linear Gradient Paint Java con Aspose.Page per Java. Codice passo‑passo,
  problemi comuni e FAQ.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Crea un gradiente orizzontale java in PostScript con Aspose
og_description: Crea un gradiente orizzontale java in PostScript con Linear Gradient
  Paint Java. Questo tutorial di Aspose.Page ti mostra i passaggi esatti, i prerequisiti
  e i consigli per la risoluzione dei problemi in meno di 15 minuti.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Crea un gradiente orizzontale java in PostScript con Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Crea un gradiente orizzontale java in PostScript con Aspose
url: /it/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un gradiente orizzontale in Java PostScript usando Linear Gradient Paint

## Introduzione
Nella presente guida completa imparerai **come creare un gradiente orizzontale in Java** in un documento PostScript utilizzando la classe **Linear Gradient Paint Java** fornita con Aspose.Page per Java. Ti guideremo passo passo—dalla configurazione del progetto al rendering del gradiente su forme e testo—così potrai produrre grafiche rifinite, pronte per la stampa, in pochi minuti. Che tu stia costruendo un motore di reporting, uno strumento di automazione del design o un driver di stampa personalizzato, questa guida ti fornisce il codice esatto di cui hai bisogno.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java (includes Linear Gradient Paint Java).  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un gradiente orizzontale di base.  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per l'uso in produzione.  
- **Quale versione di JDK funziona?** Java 8 o successiva.  
- **Posso usare il gradiente sia su forme che su testo?** Sì – la stessa istanza `LinearGradientPaint` può riempire le forme e essere applicata a tratti o riempimenti di testo.

## Cos'è un gradiente orizzontale e perché usarlo?
Un gradiente orizzontale mescola i colori dal bordo sinistro di un oggetto a quello destro, creando una transizione fluida che aggiunge profondità e interesse visivo. È ideale per componenti UI moderni, intestazioni evidenziate o sfumature di sfondo sottili in report PDF o PostScript. L'uso di **Linear Gradient Paint Java** consente di controllare con precisione i colori di inizio e fine, l'opacità e la scala, garantendo che il risultato sia nitido su qualsiasi dispositivo o stampante.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere quanto segue:

- Java Development Kit (JDK) installato sulla tua macchina.  
- Libreria Aspose.Page per Java. Puoi scaricarla dalla [documentazione Aspose.Page Java](https://reference.aspose.com/page/java/).

## Importa pacchetti
Inizia importando i pacchetti necessari nel tuo progetto Java. Queste importazioni ti danno accesso alle primitive grafiche, alla gestione dei gradienti e all'API Aspose.Page.

La classe `PsDocument` rappresenta un documento PostScript su cui è possibile disegnare grafica.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Passo 1: crea un rettangolo
Per prima cosa, configura lo stream di output, il documento e un rettangolo che ospiterà il gradiente.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Passo 2: crea un paint di gradiente lineare orizzontale
`LinearGradientPaint` è la classe principale che definisce una transizione di colore lineare.  
La classe `LinearGradientPaint` rappresenta un oggetto paint che rende un gradiente lungo una linea retta; si specificano i punti di inizio/fine, le fermate di colore e un opzionale `AffineTransform` per scalarlo alla forma.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Passo 3: riempi il rettangolo
Ora riempi il rettangolo con il gradiente appena definito.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Passo 4: riempi un testo con il gradiente
Puoi anche applicare lo stesso gradiente al testo, creando un effetto visivo sorprendente.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Passo 5: traccia un testo con il gradiente
Infine, delinea il testo usando il gradiente come colore del tratto.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| Il gradiente appare allungato | Scalatura `AffineTransform` errata | Assicurati che la larghezza e l'altezza della trasformazione corrispondano alle dimensioni del rettangolo (200 × 100 nell'esempio). |
| I colori appaiono sbiaditi | Valori alfa impostati troppo bassi | Aumenta il componente alfa (il quarto valore in `new Color(r,g,b,alpha)`). |
| Il testo non è visibile | Paint non impostato prima di disegnare il testo | Chiama `document.setPaint(paint)` **prima** di qualsiasi chiamata a `fillAndStrokeText` o `outlineText`. |

## Domande frequenti
**Q:** Posso usare Aspose.Page per Java in progetti commerciali?  
**A:** Sì, Aspose.Page per Java può essere usato in progetti commerciali. Per i dettagli sulla licenza, visita la pagina [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** È disponibile una versione di prova gratuita?  
**A:** Sì, puoi accedere a una versione di prova gratuita di Aspose.Page per Java nella pagina [Aspose.Page for Java free trial](https://releases.aspose.com/).

**Q:** Dove posso trovare documentazione aggiuntiva e supporto?  
**A:** Visita la [documentazione Aspose.Page Java](https://reference.aspose.com/page/java/) per risorse complete. Per aiuto della community, controlla il [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**Q:** Come posso ottenere una licenza temporanea?  
**A:** Puoi ottenere una licenza temporanea dalla [pagina di licenza temporanea Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**Q:** Quali sono i requisiti di sistema per Aspose.Page per Java?  
**A:** Consulta la [documentazione Aspose.Page Java](https://reference.aspose.com/page/java/) per i requisiti di sistema dettagliati.

---

**Ultimo aggiornamento:** 2026-09-04  
**Testato con:** Aspose.Page for Java 24.11  
**Autore:** Aspose

## Tutorial correlati

- [Crea gradiente PostScript in Java – Aggiungi gradiente verticale](/page/java/postscript-gradient-addition/vertical/)
- [Come aggiungere gradiente: Gradiente diagonale in Java PostScript usando Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Crea gradiente PostScript – Gradiente radiale in Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}