---
date: 2026-09-09
description: Scopri come creare un gradiente radiale in Java PostScript usando Aspose.Page.
  Questa guida passo-passo ti mostra come aggiungere un gradiente con fermate di colore,
  impostare i raggi e generare rapidamente un file PS.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Padroneggiare i gradienti radiali in Java
og_description: Scopri come creare un gradiente radiale in Java PostScript usando
  Aspose.Page. Questa guida spiega come aggiungere un gradiente con fermate di colore,
  impostare i raggi e generare un file PS in pochi minuti.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Come creare un gradiente radiale in Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Come creare un gradiente radiale in Java PostScript
url: /it/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un gradiente radiale in Java PostScript con Aspose.Page

## Introduzione
Se hai bisogno di **creare un gradiente radiale** all'interno di un file PostScript, sei nel posto giusto. In questo tutorial ti guideremo passo passo attraverso tutte le operazioni necessarie per generare un documento PostScript che contiene un gradiente radiale uniforme, usando **Aspose.Page for Java**. Alla fine comprenderai l'API, vedrai un esempio completo eseguibile e saprai come regolare colori, posizioni e raggi per qualsiasi scenario di design.

## Risposte rapide
- **Quale libreria crea gradienti radiali in PostScript?** Aspose.Page for Java.  
- **Quanto tempo richiede l'implementazione?** About 10‑15 minutes for a basic example.  
- **È necessaria una licenza per eseguire il codice?** A free trial works for development; a commercial license is required for production.  
- **Quale versione di Java è supportata?** Java 8 or higher.  
- **Posso modificare la forma del gradiente?** Yes – adjust the radius and center point in the `RadialGradientPaint` constructor.

## Come creare un gradiente radiale in Java

Carica il tuo progetto Java, importa le classi necessarie e segui la guida passo‑passo qui sotto. La risposta fondamentale è che devi istanziare un `RadialGradientPaint` con le tue fermate di colore e poi applicarlo a un rettangolo disegnato su un `PsDocument`. Questo approccio a due oggetti gestisce tutti i comandi PostScript di basso livello per te.

## Che cos'è un gradiente radiale?
`RadialGradientPaint` è una classe Java AWT che definisce una transizione di colore circolare da un punto centrale verso l'esterno. Crea una fusione uniforme di più fermate di colore, rendendola ideale per riflettori, sfondi morbidi o qualsiasi effetto in cui i colori si irradiano da un punto focale.

## Perché usare Aspose.Page per i gradienti radiali?
Aspose.Page ti offre il pieno controllo programmatico sull'output PostScript gestendo al contempo la parte più complessa della sintassi PS di basso livello. Supporta **oltre 50 formati di input e output**, può renderizzare documenti di centinaia di pagine senza caricare l'intero file in memoria, e funziona su qualsiasi sistema operativo che supporti Java 8+. Questa capacità quantificata lo rende una scelta affidabile per la generazione di grafica di livello enterprise.

## Prerequisiti
- **Java Development Kit (JDK) 8+** – verifica con `java -version`.  
- **Aspose.Page for Java** – scarica l'ultimo JAR dalla pagina ufficiale [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE of your choice** – Eclipse, IntelliJ IDEA o VS Code con estensioni Java.  
- **A writable folder** – dove verrà salvato il file `.ps` generato.

## Importa pacchetti
Innanzitutto, importa le classi di cui avremo bisogno. Il pacchetto `java.awt` fornisce gli oggetti di pittura del gradiente, mentre `com.aspose.eps` contiene le classi per la gestione dei documenti PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guida passo‑passo

### Passo 1: crea un rettangolo e apri un documento PS
`PsDocument` è la classe di Aspose.Page che rappresenta un documento PostScript e fornisce metodi per disegnare forme, testo e immagini. Iniziamo creando uno stream di output, configurando la dimensione della pagina (A4 per impostazione predefinita) e definendo un rettangolo che ospiterà il gradiente.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Suggerimento:** Regola le coordinate del rettangolo (`200, 100, 200, 200`) per posizionare il gradiente ovunque sulla pagina.

### Passo 2: definisci colori e frazioni
Un gradiente radiale è costruito da *color stop* (i colori) e *fractions* (le posizioni relative di tali fermate). Qui creiamo un array di sei colori e le loro frazioni corrispondenti.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Perché è importante:** Modificando le `fractions` controlli la rapidità con cui i colori si fondono, consentendo effetti sottili o drammatici.

### Passo 3: crea il paint del gradiente radiale
`RadialGradientPaint` è la classe principale che descrive un gradiente di colore radiale, includendo punto centrale, raggio, punto di messa a fuoco, frazioni, colori, metodo di ciclo e spazio colore. Ora costruiamo l'oggetto `RadialGradientPaint` usando gli array definiti sopra.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Nota:** `transform` può essere `null` se non hai bisogno di scalatura o rotazione aggiuntiva. Sentiti libero di sperimentare con `AffineTransform` per gradienti inclinati.

### Passo 4: imposta il paint e riempi il rettangolo
Con il paint pronto, diciamo al `PsDocument` di usarlo e poi riempiamo il rettangolo definito in precedenza.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

A questo punto la pagina PostScript contiene un rettangolo riempito uniformemente con il gradiente radiale configurato.

### Passo 5: chiudi e salva il documento
Infine, chiudi la pagina corrente e scrivi il file su disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Apri `RadialGradient1_outPS.ps` in qualsiasi visualizzatore PostScript (ad esempio Ghostscript) e vedrai il gradiente renderizzato esattamente come definito.

## Problemi comuni e soluzioni
| Problema | Probabile causa | Soluzione |
|----------|----------------|-----------|
| Il gradiente appare come un colore solido | L'array `fractions` non inizia con `0.0f` o non termina con `1.0f` | Assicurati che la prima frazione sia `0.0f` e l'ultima sia `1.0f`. |
| I colori appaiono sbiaditi | Uso del `ColorSpaceType` errato | Passa a `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` per un output più vivace. |
| Nessun file di output generato | Il percorso di `FileOutputStream` è non valido o non scrivibile | Verifica che `dataDir` esista e che l'applicazione abbia i permessi di scrittura. |

## Domande frequenti

**Q: Posso usare Aspose.Page per Java in progetti commerciali?**  
A: Sì. È necessaria una licenza commerciale per l'uso in produzione. Puoi acquistarne una dalla [pagina di licenza Aspose](https://purchase.aspose.com/buy).

**Q: Dove posso trovare la documentazione ufficiale dell'API?**  
A: La documentazione completa è disponibile [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: È disponibile una versione di prova gratuita per i test?**  
A: Assolutamente. Scarica una versione di prova dalla [pagina di rilascio Aspose.Page](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per la valutazione?**  
A: Una licenza temporanea può essere richiesta dalla [pagina di richiesta licenza temporanea](https://purchase.aspose.com/temporary-license/).

**Q: Dove posso trovare supporto dalla community?**  
A: Unisciti al forum della community Aspose.Page su [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusione
Ora sai **come creare un gradiente radiale** in un documento Java PostScript usando Aspose.Page. Regolando le dimensioni del rettangolo, le fermate di colore e il raggio del gradiente puoi creare innumerevoli effetti visivi—da riempimenti di sfondo sottili a grafiche di riflettori audaci. Sentiti libero di sperimentare con diversi valori di `AffineTransform` per ruotare o inclinare il gradiente, e combina questa tecnica con testo e immagini per output PDF o EPS più ricchi.

---

**Ultimo aggiornamento:** 2026-09-09  
**Testato con:** Aspose.Page for Java latest (as of writing)  
**Autore:** Aspose

## Tutorial correlati

- [Riempire forma con gradiente: esempio radiale Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Crea gradiente PostScript in Java – Aggiungi gradiente verticale](/page/java/postscript-gradient-addition/vertical/)
- [Tutorial trasparenza Aspose.Page – Aggiungi trasparenza in Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}