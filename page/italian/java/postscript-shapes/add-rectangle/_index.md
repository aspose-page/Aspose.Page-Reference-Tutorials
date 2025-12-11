---
date: 2025-12-11
description: Scopri come disegnare forme rettangolari in Java PostScript usando Aspose.Page.
  Questa guida passo‑passo mostra come impostare la vernice, impostare il colore del
  rettangolo in Java e creare grafiche vivaci.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Come disegnare un rettangolo in Java PostScript con Aspose.Page
url: /it/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come disegnare un rettangolo in Java PostScript con Aspose.Page

## Introduzione
Se hai bisogno di **come disegnare un rettangolo** all'interno di un file Java PostScript, sei nel posto giusto. In questo tutorial vedremo come utilizzare Aspose.Page per Java per aggiungere rettangoli colorati, controllare il loro riempimento e contorno, e salvare il risultato come documento PostScript. Vedrai esattamente **come impostare la vernice**, come definire la geometria del rettangolo, e perché questo approccio è ideale per generare grafiche stampabili programmaticamente.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java  
- **Posso cambiare i colori del rettangolo?** Sì – usa `setPaint` con qualsiasi `java.awt.Color`  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita funziona per i test; è necessaria una licenza per la produzione  
- **Quale dimensione di pagina è usata nell'esempio?** A4 (predefinito `PsSaveOptions`)  
- **Il codice è compatibile con Java 8+?** Assolutamente – utilizza le classi standard AWT  

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Comprensione di base della programmazione Java.  
- Libreria Aspose.Page per Java installata. In caso contrario, scaricala dalla [documentazione Aspose.Page per Java](https://reference.aspose.com/page/java/).  
- Un ambiente di sviluppo Java configurato sulla tua macchina.

## Importa i pacchetti
Nel tuo progetto Java, inizia importando i pacchetti necessari:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Come disegnare un rettangolo in Java PostScript
Di seguito è riportato il flusso di lavoro completo suddiviso in passaggi chiari. Ogni passaggio include una breve spiegazione seguita dal blocco di codice originale (invariato).

### Passo 1: Imposta la vernice per riempire il rettangolo  
**Come impostare la vernice** – scegliamo un colore di riempimento arancione per il primo rettangolo.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Passo 2: Imposta la vernice per il contorno del rettangolo  
**Imposta colore rettangolo java** – ora cambiamo la vernice in rosso e definiamo una larghezza del contorno.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Passo 3: Chiudi la pagina corrente e salva il documento  
Dopo aver disegnato, chiudiamo la pagina e salviamo il file.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Perché usare Aspose.Page per le grafiche a rettangolo?
- **Cross‑platform**: Genera PostScript standard che funziona su qualsiasi stampante.  
- **Controllo fine‑grained**: Puoi impostare colori di riempimento, colori di contorno e spessori di linea in modo indipendente.  
- **Nessuna dipendenza esterna**: Utilizza solo le classi di geometria AWT integrate.  

## Problemi comuni e consigli
- **Errori di percorso file** – assicurati che `dataDir` termini con un separatore di file (`/` o `\\`).  
- **Eccezioni di licenza** – la versione di prova aggiunge una filigrana; ottieni una licenza completa per l'uso in produzione.  
- **Visibilità del colore** – alcune stampanti possono interpretare diversamente alcuni valori RGB; testa prima con un semplice rettangolo nero.

## Conclusione
In questa guida abbiamo dimostrato **come disegnare rettangoli** in un documento Java PostScript, trattato **come impostare la vernice**, e mostrato come **impostare colore rettangolo java** usando Aspose.Page. Sentiti libero di sperimentare con forme, colori e stili di linea diversi per creare grafiche stampabili ricche per report, fatture o stampe personalizzate.

## Domande frequenti

### Posso usare Aspose.Page per Java con altri linguaggi di programmazione?
Aspose.Page supporta principalmente Java, ma librerie simili sono disponibili per altri linguaggi.

### È disponibile una versione di prova di Aspose.Page per Java?
Sì, puoi esplorare le funzionalità di Aspose.Page per Java con la [versione di prova gratuita](https://releases.aspose.com/).

### Dove posso trovare ulteriore aiuto e discussioni?
Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per interagire con la community e ottenere assistenza.

### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
Ottieni una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Dove posso acquistare una versione con licenza di Aspose.Page per Java?
Acquista una versione con licenza [qui](https://purchase.aspose.com/buy).

**Domande aggiuntive**

**Q:** *Posso cambiare dinamicamente le dimensioni del rettangolo?*  
**A:** Sì – basta modificare i parametri `Rectangle2D.Float(x, y, width, height)` prima di chiamare `fill` o `draw`.

**Q:** *È possibile aggiungere testo all'interno del rettangolo?*  
**A:** Assolutamente. Dopo aver disegnato il rettangolo, usa `document.drawString(...)` con il font e la posizione desiderati.

**Q:** *Aspose.Page supporta altre forme come cerchi o poligoni?*  
**A:** Sì, l'API fornisce metodi come `drawEllipse` e `drawPolygon` per una varietà di grafica vettoriale.

---

**Ultimo aggiornamento:** 2025-12-11  
**Testato con:** Aspose.Page for Java 24.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}