---
date: 2026-09-09
description: Scopri come creare un gradiente in Java PostScript e aggiungere un gradiente
  a una forma usando Aspose.Page. Segui questa guida passo‑passo con codice e consigli.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Gradiente radiale Java PostScript con Aspose.Page
og_description: Scopri come creare un gradiente in Java PostScript e aggiungere un
  gradiente a una forma usando Aspose.Page. Segui questa guida passo‑passo con codice
  e consigli.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Come creare un gradiente in Java PostScript con riempimento radiale
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Come creare un gradiente in Java PostScript con riempimento radiale
url: /it/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un gradiente in Java PostScript con riempimento radiale

## Introduzione
Nella presente tutorial imparerai **come creare un gradiente** grafica in un documento PostScript usando Java e Aspose.Page. Ti guideremo passo passo—dalla configurazione del progetto al rendering di un cerchio riempito con un gradiente radiale uniforme—così potrai **aggiungere un gradiente a una forma** oggetti istantaneamente e migliorare la qualità visiva delle tue applicazioni Java.

## Risposte rapide
- **Cosa crea questo tutorial?** Un file PostScript (`.ps`) contenente un cerchio riempito con un gradiente radiale.  
- **Quale libreria è necessaria?** Aspose.Page per Java (ultima versione).  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio funzionante.  
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea o completa per l'uso in produzione; una versione di prova gratuita funziona per lo sviluppo.  
- **Posso riutilizzare il codice per PDF o SVG?** Sì—Aspose.Page supporta più formati di output con modifiche minime.  

## Come riempire una forma con un gradiente in PostScript
Puoi riempire una forma con un gradiente radiale in PostScript creando un `PsDocument`, definendo un `RadialGradientPaint`, applicandolo alla forma di destinazione e infine salvando il documento. Questo flusso di lavoro conciso ti consente di produrre grafica vettoriale dall'aspetto professionale senza immagini raster, e lo stesso codice può essere riutilizzato per output PDF o SVG. Il processo è semplice e funziona in modo coerente su tutti i formati supportati.

## Che cos'è un gradiente radiale?
Un gradiente radiale trasforma i colori verso l'esterno da un punto centrale, creando una fusione liscia e circolare. È ideale per evidenziazioni, sfondi di pulsanti o qualsiasi elemento visivo che richieda un effetto di “bagliore” naturale. Variando le fermate di colore e il raggio, è possibile simulare illuminazione, profondità e proprietà dei materiali in forma vettoriale pura.

## Perché usare Aspose.Page per i gradienti radiali?
Aspose.Page ti consente di generare grafica vettoriale indipendente dal dispositivo con una singola API Java. Supporta oltre 50 formati di input e output—including PostScript, PDF e SVG—preservando l'accuratezza dei colori e l'anti‑aliasing per output ad alta risoluzione. La libreria fornisce anche classi di gradiente facili da usare, rendendo semplici da implementare effetti visivi complessi.

## Prerequisiti
- Familiarità di base con la programmazione Java.  
- JDK 8 o versioni successive installato sulla tua macchina.  
- Libreria Aspose.Page per Java (scarica dalla [documentazione Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Importa pacchetti
Per prima cosa, importa le classi necessarie. Queste includono i tipi grafici standard AWT e l'API Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Passo 1: impostare la directory del documento
Definisci la cartella in cui verrà salvato il file PostScript generato. Sostituisci il segnaposto con un percorso reale sul tuo sistema.

```java
String dataDir = "Your Document Directory";
```

## Passo 2: creare lo stream di output
`FileOutputStream` scrive byte grezzi su un file, consentendo il salvataggio di dati binari. Aprirne uno puntato a un file `.ps` permette ad Aspose.Page di trasmettere i dati PostScript generati direttamente su disco.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Passo 3: creare le opzioni di salvataggio
`PsSaveOptions` configura come viene salvato un file PostScript, includendo dimensione della pagina e compressione. Puoi personalizzare queste impostazioni, ma i valori predefiniti vanno bene per questo esempio.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Passo 4: creare il documento ps
`PsDocument` rappresenta un documento PostScript in memoria e fornisce metodi per aggiungere pagine e grafica.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 5: creare un cerchio
`Ellipse2D.Float` descrive una forma ellittica; quando larghezza = altezza diventa un cerchio perfetto. Questo oggetto servirà da tela per il nostro riempimento a gradiente.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Come disegnare un cerchio con gradiente
Per disegnare un cerchio con un gradiente radiale, carichi un `RadialGradientPaint` nel contesto grafico e poi riempi l'ellisse precedentemente definita. Questa singola operazione dipinge la forma con una transizione di colore fluida dal centro verso l'esterno, creando un effetto visivamente gradevole.

## Passo 6: definire i colori del gradiente
Prepara due array: uno per i colori che appariranno nel gradiente e un altro per le posizioni frazionarie corrispondenti (0 = centro, 1 = bordo).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Passo 7: creare AffineTransform
`AffineTransform` è una matrice che può traslare, ruotare, scalare o deformare oggetti grafici. Qui scala e trasla il gradiente in modo che si adatti perfettamente all'interno del cerchio.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Passo 8: creare RadialGradientPaint
`RadialGradientPaint` crea un gradiente di colore radiale basato su un punto centrale, un raggio e le fermate di colore.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Passo 9: impostare il paint e riempire il cerchio
Applica il paint del gradiente al documento e riempi il cerchio precedentemente definito. Questo è il cuore del nostro **esempio di gradiente radiale** e dimostra come **riempire una forma con un gradiente**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Passo 10: chiudere la pagina e salvare il documento
Finalizza la pagina, scrivi il contenuto su disco e chiudi lo stream. Il tuo file PostScript è ora pronto per essere visualizzato con qualsiasi visualizzatore PS.

```java
document.closePage();
document.save();
```

Congratulazioni! Hai creato con successo un esempio di gradiente radiale in Java PostScript usando Aspose.Page. Ora disponi di un modello riutilizzabile per **riempire una forma con un gradiente** che può essere adattato ad altre forme e formati di output.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **FileNotFoundException** when opening the output stream | Verifica che `dataDir` punti a una cartella esistente e che tu abbia i permessi di scrittura. |
| Gradient looks flat or missing | Assicurati che l'array `fractions` corrisponda alla lunghezza dell'array `colors` e che `AffineTransform` sia scalato correttamente. |
| Colors appear inverted | Scambia l'ordine dei colori nell'array `colors` o regola le coordinate del punto `focus`. |

## Domande frequenti

**Q: Dove posso trovare la documentazione per Aspose.Page per Java?**  
A: Il riferimento completo dell'API è disponibile nella [documentazione Aspose.Page Java API](https://reference.aspose.com/page/java/).

**Q: Come posso scaricare Aspose.Page per Java?**  
A: Scarica l'ultimo JAR dalla [pagina dei rilasci](https://releases.aspose.com/page/java/).

**Q: È disponibile una versione di prova gratuita?**  
A: Sì—scarica una versione di prova dalla [pagina di download della prova gratuita di Aspose](https://releases.aspose.com/).

**Q: Posso ottenere una licenza temporanea per i test?**  
A: Certamente, richiedila dalla [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

**Q: Dove posso trovare supporto dalla community?**  
A: Partecipa alla discussione sul [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Conclusione
In questa guida abbiamo costruito un **esempio completo di gradiente radiale** per un documento PostScript usando Aspose.Page per Java. Seguendo i passaggi ora disponi di un modello riutilizzabile per **riempire una forma con un gradiente**, che puoi adattare a PDF, SVG o a qualsiasi altro formato supportato da Aspose.Page. Sperimenta con colori, raggi e forme diversi per arricchire i tuoi progetti grafici Java.

---

**Ultimo aggiornamento:** 2026-09-09  
**Testato con:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Autore:** Aspose

## Tutorial correlati

- [Crea gradiente PostScript in Java – Aggiungi gradiente verticale](/page/java/postscript-gradient-addition/vertical/)
- [Crea pattern di texture in PostScript con Aspose.Page per Java](/page/java/postscript-texture-patterns/)
- [Tutorial sulla trasparenza di Aspose.Page – Aggiungi trasparenza in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}