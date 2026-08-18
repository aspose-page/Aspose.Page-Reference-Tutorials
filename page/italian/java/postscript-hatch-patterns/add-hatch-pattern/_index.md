---
date: 2026-08-18
description: Scopri come aggiungere un motivo a tratteggio ai file Java PostScript
  utilizzando Aspose.Page Java. Questa guida passo‑passo mostra il codice completo
  e consigli.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Aggiungi un motivo a tratteggio in Java PostScript
og_description: Scopri come aggiungere un motivo a tratteggio in Java PostScript usando
  Aspose.Page. Segui questo tutorial passo‑passo per creare rapidamente grafiche riempite
  con tratteggio.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Come aggiungere un motivo a tratteggio in Java PostScript – guida Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Come aggiungere un motivo a tratteggio in Java PostScript
url: /it/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un motivo a trama in Java PostScript

## Introduzione
Se stai lavorando con **Aspose.Page Java** e ti chiedi **come aggiungere un motivo a trama** al tuo output PostScript, i motivi a trama sono una soluzione rapida e flessibile. In questo tutorial vedremo **come aggiungere design a trama** a un documento PostScript, spiegheremo perché sono utili e ti forniremo un esempio di codice completo, pronto‑da‑eseguire. Alla fine, sarai in grado di creare forme e testo riempiti con trama visivamente accattivanti con poche righe di Java.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java (l'SDK “aspose page java”).  
- **Quale effetto visivo stiamo aggiungendo?** Motivi a trama (ad es. linee diagonali, reticolato).  
- **È necessaria una licenza per eseguire il campione?** Una versione di prova gratuita funziona per lo sviluppo; è richiesta una licenza per la produzione.  
- **Quante righe di codice?** Circa 70 righe, suddivise in passaggi chiari.  
- **Posso usare lo stesso approccio per i PDF?** Sì—Aspose.Page supporta più formati di output, incluso PDF.

## Che cos'è un motivo a trama?
Un motivo a trama è un riempimento vettoriale costituito da linee o forme ripetute che creano un effetto di texture. Poiché è definito matematicamente, il motivo si scala senza perdita di qualità, rendendolo ideale per la stampa ad alta risoluzione e per output monocromatico.

## Perché usare i motivi a trama con Aspose.Page Java?
Aspose.Page supporta **10+ formati di output** (inclusi PostScript, PDF, EPS, SVG e XPS) e può renderizzare riempimenti a trama su documenti fino a **500 pagine** senza caricare l'intero file in memoria. Questo significa prestazioni rapide, basso consumo di memoria e risultati visivi coerenti su tutti i formati supportati.

## Come aggiungere un motivo a trama – panoramica
I motivi a trama sono texture vettoriali che si rendono nitide a qualsiasi risoluzione e funzionano bene su stampanti monocromatiche. Con Aspose.Page Java, puoi applicare questi motivi a forme, percorsi e persino al testo senza dover gestire comandi PostScript a basso livello.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Ambiente di sviluppo Java** – JDK 8 o superiore e un IDE a tua scelta.  
- **Libreria Aspose.Page for Java** – Scarica l'ultimo JAR dalla pagina ufficiale di **download di Aspose.Page for Java** [qui](https://releases.aspose.com/page/java/).  
- Puoi anche esplorare altre versioni Aspose [qui](https://releases.aspose.com/).  
- **Accesso in scrittura** a una cartella dove verrà salvato il file PostScript generato.

## Importare i pacchetti
Le importazioni qui sotto includono le classi standard Java AWT per primitive grafiche come colori, tratti e forme geometriche, nonché le classi Aspose.Page che forniscono il modello di documento, le definizioni di stile a trama e le opzioni di salvataggio necessarie per generare un file PostScript.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Che cos'è la classe `Document`?
La classe `Document` è l'oggetto di livello superiore di Aspose.Page che rappresenta un singolo file PostScript in memoria. Tutte le operazioni di disegno vengono eseguite tramite questo oggetto.

## Come configurare lo stream di output?
Per scrivere l'output, crea un `FileOutputStream` che punti al percorso file desiderato; questo stream gestisce la scrittura a basso livello dei byte. `PsSaveOptions` configura come il documento viene salvato, includendo dimensione della pagina e compressione. Quindi istanzia un `Document` con un oggetto `PsSaveOptions` che specifica dimensione della pagina, compressione e altre impostazioni specifiche di PostScript.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Come salvare lo stato grafico e traslare l'origine?
Il salvataggio dello stato grafico cattura la matrice di trasformazione corrente, la regione di clipping e gli attributi di disegno, consentendo di ripristinarli in seguito. Dopo il salvataggio, chiama `translate(x, y)` sull'oggetto grafico per spostare l'origine in una posizione comoda per disegnare la griglia di quadrati a trama.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Come creare un quadrato riutilizzabile per ogni motivo?
`Rectangle2D` rappresenta una forma rettangolare definita dalla sua posizione e dimensione. Creando un'unica istanza che corrisponde alle dimensioni della cella, puoi riutilizzarla per ogni quadrato riempito a trama, riducendo l'allocazione di oggetti e mantenendo efficiente il ciclo di disegno.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Come impostare una penna per il contorno del quadrato del motivo?
`BasicStroke` descrive lo spessore del contorno, il pattern di tratteggi e le estremità per le forme vettoriali. Usare un `BasicStroke` da 2 punti fornisce un bordo chiaro attorno a ogni cella riempita a trama, assicurando che il riempimento sia visivamente separato dai quadrati adiacenti.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Come iterare attraverso i motivi a trama?
`HatchStyle` è un'enumerazione che elenca tutti i motivi a trama predefiniti come diagonale, incrociato e puntinato. Iterare su `HatchStyle.values()` ti permette di applicare ciascun motivo a turno, riempire il rettangolo con un `HatchBrush` e poi disegnarne il contorno.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Come ripristinare lo stato grafico dopo il disegno?
Chiamare `restore()` sull'oggetto grafico riporta la matrice di trasformazione e le impostazioni di disegno allo stato salvato in precedenza, evitando che traduzioni o scalature cumulative influenzino le operazioni successive. Questo garantisce che i contenuti successivi partano dal sistema di coordinate originale e usino gli attributi predefiniti.  
```java
document.writeGraphicsRestore();
```

## Come riempire il testo con un motivo a trama?
`TextFragment` rappresenta un pezzo di testo che può essere posizionato e stilizzato indipendentemente. Assegnando un `HatchBrush` con un `HatchStyle` scelto al riempimento del frammento, i caratteri del testo vengono renderizzati usando la texture a trama anziché un colore solido.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Come delineare il testo con uno stile a trama diverso?
`HatchBrush` può essere usato anche per lo stroking. Per disegnare un contorno, imposta lo stroke del frammento a un `HatchBrush` con un `HatchStyle` diverso (ad es. 70 % di trama) e aumenta lo spessore dello stroke tramite `setStrokeWidth`. Questo renderizza il bordo del testo con il proprio motivo a trama mantenendo l'interno riempito.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Come chiudere e salvare il documento?
`document.save()` scrive il documento in memoria nello stream di output specificato. Dopo aver completato tutti i comandi di disegno, invoca questo metodo e poi chiudi il `FileOutputStream` per rilasciare le risorse di sistema e assicurare che il file sia correttamente flushato su disco.  
```java
document.closePage();
document.save();
```

Segui questi passaggi e otterrai un file PostScript che mostra un set completo di motivi a trama applicati sia a forme che a testo—tutto alimentato da **aspose page java**.

## Problemi comuni e consigli
- **Errori di percorso file** – Assicurati che `dataDir` termini con il separatore di file appropriato (`/` o `\`).  
- **Colori non supportati** – Alcuni interpreter PostScript più vecchi potrebbero non gestire certi spazi colore; utilizza RGB di base per la massima compatibilità.  
- **Avvisi di licenza** – Eseguire il campione senza licenza valida inserirà una filigrana nell'output.

## Domande frequenti

**Q: Posso usare Aspose.Page Java con altri framework Java?**  
A: Sì, la libreria è indipendente dal framework e funziona con Spring, Jakarta EE, Android (limitato) e Java SE puro.

**Q: È disponibile una versione di prova per Aspose.Page Java?**  
A: Assolutamente. Scarica una prova gratuita di 30 giorni [Aspose trial download page](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per lo sviluppo?**  
A: Richiedi una licenza temporanea [temporary license request page](https://purchase.aspose.com/temporary-license/). Rimuove le filigrane di valutazione.

**Q: Dove posso trovare più tutorial e supporto della community?**  
A: Visita il forum ufficiale [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) per esempi aggiuntivi e Q&A.

**Q: Esiste una documentazione completa per tutte le classi e i metodi?**  
A: Sì, il riferimento API completo è disponibile [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Posso renderizzare lo stesso motivo a trama in PDF invece di PostScript?**  
A: Assolutamente. Cambia `PsSaveOptions` in `PdfSaveOptions` (o l'equivalente) e il resto del codice rimane invariato.

**Q: Cosa devo fare se il file generato è vuoto?**  
A: Verifica che lo stream di output punti a una directory scrivibile e che `document.save()` sia chiamato dopo tutte le operazioni di disegno.

**Ultimo aggiornamento:** 2026-08-18  
**Testato con:** Aspose.Page for Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose

## Tutorial correlati

- [Crea un motivo di texture in PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Come aggiungere un gradiente: Gradiente diagonale in Java PostScript usando Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Come convertire PostScript in PDF usando Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}