---
date: 2026-05-30
description: Scopri come creare un documento XPS in Java usando Aspose.Page e aggiungere
  un'immagine a mosaico senza sforzo con questa guida passo-passo. Come creare file
  XPS rapidamente.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Aggiungi immagine a mosaico in Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Come creare un documento XPS con un'immagine a mosaico in Java
url: /it/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un documento XPS con un'immagine a tasselli in Java

## Introduzione
Creare documenti XPS programmaticamente è una competenza fondamentale per gli sviluppatori Java che necessitano di output stampabile e indipendente dal dispositivo. **Come creare XPS** file in modo efficiente è risposto da Aspose.Page per Java, che astrae i dettagli a basso livello della XML Paper Specification e ti consente di concentrarti sul design visivo. In questa guida vedrai esattamente come creare un documento XPS, aggiungere un'immagine a tasselli come sfondo o motivo, e salvare il risultato—tutto con codice conciso, pronto per la produzione.

## Risposte rapide
- **Cosa fa Aspose.Page?** Fornisce un'API di alto livello per generare e manipolare documenti XPS in Java.  
- **Posso creare un'immagine a tasselli?** Sì – usa `XpsImageBrush` con `XpsTileMode.Tile`.  
- **È necessaria una licenza?** È richiesta una licenza temporanea o commerciale per l'uso in produzione.  
- **Quale versione di Java è supportata?** Qualsiasi JDK 8+ è compatibile.  
- **Quanto tempo richiede l'implementazione?** Circa 10–15 minuti per uno scenario base di immagine a tasselli.

## Cos'è “creare documento XPS”?
`XpsDocument` è l'oggetto di livello superiore di Aspose.Page che rappresenta un singolo file XPS in memoria. Incapsula pagine, risorse e metadati, consentendoti di costruire il documento programmaticamente. Creare un documento XPS significa istanziare questa classe, aggiungere elementi visivi e infine chiamare `save` per scrivere il file a layout fisso su disco. Questo approccio elimina la gestione manuale dell'XML e garantisce la conformità alla XML Paper Specification.

## Perché aggiungere un'immagine a tasselli?
Il tassellamento ripete un'immagine su un'area definita, ideale per sfondi, filigrane o riempimenti a motivo. Usando `XpsTileMode.Tile` l'immagine si ripete automaticamente senza duplicazione manuale, risparmiando tempo di sviluppo e assicurando un rendering coerente su qualsiasi dispositivo. Le immagini a tasselli mantengono anche le dimensioni del file basse perché la stessa risorsa bitmap viene riutilizzata anziché incorporata più volte.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – JDK 8 o versioni successive installate.  
2. **Aspose.Page per Java** – scaricalo dal [sito web](https://releases.aspose.com/page/java/).  
3. **Una directory scrivibile** – dove verrà salvato il file XPS generato.

## Importare i pacchetti
Nel tuo progetto Java, importa le classi necessarie:

`XpsDocument` è l'oggetto principale che rappresenta un file XPS.  
`XpsImageBrush` dipinge forme usando una sorgente immagine.  
`XpsTileMode` specifica come un'immagine viene tassellata.  
`Rectangle2D` descrive una regione rettangolare per il posizionamento.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guida passo‑passo

### Passo 1: Configura il tuo progetto
Aggiungi i file JAR di Aspose.Page al classpath del progetto e verifica che le istruzioni di importazione compilino senza errori.

### Passo 2: Crea il documento XPS
`XpsDocument` è il contenitore principale che contiene pagine, percorsi e risorse. Istanzialo con la dimensione di pagina desiderata, quindi potrai iniziare ad aggiungere elementi grafici.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Passo 3: Definisci il percorso dell'immagine a tasselli
Posiziona l'immagine che desideri tassellare (ad es., `R08LN_NN.jpg`) nella directory indicata da `dataDir`. L'immagine verrà usata come modello di pennello.

### Passo 4: Aggiungi l'immagine a tasselli
Crea un percorso rettangolare e riempilo con un `XpsImageBrush`. Impostando la modalità di tassellatura su `Tile`, l'immagine si ripete lungo il rettangolo. Regola i rettangoli di origine e destinazione per controllare la dimensione e il posizionamento del tassello.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Passo 5: Salva il documento
Persisti il file XPS su disco. Il file di output conterrà l'immagine a tasselli appena definita e potrà essere aperto con qualsiasi visualizzatore XPS.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Ripeti questi passaggi ogni volta che devi **aggiungere un'immagine a tasselli** ad altre pagine o forme all'interno dello stesso documento XPS.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| L'immagine non viene visualizzata | Verifica che il percorso del file (`dataDir + "R08LN_NN.jpg"`) sia corretto e che l'immagine sia accessibile. |
| Il motivo a tasselli appare allungato | Regola i valori di `Rectangle2D` di origine e destinazione per controllare la dimensione del tassello. |
| L'opacità non ha effetto | Assicurati che l'opacità del pennello sia impostata **dopo** la configurazione della modalità di tassellatura. |

## Domande frequenti

**D:** Aspose.Page è compatibile con tutte le versioni di Java?  
**R:** Aspose.Page supporta Java 8 fino a Java 21; la matrice completa di compatibilità è disponibile [qui](https://reference.aspose.com/page/java/).

**D:** Posso usare Aspose.Page per progetti commerciali?  
**R:** Sì, è necessaria una licenza commerciale per l'uso in produzione. Le opzioni di acquisto sono elencate [qui](https://purchase.aspose.com/buy).

**D:** È disponibile una versione di prova gratuita?  
**R:** È possibile scaricare una prova gratuita completamente funzionale dalla pagina dei rilasci di Aspose [qui](https://releases.aspose.com/).

**D:** Dove posso ottenere supporto dalla community?  
**R:** Unisciti al forum della community di Aspose.Page su [forum](https://forum.aspose.com/c/page/39) per porre domande e condividere esempi.

**D:** Come ottengo una licenza temporanea per la valutazione?  
**R:** Le licenze temporanee sono fornite su richiesta tramite il portale Aspose [qui](https://purchase.aspose.com/temporary-license/).

## Conclusione
Ora disponi di un flusso di lavoro completo, pronto per la produzione, su **come creare XPS** documenti con immagini a tasselli usando Aspose.Page per Java. Sfruttando `XpsImageBrush` e `XpsTileMode.Tile`, puoi generare grafiche ricche e ripetibili senza gonfiare le dimensioni del file. Sperimenta con diverse dimensioni di tassello, livelli di opacità e forme per costruire layout di documento sofisticati. Per il passo successivo, esplora l'aggiunta di forme vettoriali o sovrapposizioni di testo per migliorare ulteriormente i tuoi file XPS.

---

**Ultimo aggiornamento:** 2026-05-30  
**Testato con:** Aspose.Page per Java 24.12 (ultima versione)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Add Pages to XPS Tutorial](/page/java/xps-page-manipulation/add-page/)
- [Convert XPS to PDF in Java using Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}