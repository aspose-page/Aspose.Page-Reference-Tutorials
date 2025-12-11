---
date: 2025-12-11
description: Scopri come creare un'ellisse PostScript in Java usando Aspose.Page.
  Questa guida passo passo ti mostra come riempire l'ellisse con colore e disegnarla
  usando Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Come creare un'ellisse PostScript in Java con Aspose.Page
url: /it/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'ellisse PostScript in Java con Aspose.Page

## Introduzione
Creare programmaticamente un **ellisse PostScript** ti consente di avere un controllo dettagliato sulla grafica vettoriale in report, fatture o qualsiasi documento stampabile. In questo tutorial imparerai a **creare forme ellisse PostScript** usando la libreria Aspose.Page per Java, a riempire un'ellisse con colore e a disegnare il contorno di un'ellisse. Alla fine sarai pronto a incorporare grafiche personalizzate direttamente nel tuo output PostScript.

## Risposte rapide
- **Quale libreria è la migliore per disegnare grafiche PostScript in Java?** Aspose.Page per Java.  
- **Posso riempire un'ellisse con un colore solido?** Sì – usa `document.setPaint(Color.YOUR_COLOR)` prima di `fill`.  
- **Come disegno solo il contorno di un'ellisse?** Imposta il paint e lo stroke, poi chiama `document.draw(...)`.  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza commerciale; è disponibile una licenza temporanea per i test.  
- **Quale versione di Java è supportata?** Qualsiasi runtime Java 8+ funziona con l'attuale rilascio di Aspose.Page.

## Che cos'è un'ellisse PostScript?
Un'ellisse PostScript è una forma vettoriale definita da un rettangolo di delimitazione. A differenza delle immagini raster, si scala senza perdita di qualità, rendendola ideale per la stampa ad alta risoluzione e la conversione in PDF.

## Perché usare Aspose.Page per creare un'ellisse PostScript?
- **Controllo totale** sui primitivi di disegno (linee, curve, ellissi).  
- **Cross‑platform** – funziona su Windows, Linux e macOS.  
- **Nessuna dipendenza esterna** – API Java pura, senza codice nativo.  
- **Facile integrazione** con le applicazioni Java esistenti e gli strumenti di build.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. Un ambiente di sviluppo Java funzionante (JDK 8 o successivo).  
2. La libreria Aspose.Page per Java aggiunta al tuo progetto. Puoi scaricarla **[qui](https://releases.aspose.com/page/java/)**.  

## Importare i pacchetti
Nel tuo file sorgente Java, importa le classi necessarie per disegnare e salvare contenuti PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guida passo‑passo

### Passo 1: Configurare il documento PostScript
Crea uno stream di output, configura le dimensioni della pagina e istanzia un `PsDocument`.

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

### Passo 2: Riempire l'ellisse con colore
Imposta il paint al colore di riempimento desiderato e chiama `fill` con un'istanza di `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Passo 3: Contornare l'ellisse con lo stroke
Cambia il paint al colore dello stroke, definisci un `BasicStroke` per lo spessore della linea e disegna il contorno dell'ellisse.

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

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ora hai un file PostScript che contiene due ellissi—una riempita di arancione e l'altra contornata in rosso. Sentiti libero di sperimentare con coordinate, dimensioni e colori diversi per soddisfare le esigenze del tuo design.

## Problemi comuni e risoluzione
- **Percorso file errato** – Assicurati che `dataDir` termini con un separatore (`/` o `\\`) appropriato per il tuo OS.  
- **Licenza mancante** – Senza una licenza valida, la libreria funziona in modalità di valutazione e può aggiungere filigrane.  
- **Colore non applicato** – Ricorda di impostare `document.setPaint(...)` *prima* di ogni chiamata a `fill` o `draw`; l'impostazione del paint non persiste automaticamente tra operazioni separate.

## Domande frequenti

**D: Posso usare Aspose.Page per Java con altre librerie Java?**  
R: Sì, Aspose.Page per Java è progettato per integrarsi senza problemi con altre librerie Java.

**D: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
R: Ottieni una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)** per scopi di test.

**D: Aspose.Page è adatto a progetti commerciali?**  
R: Assolutamente! Visita **[qui](https://purchase.aspose.com/buy)** per esplorare le opzioni di licenza per uso commerciale.

**D: Dove posso chiedere aiuto o discutere di quesiti relativi ad Aspose.Page?**  
R: Unisciti alla community sul **[Forum Aspose.Page](https://forum.aspose.com/c/page/39)** per discussioni e assistenza.

**D: Esistono risorse gratuite per approfondire Aspose.Page per Java?**  
R: Utilizza la **[prova gratuita](https://releases.aspose.com/)** e esplora gli esempi nella documentazione.

## Conclusione
Aspose.Page per Java rende semplice **creare grafiche ellisse PostScript**, sia che tu abbia bisogno di una forma semplice riempita o di un contorno complesso. Con i passaggi sopra puoi aggiungere rapidamente grafiche vettoriali di livello professionale a qualsiasi documento stampabile. Per approfondimenti—come combinare più forme, applicare gradienti o convertire in PDF—consulta la documentazione ufficiale **[qui](https://reference.aspose.com/page/java/)**.

---

**Ultimo aggiornamento:** 2025-12-11  
**Testato con:** Aspose.Page per Java 24.11  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
