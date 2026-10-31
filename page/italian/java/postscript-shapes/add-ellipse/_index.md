---
date: 2026-10-31
description: Scopri come impostare il paint color e riempire l'ellipse in Java PostScript
  usando Aspose.Page. Questa guida mostra come riempire l'ellipse, disegnare l'ellipse
  outline e impostare lo stroke thickness con chiari code steps.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Aggiungi Ellipse in Java PostScript
og_description: Scopri come riempire l'ellipse e impostare il paint color in Java
  PostScript usando Aspose.Page. Segui il code step‑by‑step per disegnare ellipsi
  riempite e outlined in pochi secondi.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Come riempire un'ellipse e impostare il paint color in Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Come riempire un'ellipse e impostare il paint color in Java PostScript
url: /it/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come riempire un'ellisse e impostare il colore di pittura in Java PostScript

## Introduzione
Se hai bisogno di **impostare il colore di pittura** durante il disegno di grafica vettoriale, la libreria Aspose.Page per Java ti offre il pieno controllo su ogni tratto e riempimento. In questo tutorial scoprirai come **impostare il colore di pittura**, **riempire un'ellisse** e **disegnare il contorno di un'ellisse** usando un approccio semplice, passo‑passo. Alla fine, sarai in grado di aggiungere ellissi PostScript di alta qualità a fatture, report o qualsiasi documento stampabile.

## Risposte rapide
- **Qual è la libreria migliore per disegnare grafica PostScript in Java?** Aspose.Page for Java.  
- **Posso riempire un'ellisse con un colore solido?** Sì – usa `document.setPaint(Color.YOUR_COLOR)` prima di `fill`.  
- **Come disegno solo il contorno di un'ellisse?** Imposta il colore e lo stroke, poi chiama `document.draw(...)`.  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza commerciale; è disponibile una licenza temporanea per i test.  
- **Quale versione di Java è supportata?** Qualsiasi runtime Java 8+ funziona con l'attuale versione di Aspose.Page.

## Cos'è un'ellisse PostScript?
Un'ellisse PostScript è una forma vettoriale definita da un rettangolo di delimitazione. A differenza delle immagini raster, si scala senza perdita di qualità, rendendola ideale per la stampa ad alta risoluzione e la conversione in PDF. Poiché la forma è descritta matematicamente, può essere renderizzata a qualsiasi dimensione o risoluzione mantenendo bordi nitidi e curve fluide.

## Perché usare Aspose.Page per creare un'ellisse PostScript?
Aspose.Page ti offre un controllo deterministico su ogni primitiva di disegno. Supporta **3 principali sistemi operativi (Windows, Linux, macOS)**, **0 dipendenze native**, e può renderizzare **oltre 50 primitive vettoriali** al secondo su un tipico server. La libreria è pura Java, quindi puoi integrarla in qualsiasi applicazione Java 8+ senza librerie native aggiuntive.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. Un ambiente di sviluppo Java funzionante (JDK 8 o successivo).  
2. La libreria Aspose.Page per Java aggiunta al tuo progetto. Puoi scaricarla **[dalla pagina di rilascio di Aspose.Page per Java](https://releases.aspose.com/page/java/)**.  

## Importare i pacchetti
Nel tuo file sorgente Java, importa le classi necessarie per disegnare e salvare contenuti PostScript.

Il pacchetto `java.awt` fornisce i tipi grafici di base come `Color`, `Ellipse2D` e `BasicStroke`. Il pacchetto `com.aspose.page` fornisce la classe `PsDocument` che scrive l'output PostScript.

- **`Color`** – rappresenta un colore sRGB usato per la pittura.  
- **`Ellipse2D`** – descrive una forma ellittica definita da un rettangolo di delimitazione.  
- **`BasicStroke`** – specifica lo spessore della linea, il modello di tratteggio e lo stile di estremità per disegnare i contorni.  
- **`PsDocument`** – rappresenta un documento PostScript e fornisce metodi per disegnare grafica e gestire le pagine.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Come impostare il colore di pittura per un'ellisse
Il primo passo è indicare al documento quale colore usare per la prossima operazione di disegno. Il metodo `setPaint` imposta un colore solido che verrà applicato a un riempimento o a un tratto, a seconda della chiamata successiva.

### Passo 1: Configurare il documento PostScript
Crea uno stream di output, configura le dimensioni della pagina e istanzia un `PsDocument`.

`PsDocument` è la classe principale che rappresenta un file PostScript in memoria. Tutti i comandi di disegno passano attraverso questo oggetto, che gestisce il layout della pagina, la gestione delle risorse e la generazione finale del file.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Passo 2: Riempire l'ellisse – usare set paint color
Per **riempire un'ellisse**, devi prima chiamare `setPaint` con il colore di riempimento desiderato, poi invocare `fill` con un'istanza `Ellipse2D`.

`setPaint` imposta il colore di disegno corrente usato per le operazioni di riempimento o tratto successive.  
`Ellipse2D` definisce i limiti geometrici dell'ellisse; il suo costruttore accetta le coordinate X‑Y dell'angolo superiore sinistro più larghezza e altezza.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Passo 3: Disegnare il contorno dell'ellisse e impostare lo spessore dello stroke
Dopo il riempimento, puoi cambiare il colore, definire un `BasicStroke` per controllare lo spessore della linea e disegnare il contorno dell'ellisse.

`BasicStroke` specifica lo spessore della linea, il modello di tratteggio e lo stile di estremità per disegnare i contorni. Regolando la proprietà `width` controlli quanto spesso appare il bordo dell'ellisse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Passo 4: Chiudere e salvare il documento
Finalizza la pagina e scrivi il file PostScript su disco.

Chiamare `document.close()` svuota tutti i comandi di disegno pendenti e rilascia le risorse. Il file `.ps` risultante può essere aperto con qualsiasi visualizzatore PostScript o convertito in PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ora disponi di un file PostScript che contiene due ellissi — una riempita di arancione e l'altra con contorno rosso. Sentiti libero di sperimentare con coordinate, dimensioni e colori diversi per adattarli alle tue esigenze di design.

## Problemi comuni e risoluzione dei problemi
- **Percorso file errato** – Assicurati che `dataDir` termini con un separatore (`/` o `\\`) appropriato per il tuo OS.  
- **Licenza mancante** – Senza una licenza valida, la libreria funziona in modalità di valutazione e può aggiungere filigrane.  
- **Colore non applicato** – Ricorda di impostare `document.setPaint(...)` *prima* di ogni chiamata `fill` o `draw`; l'impostazione del colore non persiste automaticamente tra operazioni separate.

## Domande frequenti

**Q: Posso usare Aspose.Page per Java con altre librerie Java?**  
A: Sì, Aspose.Page per Java è progettato per integrarsi perfettamente con altre librerie Java.

**Q: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
A: Ottieni una licenza temporanea **[dalla pagina di licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/)** per scopi di test.

**Q: Aspose.Page è adatto per progetti commerciali?**  
A: Assolutamente! Visita **[la pagina di acquisto di Aspose](https://purchase.aspose.com/buy)** per esplorare le opzioni di licenza per uso commerciale.

**Q: Dove posso cercare aiuto o discutere domande relative ad Aspose.Page?**  
A: Unisciti alla community sul **[Forum di Aspose.Page](https://forum.aspose.com/c/page/39)** per discussioni e assistenza.

**Q: Ci sono risorse gratuite per approfondire Aspose.Page per Java?**  
A: Utilizza la **[pagina di prova gratuita di Aspose](https://releases.aspose.com/)** e esplora esempi nella documentazione.

## Conclusione
Aspose.Page per Java rende semplice **impostare il colore di pittura**, **riempire un'ellisse** e **disegnare il contorno di un'ellisse** — sia che tu abbia bisogno di una forma semplice riempita o di una grafica complessa con tratto. Con i passaggi sopra puoi aggiungere rapidamente grafica vettoriale di livello professionale a qualsiasi documento stampabile. Per un'esplorazione più approfondita — come combinare più forme, applicare gradienti o convertire in PDF — consulta la **[documentazione di Aspose.Page Java](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Tutorial correlati

- [Come disegnare un rettangolo in Java PostScript con Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Come aggiungere testo Unicode in Java PostScript con Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Creare un gradiente radiale in PostScript con Aspose.Page per Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}