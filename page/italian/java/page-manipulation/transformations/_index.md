---
date: 2026-10-20
description: Scopri come ridimensionare un rettangolo con Aspose.Page per Java, come
  traslare una forma e applicare una trasformazione affine per creare documenti PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Trasformazioni nella manipolazione di pagine Java
og_description: Scopri come ridimensionare un rettangolo, traslare una forma e applicare
  una trasformazione affine usando Aspose.Page per Java per generare file PostScript
  in modo efficiente.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Come ridimensionare un rettangolo con Aspise.Page per Java – guida passo
  passo
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Come ridimensionare un rettangolo con Aspose.Page per Java
url: /it/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ridimensionare un rettangolo con Aspose.Page per Java

## Introduzione
In questa guida scoprirai **how to scale rectangle** oggetti usando Aspose.Page per Java, imparando anche come tradurre le posizioni delle forme, ruotare la grafica e applicare operazioni di trasformazione affine per produrre output PostScript di alta qualità. Queste tecniche ti permettono di creare grafiche sofisticate e indipendenti dal dispositivo senza scrivere codice di rendering a basso livello, rendendo le tue applicazioni Java più potenti e manutenibili.

## Risposte rapide
`scale(sx, sy)` scala il contesto grafico dei fattori orizzontali e verticali forniti.  

- **Come ridimensiono un rettangolo in Java con Aspose.Page?** Chiama il metodo `scale(sx, sy)` sul contesto grafico prima di disegnare il rettangolo.  
- **Posso spostare (traslare) una forma senza influenzare altre grafiche?** Sì—avvolgi la traslazione tra le chiamate `writeGraphicsSave()` e `writeGraphicsRestore()`.  
- **Quale classe crea un file PostScript?** Usa `PsDocument` insieme a `PsSaveOptions`.  
- **Ho bisogno di una licenza per l'uso in produzione?** È necessaria una licenza valida di Aspose.Page per le distribuzioni commerciali.  
- **Quale versione di Java è supportata?** Aspose.Page funziona con Java 8 e successive.

## Prerequisiti
Prima di iniziare, verifica di avere:

- Una solida comprensione della sintassi di base di Java e dei concetti orientati agli oggetti.  
- La libreria Aspose.Page per Java installata. Puoi scaricarla dalla [documentazione Aspose.Page per Java](https://reference.aspose.com/page/java/).  
- Un IDE Java (IntelliJ IDEA, Eclipse o VS Code) configurato con i file JAR della libreria nel classpath.

## Importa pacchetti
`PsDocument` è la classe principale usata per creare un documento PostScript, e `PsSaveOptions` configura come il documento viene salvato.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cos'è “how to scale rectangle” in Aspose.Page?
Il metodo `scale(float sx, float sy)` applica una trasformazione di scala affine allo stato grafico corrente, ridimensionando i disegni successivi dei fattori `sx` (orizzontale) e `sy` (verticale). Questa è l'operazione principale dietro la parola chiave **how to scale rectangle**. Applicando questa trasformazione prima del disegno, tutte le forme successive come i rettangoli verranno renderizzate con le nuove dimensioni preservando le loro proporzioni.

## Come traslare una forma con Aspose.Page
`writeGraphicsSave()` salva lo stato grafico corrente e `writeGraphicsRestore()` lo ripristina, garantendo che le trasformazioni influenzino solo la forma desiderata. La traslazione riposiziona l'origine del sistema di coordinate senza alterare le dimensioni dell'oggetto. Avvolgendo `translate(dx, dy)` con `writeGraphicsSave()` / `writeGraphicsRestore()`, ti assicuri che solo la forma desiderata si sposti mentre le altre grafiche rimangono inalterate, fornendo un controllo preciso sugli elementi individuali.

## Esempio 1: nessuna trasformazione
Il primo esempio disegna un rettangolo senza alcuna trasformazione, stabilendo una base di riferimento per il confronto visivo con gli esempi successivi.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Esempio 2: traslazione
In questo esempio spostiamo il contesto grafico di 250 unità a destra prima di disegnare un secondo rettangolo, illustrando **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Esempio 3: scala
Qui rispondiamo alla domanda principale **how to scale rectangle**. Il rettangolo è ridotto al 50 % della sua larghezza originale e al 75 % della sua altezza originale usando la chiamata `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Come ruotare una forma java (rotate shape java)
`rotate(angle)` ruota il sistema di coordinate dell'angolo specificato in gradi. Carica il tuo `PsDocument`, chiama `rotate(angle)` sullo stato grafico, disegna la forma, poi ripristina lo stato precedente. Questo modello implementa **rotate shape java** e **how to rotate rectangle** in un unico blocco riutilizzabile, permettendoti di ruotare le grafiche attorno a qualsiasi punto tu scelga.

## Perché è importante – benefici concreti
- **Output indipendente dal dispositivo** – Aspose.Page può generare file PostScript e XPS che vengono renderizzati identicamente su qualsiasi stampante o visualizzatore, eliminando le modifiche specifiche della piattaforma.  
- **Controllo fine‑grained** – Combina traslazione, scala, shear e rotazione per soddisfare specifiche di layout esatte; l'API supporta oltre 20 combinazioni di trasformazione per pagina.  
- **Elaborazione orientata alle prestazioni** – La libreria elabora i documenti con un consumo di memoria inferiore a 10 MB per report tipici di 100 pagine, rendendo i lavori batch rapidi e scalabili.

## Casi d'uso comuni
- **Fatture stampabili** – Posiziona con precisione loghi, codici a barre e tabelle usando scala e traslazione per rispettare le linee guida del branding aziendale.  
- **Diagrammi tecnici** – Genera schemi in cui ogni componente deve essere ridimensionato e posizionato proporzionalmente.  
- **Report multi‑pagina automatizzati** – Crea report PostScript che richiedono una scala coerente tra le pagine, come specifiche ingegneristiche.

## Problemi comuni e soluzioni
- **Trasformazione non ripristinata** – Associa sempre `writeGraphicsSave()` con `writeGraphicsRestore()`; altrimenti i disegni successivi ereditano trasformazioni indesiderate.  
- **Colori inaspettati** – Imposta il colore (paint) dopo ogni trasformazione perché lo stato grafico non conserva le informazioni di colore dopo un ripristino.  
- **Dimensione file troppo grande** – Abilita la compressione in `PsSaveOptions` e limita la risoluzione delle immagini raster incorporate per mantenere il file finale sotto i 5 MB per documenti tipici di 50 pagine.

## FAQ

### Posso usare Aspose.Page per Java per altri formati di documento?
Aspose.Page si concentra principalmente sulla manipolazione di pagine per i formati PostScript e XPS, ma offre anche capacità limitate di esportazione PDF.

### Dove posso trovare più esempi e documentazione per Aspose.Page per Java?
Visita la [documentazione Aspose.Page per Java](https://reference.aspose.com/page/java/) per guide complete, riferimenti API e progetti di esempio.

### È disponibile una versione di prova gratuita per Aspose.Page per Java?
Sì, puoi accedere a una prova gratuita tramite la pagina **Aspose free trial download**: [Aspose free trial download](https://releases.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
Ottieni una licenza temporanea tramite la **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Dove posso trovare supporto della community o fare domande su Aspose.Page per Java?
Visita il [forum Aspose.Page per Java](https://forum.aspose.com/c/page/39) per discussioni della community, snippet di codice e suggerimenti di risoluzione dei problemi.

## Domande frequenti

**Q: Qual è la differenza tra `translate` e `scale`?**  
**A:** `translate` sposta l'origine del sistema di coordinate, mentre `scale` cambia la dimensione degli oggetti disegnati lungo gli assi X e/o Y.

**Q: Posso combinare più trasformazioni in un unico stato grafico?**  
**A:** Sì—chiamando `translate`, `scale`, `rotate` o `shear` in sequenza prima del disegno, crei una trasformazione affine combinata.

**Q: Come resetto le trasformazioni dopo aver disegnato una forma?**  
**A:** Usa `writeGraphicsRestore()` per tornare allo stato grafico precedentemente salvato.

**Q: È possibile ruotare un rettangolo attorno al suo centro?**  
**A:** Assolutamente. Trasla il rettangolo all'origine, applica `rotate(angle)`, poi traslalo nuovamente prima del disegno.

**Q: Aspose.Page supporta l'anti‑aliasing per grafiche più fluide?**  
**A:** Sì—imposta le opzioni di rendering appropriate in `PsSaveOptions` per abilitare l'anti‑aliasing.

---

**Ultimo aggiornamento:** 2026-10-20  
**Testato con:** Aspose.Page for Java 24.12  
**Autore:** Aspose

## Tutorial correlati

- [Come disegnare un rettangolo in Java PostScript con Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Crea gradiente radiale in PostScript con Aspose.Page per Java](/page/java/postscript-gradient-addition/)
- [Manipolazione di pagine PostScript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}