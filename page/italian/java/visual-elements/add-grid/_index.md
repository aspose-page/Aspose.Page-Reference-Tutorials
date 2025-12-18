---
date: 2025-12-18
description: Impara come aggiungere una griglia e un rettangolo trasparente nei documenti
  XPS Java con Aspose.Page. Guida passo passo per salvare il documento XPS in modo
  efficiente.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Come aggiungere una griglia usando Visual Brush in Java
url: /it/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere una griglia usando Visual Brush in Java

## Introduzione
Se stai cercando **come aggiungere una griglia** agli XPS generati da Java, sei nel posto giusto. In questo tutorial ti guideremo nell'aggiungere una griglia con un Visual Brush, nel sovrapporre un rettangolo trasparente e infine **salvare il documento XPS** usando l'Aspose.Page Java API. Alla fine avrai un risultato visivo raffinato che potrà essere riutilizzato in report, fatture o qualsiasi applicazione con molti documenti.

## Risposte rapide
- **Che cosa fa un Visual Brush?** Dipinge un'area definita con contenuto visivo riutilizzabile, perfetto per pattern ripetuti come le griglie.  
- **Posso cambiare il colore della griglia?** Sì – modifica le impostazioni del pennello a colore solido.  
- **Come aggiungere un rettangolo trasparente sopra la griglia?** Usa `setOpacity` su un percorso riempito con un colore solido.  
- **Quale metodo salva il file?** `doc.save(...)` scrive il file XPS su disco.  
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea o completa per l'uso in produzione.

## Che cos'è una griglia Visual Brush?
Un Visual Brush ti consente di definire un piccolo elemento visivo (il pattern della griglia) e poi di ripeterlo su un'area più ampia. Questo approccio è più efficiente in termini di memoria rispetto al disegnare ogni linea singolarmente e garantisce una ripetizione pixel‑perfect.

## Perché usare Aspose.Page per questo compito?
- **Cross‑platform** – Funziona su qualsiasi OS che supporta Java.  
- **Rendering ad alta fedeltà** – Controllo preciso su colori, opacità e tiling.  
- **Nessuna dipendenza esterna** – Tutto è gestito tramite la libreria Aspose.Page.

## Prerequisiti
- Conoscenza di base della programmazione Java.  
- Libreria Aspose.Page installata – puoi scaricarla dalla [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- JDK 8 o successivo configurato sulla tua macchina di sviluppo.

## Importare i pacchetti
Per prima cosa, importa le classi necessarie affinché il compilatore sappia dove trovare i tipi che utilizzeremo:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Guida passo‑passo

### Passo 1: Configura il tuo progetto
Crea una nuova istanza `XpsDocument` e indica la cartella in cui desideri salvare il file di output.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Passo 2: Crea un Visual Brush a griglia magenta
Definiamo una piccola forma magenta che verrà ripetuta sull'area della griglia.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Passo 3: Definisci la geometria per il Grid Brush
Imposta l'area rettangolare che riceverà il visual ripetuto.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Passo 4: Crea un nuovo Canvas per il documento
Aggiungi un canvas al documento e posizionalo dove deve apparire la griglia.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Passo 5: Aggiungi la griglia al Canvas
Applica il visual brush alla geometria, abilitando il tiling.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Passo 6: Aggiungi un rettangolo rosso trasparente (funzionalità secondaria)
Qui dimostriamo **aggiungere un rettangolo trasparente** sopra la griglia per enfatizzare.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Passo 7: Salva il documento XPS risultante
Infine, scrivi il documento su disco—questo è il passaggio per **salvare il documento XPS**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Segui questi passaggi e otterrai una griglia dall'aspetto professionale con una sovrapposizione trasparente, generata interamente in modo programmatico.

## Problemi comuni e consigli

- **Dimensione tile errata:** Assicurati che il `Rectangle2D` usato per il brush corrisponda alla dimensione di ripetizione desiderata; altrimenti il pattern potrebbe allungarsi.  
- **Opacità non applicata:** Ricorda di chiamare `setOpacity` sul percorso che vuoi rendere trasparente; non influirà sul brush stesso.  
- **File non salvato:** Verifica che `dataDir` punti a una cartella esistente e che la tua applicazione abbia i permessi di scrittura.

## Domande frequenti

**D: Aspose.Page è adatto per la generazione professionale di documenti?**  
R: Sì, Aspose.Page è una libreria robusta progettata per la generazione di XPS e PDF di alta qualità in Java.

**D: Posso personalizzare i colori della griglia usando Visual Brush?**  
R: Assolutamente! Cambia i parametri di `createColor` nella chiamata `setFill` del brush con i valori RGBA che ti servono.

**D: Dove posso trovare supporto aggiuntivo per Aspose.Page?**  
R: Visita il [Aspose.Page forum](https://forum.aspose.com/c/page/39) per aiuto della community e risposte ufficiali.

**D: È disponibile una versione di prova gratuita per Aspose.Page?**  
R: Sì, puoi accedere alla [free trial](https://releases.aspose.com/) per esplorare tutte le funzionalità prima dell'acquisto.

**D: Come posso ottenere una licenza temporanea per i test?**  
R: Acquista una [temporary license](https://purchase.aspose.com/temporary-license/) valida per sviluppo e valutazione.

**Ultimo aggiornamento:** 2025-12-18  
**Testato con:** Aspose.Page for Java 23.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}