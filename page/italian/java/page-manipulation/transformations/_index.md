---
date: 2026-02-07
description: Scopri come scalare un rettangolo con Aspose.Page per Java, come traslare
  una forma e applicare una trasformazione affine per creare documenti PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Come scalare un rettangolo con Aspose.Page per Java
url: /it/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ridimensionare un rettangolo con Aspose.Page per Java

## Introduzione
Benvenuti a una guida completa sull'utilizzo delle potenti funzionalità di **Aspose.Page for Java** per eseguire una varietà di trasformazioni di pagina. In questo tutorial imparerete **how to scale rectangle**, tradurre forme, ruotare oggetti e **apply affine transform** mentre create un **PostScript document**. Queste capacità vi consentono di costruire applicazioni Java ricche e intensive di grafica senza dover gestire codice di rendering a basso livello.

## Risposte rapide
- **Come faccio a ridimensionare un rettangolo in Java con Aspose.Page?** Usa il metodo `document.scale()` prima di disegnare la forma.  
- **Posso spostare (traslare) una forma senza influenzare altre grafiche?** Sì—salva lo stato grafico, chiama `document.translate(x, y)`, disegna, poi ripristina lo stato.  
- **Quale classe crea un file PostScript?** `PsDocument` together with `PsSaveOptions`.  
- **Ho bisogno di una licenza per l'uso in produzione?** È necessaria una licenza valida di Aspose.Page per le distribuzioni commerciali.  
- **Quale versione di Java è supportata?** Aspose.Page works with Java 8 and later.

## Prerequisiti
Prima di immergerci nella guida passo‑per‑passo, assicuratevi di avere i seguenti prerequisiti:

- Conoscenza di base della programmazione Java.  
- Libreria Aspose.Page per Java installata. Puoi scaricarla dalla [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Un ambiente di sviluppo integrato Java (IDE) configurato sulla tua macchina.

## Importare i pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per utilizzare Aspose.Page for Java:

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
Ridimensionare un rettangolo ne modifica le dimensioni lungo gli assi X e Y mantenendo la forma. Aspose.Page espone il metodo `scale(float sx, float sy)`, che applica un **affine transform** allo stato grafico corrente. Questa è la tecnica principale dietro la parola chiave **how to scale rectangle**.

## Come tradurre una forma con Aspose.Page
La traduzione sposta una forma in una nuova posizione senza alterarne le dimensioni. Questa è l'essenza di **how to translate shape**. Salvando lo stato grafico, applicando `translate(dx, dy)`, disegnando e poi ripristinando lo stato, si mantengono gli altri oggetti inalterati.

## Esempio 1: Nessuna trasformazione
Il primo esempio disegna un semplice rettangolo senza alcuna trasformazione applicata. Questo serve come base di confronto per gli esempi successivi.

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

## Esempio 2: Traslazione
Qui dimostriamo **how to translate shape** spostando il contesto grafico di 250 unità verso destra prima di disegnare un secondo rettangolo.

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

## Esempio 3: Ridimensionamento
Questo esempio risponde alla domanda principale **how to scale rectangle**. Riduciamo il rettangolo al 50 % della sua larghezza originale e al 75 % della sua altezza.

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

## Come ruotare una forma Java (rotate shape java)
La rotazione è un'altra operazione affine comune. Sebbene i frammenti di codice per la rotazione siano omessi per brevità, il modello è identico: salva lo stato grafico, chiama `document.rotate(angle)`, disegna la forma, poi ripristina. Questo dimostra **rotate shape java** e **how to rotate rectangle** nella pratica.

## Perché è importante – Benefici nel mondo reale
- **Device‑independent output** – Scrivi una volta e genera PostScript o XPS senza modifiche specifiche per la piattaforma.  
- **Fine‑grained control** – Combina traslazione, ridimensionamento, shear e rotazione per soddisfare requisiti di layout precisi.  
- **Performance‑oriented** – API a basso overhead ideale per l'elaborazione batch di documenti di grandi dimensioni.  

## Casi d'uso comuni
- Generazione di fatture stampabili – ad esempio, una soluzione **printable invoice java** che posiziona loghi e codici a barre con precisione.  
- Creazione di diagrammi tecnici dove sono richiesti ridimensionamento e posizionamento precisi.  
- Automazione della produzione di report multipagina in formato PostScript.  

## Problemi comuni e soluzioni
- **Transformation not resetting** – Sempre accoppia `document.writeGraphicsSave()` con `document.writeGraphicsRestore()` per evitare effetti di carry‑over indesiderati.  
- **Unexpected colors** – Assicurati di impostare il paint dopo ogni trasformazione; lo stato grafico non conserva le impostazioni di colore precedenti dopo un ripristino.  
- **File size too large** – Usa `PsSaveOptions` per abilitare la compressione o ridurre la risoluzione dell'immagine quando incorpori grafica raster.  

## FAQ
### Posso usare Aspose.Page per Java per altri formati di documento?
Aspose.Page primarily focuses on page manipulation for PostScript and XPS formats.

### Dove posso trovare più esempi e documentazione per Aspose.Page per Java?
Visita la [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) per informazioni complete.

### È disponibile una prova gratuita per Aspose.Page per Java?
Sì, puoi accedere a una prova gratuita [qui](https://releases.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
Ottieni una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Dove posso cercare supporto della community o fare domande su Aspose.Page per Java?
Visita il [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) per discussioni della community.

## Domande frequenti

**Q: Qual è la differenza tra `translate` e `scale`?**  
A: `translate` sposta l'origine del sistema di coordinate, mentre `scale` cambia le dimensioni degli oggetti disegnati lungo gli assi X e/o Y.

**Q: Posso combinare più trasformazioni in un unico stato grafico?**  
A: Sì—chiamando `translate`, `scale`, `rotate` o `shear` in sequenza prima di disegnare, crei una trasformazione affine combinata.

**Q: Come resetto le trasformazioni dopo aver disegnato una forma?**  
A: Usa `document.writeGraphicsRestore()` per tornare allo stato grafico precedentemente salvato.

**Q: È possibile ruotare un rettangolo attorno al suo centro?**  
A: Assolutamente. Trasla il rettangolo all'origine, applica `rotate(angle)`, poi traslalo nuovamente prima di disegnarlo.

**Q: Aspose.Page supporta l'anti‑aliasing per grafica più fluida?**  
A: Sì—imposta le opzioni di rendering appropriate in `PsSaveOptions` per abilitare l'anti‑aliasing.

---

**Ultimo aggiornamento:** 2026-02-07  
**Testato con:** Aspose.Page for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}