---
date: 2026-09-14
description: Scopri come creare un gradiente postscript java con Aspose.Page. Questa
  guida passo‑passo ti mostra come aggiungere un gradiente verticale a un file PostScript
  in poche righe di codice Java.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Aggiungi gradiente verticale in Java PostScript
og_description: Scopri come creare un gradiente postscript java con Aspose.Page. Questa
  guida passo‑passo ti mostra come aggiungere un gradiente verticale a un file PostScript
  in poche righe di codice Java.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Crea gradiente postscript java – gradiente verticale
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Crea gradiente postscript java – gradiente verticale
url: /it/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea gradiente postscript java – gradiente verticale

## Introduzione
Aspose.Page for Java è una libreria che consente la creazione e la manipolazione di file PostScript e PDF in modo programmatico. In questo tutorial completo imparerai a **create postscript gradient java** usando tale libreria. Aggiungere un gradiente verticale può rendere i tuoi documenti più vivaci e professionali, e con poche righe di codice puoi ottenere effetti visivi sorprendenti. Ti guideremo passo passo, spiegheremo perché ogni elemento è importante e ti forniremo consigli pratici per evitare errori comuni. Alla fine di questa guida sarai in grado di generare file PostScript con transizioni di colore verticali fluide e accattivanti.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java  
- **Posso personalizzare i colori?** Sì, qualsiasi `java.awt.Color` può essere usato  
- **La rotazione è supportata?** Sì, puoi ruotare il gradiente con un `AffineTransform`  
- **Quale formato di output viene prodotto?** A standard PostScript (.ps) file  
- **È necessaria una licenza per la produzione?** Sì, è necessaria una licenza commerciale  

## Perché aggiungere un gradiente verticale a un documento PostScript?
Aggiungere un gradiente verticale conferisce profondità alle tue pagine, migliora la gerarchia visiva e mantiene le dimensioni del file ridotte perché il gradiente è definito in forma vettoriale anziché come immagini raster. Questa tecnica è perfetta per intestazioni di report, manuali tecnici o qualsiasi volantino che necessiti di un aspetto moderno senza sacrificare la scalabilità.

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Java Development Kit (JDK) installato sulla tua macchina.  
- Libreria Aspose.Page for Java. Puoi scaricarla dalla [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).

## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per iniziare:
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

Ora, vediamo passo passo il processo di aggiunta di un gradiente verticale.

## Come creare postscript gradient java
Carica il tuo ambiente Java, crea un'istanza di `PsSaveOptions` e chiama `Document.save` – questa è la sequenza principale che crea un file PostScript con un gradiente verticale. L'API gestisce l'interpolazione dei colori, le trasformazioni delle coordinate e lo svuotamento della pagina per te, così devi concentrarti solo sulla definizione del rettangolo e dei parametri del gradiente.

### Passo 1: configura la directory del documento
Gli oggetti `File` rappresentano la cartella in cui verrà scritto l'output. La directory deve esistere prima che lo stream venga aperto, altrimenti viene sollevata un'`IOException`.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Passo 2: crea lo stream di output per il documento PostScript
`FileOutputStream` scrive i dati binari PostScript su disco. L'uso di un blocco `try‑with‑resources` garantisce che lo stream venga chiuso anche se si verifica un'eccezione.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Passo 3: crea le opzioni di salvataggio con dimensione A4
`PsSaveOptions` ti permette di specificare la dimensione della pagina, DPI e se incorporare i font. Impostare la dimensione a A4 (595 × 842 punti) corrisponde alla maggior parte dei documenti stampabili.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Passo 4: crea un nuovo documento PS
`Document` è l'oggetto di livello superiore che rappresenta un singolo file PostScript in memoria. Tutti i comandi di disegno sono emessi su questo oggetto.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Passo 5: crea un rettangolo
`Rectangle2D.Double` definisce l'area che sarà riempita con il gradiente. Le coordinate del rettangolo sono espresse in punti (1 punto = 1/72 pollice).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Passo 6: imposta i colori e le frazioni per il gradiente
Un array `float[]` definisce la posizione di ciascun stop di colore (da 0.0 a 1.0). Gli oggetti `Color` contengono i valori RGB effettivi. Puoi usare qualsiasi `java.awt.Color` desideri.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Passo 7: crea la trasformazione del gradiente
`AffineTransform` scala e ruota il gradiente. Per un gradiente verticale puro è sufficiente scalare l'asse Y; la rotazione può essere aggiunta in seguito se desiderato.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Passo 8: crea il paint del gradiente lineare verticale
`LinearGradientPaint` collega il rettangolo, i color stop e la trasformazione. Questo oggetto viene poi passato al contesto grafico.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Passo 9: imposta il paint e riempi il rettangolo
`Graphics2D.setPaint` applica il gradiente, e `fill` lo rende all'interno del rettangolo definito in precedenza.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Passo 10: chiudi la pagina corrente e salva il documento
Chiamare `document.save` scrive l'intero stream PostScript nel file di output e rilascia tutte le risorse native.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Congratulazioni! Hai aggiunto con successo un gradiente verticale al tuo documento PostScript Java usando Aspose.Page for Java.

## Problemi comuni e soluzioni
- **Il gradiente appare piatto:** Assicurati che la scala `AffineTransform` corrisponda alle dimensioni del rettangolo.  
- **I colori sembrano sbiaditi:** Verifica di utilizzare il corretto `ColorSpaceType` (SRGB) e che l'array delle frazioni sia ordinato da 0.0 a 1.0.  
- **Il file non è stato generato:** Controlla che la directory di output (`dataDir`) esista e che l'applicazione abbia i permessi di scrittura.  

## Domande frequenti
**Q: Posso usare Aspose.Page for Java con altre librerie Java?**  
A: Sì, Aspose.Page for Java è progettato per funzionare senza problemi accanto ad altre librerie Java come Apache Commons o Spring.

**Q: È disponibile una versione di prova gratuita per Aspose.Page for Java?**  
A: Sì, puoi ottenere una versione di prova gratuita [pagina di download della prova gratuita](https://releases.aspose.com/).

**Q: Dove posso trovare documentazione aggiuntiva?**  
A: La documentazione dettagliata è disponibile [riferimento API Aspose.Page Java](https://reference.aspose.com/page/java/).

**Q: Come posso acquistare Aspose.Page for Java?**  
A: Puoi acquistare Aspose.Page for Java [pagina di acquisto Aspose.Page](https://purchase.aspose.com/buy).

**Q: Esiste un forum per le discussioni su Aspose.Page?**  
A: Sì, puoi unirti al forum della community [forum della community Aspose.Page](https://forum.aspose.com/c/page/39).

## Altre domande frequenti

**Q: Posso creare altre direzioni di gradiente (orizzontale, diagonale)?**  
A: Assolutamente. Regola i punti di inizio e fine in `LinearGradientPaint` e modifica l'angolo di rotazione nell'`AffineTransform`.

**Q: Funziona anche con output PDF?**  
A: La stessa logica di gradiente può essere applicata quando si salva in PDF usando `PdfSaveOptions` invece di `PsSaveOptions`.

**Q: Come posso cambiare dinamicamente la dimensione del gradiente?**  
A: Calcola le dimensioni del rettangolo a runtime e passa quei valori sia al costruttore `Rectangle2D` sia a quello `AffineTransform`.

---

**Ultimo aggiornamento:** 2026-09-14  
**Testato con:** Aspose.Page for Java 24.11 (latest)  
**Autore:** Aspose

## Tutorial correlati

- [Crea gradiente radiale in PostScript con Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Come convertire PostScript in PDF usando Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Tutorial sulla trasparenza Aspose.Page – Aggiungi trasparenza in Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}