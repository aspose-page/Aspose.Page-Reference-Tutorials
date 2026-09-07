---
date: 2026-09-04
description: Scopri come aggiungere una sfumatura in Java PostScript con Aspose.Page
  Java, creando transizioni di colore diagonali usando LinearGradientPaint per documenti
  vivaci.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Come aggiungere una sfumatura: sfumatura diagonale in Java PostScript
  usando Aspose.Page Java'
og_description: Scopri come aggiungere una sfumatura in Java PostScript usando Aspose.Page
  Java. Questa guida ti mostra come creare una sfumatura diagonale con LinearGradientPaint
  in pochi passaggi.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Come aggiungere una sfumatura in Java PostScript con Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Come aggiungere una sfumatura: sfumatura diagonale in Java PostScript usando
  Aspose.Page Java'
url: /it/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere un gradiente diagonale in Java PostScript usando Aspose.Page Java

## Introduzione
Se desideri arricchire un file PostScript con una transizione di colore diagonale fluida, **Aspose.Page Java** lo rende sorprendentemente semplice. In questo tutorial imparerai **come aggiungere un gradiente** passo dopo passo, utilizzando la classe `LinearGradientPaint` di Java 2D. Alla fine avrai uno snippet pronto all'uso che crea un documento PostScript con un vivace gradiente diagonale, e comprenderai perché questo approccio è più manutenibile rispetto al codice manuale di comandi PostScript grezzi.

## Come aggiungere un gradiente in Java PostScript
Aggiungere un gradiente potrebbe sembrare un compito esclusivamente grafico, ma con Aspose.Page ottieni il pieno controllo sui comandi PostScript sottostanti rimanendo in puro Java. Questa sezione spiega perché l'approccio funziona e cosa guadagni rispetto al codice manuale di PostScript grezzo.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java.  
- **Quale classe crea il gradiente?** `LinearGradientPaint`.  
- **Posso cambiare i colori?** Sì – modifica l'array `Color[]`.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale; è disponibile una versione di prova gratuita.  
- **Quanto tempo richiede l'implementazione?** Circa 10 minuti per un gradiente di base.

## Cos'è Aspose.Page Java?
Aspose.Page Java è un'API completa che consente agli sviluppatori di generare, modificare e convertire file PostScript e PDF senza alcun software esterno. La libreria supporta **oltre 50 formati di input e output** e può elaborare documenti con **oltre 500 pagine** mantenendo l'uso della memoria sotto i 100 MB.

## Perché usare un gradiente diagonale?
Un gradiente diagonale aggiunge profondità e interesse visivo a grafici, banner o qualsiasi elemento grafico che richieda un aspetto moderno. Poiché il gradiente si estende da un angolo all'altro, funziona bene per sfondi, skin di pulsanti e forme decorative, offrendo una finitura professionale senza risorse immagine aggiuntive.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Java Development Kit (JDK) 8 o superiore.  
- Un IDE come Eclipse, IntelliJ IDEA o VS Code.  
- **Aspose.Page for Java** library – scarica l'ultima versione dalla [pagina di download ufficiale](https://releases.aspose.com/page/java/).

## Importare i pacchetti
Il pacchetto `java.awt` fornisce le classi grafiche di base, mentre il pacchetto `com.aspose.page` ti dà accesso alle API specifiche per PostScript.

La classe `LinearGradientPaint` è il ponte di Aspose.Page verso la funzionalità di gradiente di Java 2D.  
`AffineTransform` consente rotazione e scalatura del gradiente in modo che si allinei diagonalmente.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Passo 1: creare lo stream di output per il documento PostScript
Innanzitutto, definisci la cartella in cui il file verrà salvato e apri un `FileOutputStream`. Questo stream riceve i dati PostScript generati.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Passo 2: creare le opzioni di salvataggio con formato A4
`PsSaveOptions` ti permette di specificare la dimensione della pagina, la risoluzione e altre impostazioni di output. Qui utilizziamo la dimensione A4 predefinita, che è 595 × 842 punti a 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Passo 3: creare un nuovo documento PS
La classe `PsDocument` rappresenta un documento PostScript e fornisce metodi per creare pagine e disegnare grafica.  
Istanzia un `PsDocument` usando lo stream di output e le opzioni di salvataggio. Il flag `false` indica al costruttore di non aprire automaticamente una nuova pagina – lo faremo più tardi.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 4: creare un rettangolo
Definisci il rettangolo che riceverà il riempimento a gradiente. La posizione del rettangolo (200, 100) e le dimensioni (200 × 100) sono scelte per rendere il gradiente chiaramente visibile.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Passo 5: creare la trasformazione del gradiente
Un `AffineTransform` ci permette di ruotare, scalare e traslare il gradiente in modo che si estenda diagonalmente attraverso il rettangolo. La matematica qui sotto calcola l'ipotenusa e regola il rapporto di scala di conseguenza.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Passo 6: creare il paint del gradiente lineare diagonale
`LinearGradientPaint` è la classe principale che genera la transizione di colore. Si estende dall'angolo in alto a sinistra del rettangolo a quello in basso a destra, usando la trasformazione definita in precedenza. `MultipleGradientPaint.CycleMethod.NO_CYCLE` garantisce che il gradiente non si ripeta.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Passo 7: impostare il paint e riempire il rettangolo
Applica il paint a gradiente al documento e riempi la forma del rettangolo. Questo passaggio rende la transizione di colore diagonale sulla pagina PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Passo 8: chiudere la pagina corrente e salvare il documento
Infine, chiudi la pagina, svuota lo stream e salva il file. Il file risultante `DiagonalGradient_outPS.ps` può essere aperto con qualsiasi visualizzatore PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Problemi comuni e consigli
- **Il gradiente appare piatto** – verifica l'angolo di rotazione; una rotazione di 45° crea una vera diagonale.  
- **I colori sembrano sbiaditi** – assicurati di usare `MultipleGradientPaint.ColorSpaceType.SRGB` per una resa cromatica accurata.  
- **Errore file non trovato** – verifica che `dataDir` punti a una cartella esistente e che l'applicazione abbia i permessi di scrittura.  
- **Documenti di grandi dimensioni causano picchi di memoria** – usa `PsSaveOptions.setCompress(true)` per ridurre l'impronta di memoria.

## Domande frequenti

**D: Posso usare questa libreria per altre operazioni grafiche in Java?**  
R: Sì, Aspose.Page for Java fornisce un set completo di primitive di disegno, rendering del testo e capacità di gestione delle immagini.

**D: È disponibile una versione di prova gratuita per Aspose.Page Java?**  
R: Assolutamente. Puoi scaricare una versione di prova completamente funzionale dalla [pagina di prova gratuita di Aspose](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione per Aspose.Page Java?**  
R: Il riferimento API ufficiale è disponibile [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**D: Come posso acquistare una licenza per Aspose.Page Java?**  
R: Le licenze possono essere acquistate direttamente dal [portale di acquisto Aspose](https://purchase.aspose.com/buy).

**D: Hai bisogno di assistenza o hai domande?**  
R: Visita il [forum di Aspose.Page](https://forum.aspose.com/c/page/39) gestito dalla community per ottenere aiuto sia dagli ingegneri Aspose sia da altri sviluppatori.

---

**Ultimo aggiornamento:** 2026-09-04  
**Testato con:** Aspose.Page for Java 24.12 (latest)  
**Autore:** Aspose

## Tutorial correlati

- [Crea un gradiente radiale in PostScript con Aspose.Page per Java](/page/java/postscript-gradient-addition/)
- [Come aggiungere un gradiente in Java PostScript con Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Crea un gradiente PostScript in Java – Aggiungi un gradiente verticale](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}