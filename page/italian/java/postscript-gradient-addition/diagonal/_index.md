---
date: 2026-02-13
description: Migliora i tuoi documenti Java PostScript con gradienti diagonali usando
  Aspose.Page Java. Scopri come aggiungere effetti di gradiente con LinearGradientPaint
  in Java e crea transizioni di colore vivaci senza sforzo.
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: 'Come aggiungere un gradiente: gradiente diagonale in Java PostScript usando
  Aspose.Page Java'
url: /it/java/postscript-gradient-addition/diagonal/
weight: 10
---

)"

**Author:** Aspose -> "**Autore:** Aspose"

Then closing shortcodes.

Now ensure we keep all shortcodes at top and bottom unchanged.

Let's assemble final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere un Gradiente Diagonale in Java PostScript usando Aspose.Page Java

## Introduzione
Se desideri arricchire un file PostScript con una transizione di colore diagonale fluida, **Aspose.Page Java** lo rende sorprendentemente semplice. In questo tutorial vedremo **come aggiungere un gradiente** passo dopo passo, utilizzando la classe `LinearGradientPaint` di Java 2D. Alla fine avrai uno snippet pronto all'uso che crea un documento PostScript con un vivace gradiente diagonale.

## Come Aggiungere un Gradiente in Java PostScript
Aggiungere un gradiente potrebbe sembrare un compito esclusivamente grafico, ma con Aspose.Page ottieni il pieno controllo sui comandi PostScript sottostanti restando in puro Java. Questa sezione spiega perché l'approccio funziona e cosa guadagni rispetto al codificare manualmente PostScript grezzo.

## Risposte Rapide
- **Quale libreria è necessaria?** Aspose.Page for Java.  
- **Quale classe crea il gradiente?** `LinearGradientPaint`.  
- **Posso cambiare i colori?** Sì – modifica l'array `Color[]`.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale; è disponibile una versione di prova gratuita.  
- **Quanto tempo richiede l'implementazione?** Circa 10 minuti per un gradiente di base.

## Cos'è Aspose.Page Java?
Aspose.Page Java è una potente API che consente agli sviluppatori di generare, modificare e convertire file PostScript e PDF senza necessità di software esterni. Espone tutte le capacità grafiche del linguaggio PostScript attraverso un'interfaccia Java pulita e orientata agli oggetti.

## Perché usare un gradiente diagonale?
Un gradiente diagonale aggiunge profondità e interesse visivo a grafici, banner o qualsiasi elemento grafico che richieda un aspetto moderno. Poiché il gradiente si estende da un angolo all'altro, funziona bene per sfondi, skin di pulsanti e forme decorative.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Java Development Kit (JDK) 8 o superiore.  
- Un IDE come Eclipse, IntelliJ IDEA o VS Code.  
- **Libreria Aspose.Page per Java** – scarica l'ultima versione dalla [pagina di download ufficiale](https://releases.aspose.com/page/java/).

## Importare i Pacchetti
Innanzitutto, importa le classi Java 2D e Aspose necessarie. Queste importazioni ti danno accesso alle definizioni di colore, forme geometriche, pittura del gradiente e all'API del documento PostScript.

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

## Passo 1: Creare lo Stream di Output per il Documento PostScript
Iniziamo definendo la cartella in cui il file verrà salvato e aprendo un `FileOutputStream`. Questo stream riceverà i dati PostScript generati.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Passo 2: Creare le Opzioni di Salvataggio con Formato A4
`PsSaveOptions` ti consente di specificare la dimensione della pagina, la risoluzione e altre impostazioni di output. Qui utilizziamo la dimensione A4 predefinita.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Passo 3: Creare un Nuovo Documento PS
Istanzia un `PsDocument` utilizzando lo stream di output e le opzioni di salvataggio. Il flag `false` indica al costruttore di non aprire automaticamente una nuova pagina – lo faremo più tardi.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 4: Creare un Rettangolo
Definisci il rettangolo che riceverà il riempimento a gradiente. La posizione del rettangolo (200, 100) e le dimensioni (200 × 100) sono scelte per rendere il gradiente chiaramente visibile.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Passo 5: Creare la Trasformazione del Gradiente
Un `AffineTransform` ci permette di ruotare, scalare e traslare il gradiente in modo che attraversi diagonalmente il rettangolo. Il calcolo qui sotto determina l'ipotenusa e regola di conseguenza il rapporto di scala.

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

## Passo 6: Creare un Paint Lineare Diagonale a Gradiente
Ecco il nucleo di **come aggiungere un gradiente** – costruiamo un `LinearGradientPaint` che si estende dall'angolo in alto a sinistra del rettangolo a quello in basso a destra, usando la trasformazione definita in precedenza. `MultipleGradientPaint.CycleMethod.NO_CYCLE` garantisce che il gradiente non si ripeta.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Passo 7: Impostare il Paint e Riempire il Rettangolo
Applica il paint a gradiente al documento e riempi la forma del rettangolo. Questo passaggio rende la transizione di colore diagonale sulla pagina PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Passo 8: Chiudere la Pagina Corrente e Salvare il Documento
Infine, chiudi la pagina, svuota lo stream e salva il file. Il file risultante `DiagonalGradient_outPS.ps` può essere aperto con qualsiasi visualizzatore PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Problemi Comuni e Suggerimenti
- **Il gradiente appare piatto** – verifica l'angolo di rotazione; una rotazione di 45° crea una vera diagonale.  
- **I colori sembrano sbiaditi** – assicurati di usare `MultipleGradientPaint.ColorSpaceType.SRGB` per una resa cromatica accurata.  
- **Errore file non trovato** – verifica che `dataDir` punti a una cartella esistente e che l'applicazione abbia i permessi di scrittura.

## Domande Frequenti

**Q: Posso usare questa libreria per altre operazioni grafiche in Java?**  
**A:** Sì, Aspose.Page for Java fornisce un set completo di primitive di disegno, rendering del testo e capacità di gestione delle immagini.

**Q: È disponibile una versione di prova gratuita per Aspose.Page Java?**  
**A:** Assolutamente. Puoi scaricare una versione di prova completamente funzionale dalla [pagina di prova gratuita di Aspose](https://releases.aspose.com/).

**Q: Dove posso trovare la documentazione per Aspose.Page Java?**  
**A:** Il riferimento API ufficiale è disponibile [qui](https://reference.aspose.com/page/java/).

**Q: Come posso acquistare una licenza per Aspose.Page Java?**  
**A:** Le licenze possono essere acquistate direttamente dal [portale di acquisto Aspose](https://purchase.aspose.com/buy).

**Q: Hai bisogno di assistenza o hai domande?**  
**A:** Visita il [forum di Aspose.Page gestito dalla community](https://forum.aspose.com/c/page/39) per ricevere aiuto sia dagli ingegneri Aspose sia da altri sviluppatori.

---

**Ultimo aggiornamento:** 2026-02-13  
**Testato con:** Aspose.Page for Java 24.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}