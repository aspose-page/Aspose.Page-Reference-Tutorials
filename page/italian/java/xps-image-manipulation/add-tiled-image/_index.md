---
date: 2025-12-28
description: Scopri come creare un documento XPS in Java usando Aspose.Page e aggiungere
  un’immagine a tasselli senza sforzo con questa guida passo‑passo.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Come creare un documento XPS con un'immagine a mosaico in Java
url: /it/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento XPS e aggiungi un'immagine affiancata in Java

## Introduzione
Nello sviluppo Java moderno, la capacità di **creare documenti XPS** programmaticamente è una competenza preziosa, soprattutto quando è necessario arricchirli con grafiche come immagini affiancate. Aspose.Page per Java rende questo processo semplice, permettendoti di concentrarti sul design visivo piuttosto che sulla gestione a basso livello dei file. In questo tutorial imparerai esattamente come creare un documento XPS, **aggiungere un'immagine affiancata**, e salvare il risultato, il tutto con esempi di codice chiari, passo dopo passo.

## Risposte rapide
- **Cosa fa Aspose.Page?** Fornisce un'API di alto livello per generare e manipolare documenti XPS in Java.  
- **Posso affiancare un'immagine?** Sì – usa `XpsImageBrush` con `XpsTileMode.Tile`.  
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea o commerciale per l'uso in produzione.  
- **Quale versione di Java è supportata?** Qualsiasi JDK 8+ è compatibile.  
- **Quanto tempo richiede l'implementazione?** Circa 10–15 minuti per uno scenario di immagine affiancata di base.

## Cos'è “creare documento XPS”?
Un file XPS (XML Paper Specification) è un formato di documento a layout fisso simile al PDF. Creare un documento XPS programmaticamente ti consente di generare file stampabili e indipendenti dal dispositivo direttamente dal codice Java.

## Perché aggiungere un'immagine affiancata?
Affiancare un'immagine ripete la grafica su un'area definita, il che è perfetto per sfondi, filigrane o riempimenti a motivo. Usando `XpsTileMode.Tile` di Aspose.Page è possibile ottenere questo risultato con poche righe di codice.

## Prerequisiti
Prima di immergerti, assicurati di avere:

1. **Java Development Kit (JDK)** – JDK 8 o più recente installato.  
2. **Aspose.Page for Java** – download dal [website](https://releases.aspose.com/page/java/).  
3. **Una directory scrivibile** – dove verrà salvato il file XPS generato.

## Importa pacchetti
Nel tuo progetto Java, importa le classi necessarie:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guida passo‑passo

### Passo 1: Configura il tuo progetto
Aggiungi i file JAR di Aspose.Page al classpath del tuo progetto e verifica che le istruzioni di importazione si compilino senza errori.

### Passo 2: Crea documento XPS
Istanzia un nuovo oggetto `XpsDocument`. Questo è il contenitore principale che conterrà tutte le pagine, i percorsi e le risorse.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Passo 3: Definisci il percorso dell'immagine affiancata
Posiziona l'immagine che desideri affiancare (ad esempio `R08LN_NN.jpg`) nella directory a cui fa riferimento `dataDir`. L'immagine verrà utilizzata come modello per il pennello.

### Passo 4: Aggiungi immagine affiancata
Crea un percorso rettangolare e riempilo con un `XpsImageBrush`. Impostando la modalità di affiancamento su `Tile`, l'immagine si ripete all'interno del rettangolo.

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
Salva il file XPS su disco. Il file di output conterrà l'immagine affiancata appena definita.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Ripeti questi passaggi ogni volta che devi **aggiungere un'immagine affiancata** ad altre pagine o forme all'interno dello stesso documento XPS.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| L'immagine non viene visualizzata | Verifica che il percorso del file (`dataDir + "R08LN_NN.jpg"`) sia corretto e che l'immagine sia accessibile. |
| Il motivo affiancato appare allungato | Regola i valori di `Rectangle2D` di origine e destinazione per controllare la dimensione del tassello. |
| L'opacità non ha effetto | Assicurati che l'opacità del pennello sia impostata **dopo** la configurazione della modalità di affiancamento. |

## Domande frequenti

### Aspose.Page è compatibile con tutte le versioni di Java?
Aspose.Page è progettato per funzionare con varie versioni di Java. Verifica la compatibilità consultando la documentazione [qui](https://reference.aspose.com/page/java/).

### Posso usare Aspose.Page per progetti commerciali?
Sì, Aspose.Page offre licenze commerciali. Acquistale [qui](https://purchase.aspose.com/buy).

### È disponibile una versione di prova gratuita?
Sì, esplora le funzionalità di Aspose.Page con una versione di prova gratuita [qui](https://releases.aspose.com/).

### Dove posso trovare supporto e discussioni della community?
Partecipa alla community di Aspose.Page sul [forum](https://forum.aspose.com/c/page/39).

### Come posso ottenere una licenza temporanea per Aspose.Page?
Ottieni una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2025-12-28  
**Testato con:** Aspose.Page for Java 24.12 (latest)  
**Autore:** Aspose