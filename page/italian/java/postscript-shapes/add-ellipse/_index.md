---
date: 2026-02-18
description: Scopri come impostare il colore di pittura e creare un'ellisse PostScript
  in Java usando Aspose.Page. Questa guida mostra come riempire un'ellisse in Java,
  disegnare il contorno dell'ellisse e impostare lo spessore del tratto.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Imposta il colore di pittura per disegnare un'ellisse PostScript in Java
url: /it/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il colore di vernice per disegnare un'ellisse PostScript in Java

## Introduzione
Se hai bisogno di **impostare il colore di vernice** mentre disegni grafica vettoriale, la libreria Aspose.Page per Java ti offre il pieno controllo su ogni tratto e riempimento. In questo tutorial scoprirai come **impostare il colore di vernice**, **riempire un'ellisse in Java**, e **disegnare il contorno di un'ellisse** usando un approccio semplice, passo‑passo. Alla fine, sarai in grado di aggiungere ellissi PostScript di alta qualità a fatture, report o qualsiasi documento stampabile.

## Risposte rapide
- **Qual è la libreria migliore per disegnare grafica PostScript in Java?** Aspose.Page for Java.  
- **Posso riempire un'ellisse con un colore solido?** Sì – usa `document.setPaint(Color.YOUR_COLOR)` prima di `fill`.  
- **Come disegno solo il contorno di un'ellisse?** Imposta la vernice e lo stroke, poi chiama `document.draw(...)`.  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza commerciale; è disponibile una licenza temporanea per i test.  
- **Quale versione di Java è supportata?** Qualsiasi runtime Java 8+ funziona con l'attuale rilascio di Aspose.Page.

## Che cos'è un'ellisse PostScript?
Un'ellisse PostScript è una forma vettoriale definita da un rettangolo di delimitazione. A differenza delle immagini raster, si scala senza perdita di qualità, rendendola ideale per la stampa ad alta risoluzione e la conversione in PDF.

## Perché usare Aspose.Page per creare un'ellisse PostScript?
- **Controllo completo** sui primitivi di disegno (linee, curve, ellissi).  
- **Cross‑platform** – funziona su Windows, Linux e macOS.  
- **Nessuna dipendenza esterna** – API Java pura, nessun codice nativo.  
- **Facile integrazione** con le applicazioni Java esistenti e gli strumenti di build.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. Un ambiente di sviluppo Java funzionante (JDK 8 o successivo).  
2. La libreria Aspose.Page per Java aggiunta al tuo progetto. Puoi scaricarla **[qui](https://releases.aspose.com/page/java/)**.  

## Importa i pacchetti
Nel tuo file sorgente Java, importa le classi necessarie per disegnare e salvare contenuti PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Come impostare il colore di vernice per un'ellisse
Impostare il colore di vernice è il primo passo prima di qualsiasi operazione di riempimento o stroke. Il metodo `setPaint` determina il colore che verrà usato per il prossimo comando di disegno.

### Passo 1: Configura il documento PostScript
Crea uno stream di output, configura la dimensione della pagina e istanzia un `PsDocument`.

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

### Passo 2: Come riempire un'ellisse – usa il colore di vernice
Per **riempire un'ellisse**, devi prima chiamare `setPaint` con il colore di riempimento desiderato, poi invocare `fill` con un'istanza `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Passo 3: Disegna il contorno dell'ellisse e imposta lo spessore dello stroke
Dopo il riempimento, puoi cambiare la vernice con un colore diverso, definire un `BasicStroke` per controllare lo spessore della linea, e disegnare il contorno dell'ellisse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Passo 4: Chiudi e salva il documento
Finalizza la pagina e scrivi il file PostScript su disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ora hai un file PostScript che contiene due ellissi—una riempita di arancione e un'altra con il contorno rosso. Sentiti libero di sperimentare con coordinate, dimensioni e colori diversi per soddisfare le tue esigenze di design.

## Problemi comuni e risoluzione dei problemi
- **Percorso file errato** – Assicurati che `dataDir` termini con un separatore (`/` o `\\`) appropriato per il tuo OS.  
- **Licenza mancante** – Senza una licenza valida, la libreria funziona in modalità di valutazione e può aggiungere filigrane.  
- **Colore non applicato** – Ricorda di impostare `document.setPaint(...)` *prima* di ogni chiamata `fill` o `draw`; l'impostazione della vernice non persiste automaticamente tra operazioni separate.

## Domande frequenti

**Q: Posso usare Aspose.Page per Java con altre librerie Java?**  
A: Sì, Aspose.Page per Java è progettato per integrarsi senza problemi con altre librerie Java.

**Q: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
A: Ottieni una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)** per scopi di test.

**Q: Aspose.Page è adatto per progetti commerciali?**  
A: Assolutamente! Visita **[qui](https://purchase.aspose.com/buy)** per esplorare le opzioni di licenza per uso commerciale.

**Q: Dove posso cercare aiuto o discutere domande relative ad Aspose.Page?**  
A: Unisciti alla community sul **[Forum Aspose.Page](https://forum.aspose.com/c/page/39)** per discussioni e assistenza.

**Q: Esistono risorse gratuite per approfondire Aspose.Page per Java?**  
A: Utilizza la **[prova gratuita](https://releases.aspose.com/)** ed esplora esempi nella documentazione.

## Conclusione
Aspose.Page per Java rende semplice **impostare il colore di vernice**, **riempire un'ellisse**, e **disegnare il contorno di un'ellisse** — sia che tu abbia bisogno di una forma semplice riempita o di una grafica complessa con stroke. Con i passaggi sopra puoi aggiungere rapidamente grafica vettoriale di livello professionale a qualsiasi documento stampabile. Per approfondimenti—come combinare più forme, applicare gradienti o convertire in PDF—consulta la **[documentazione](https://reference.aspose.com/page/java/)** ufficiale.

---

**Ultimo aggiornamento:** 2026-02-18  
**Testato con:** Aspose.Page for Java 24.11  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}