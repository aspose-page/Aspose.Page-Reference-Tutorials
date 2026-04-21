---
date: 2026-01-02
description: Scopri come aggiungere una maschera di opacità ai documenti XPS con Aspose.Page
  Java. Guida passo passo per creare un rettangolo di maschera di opacità e migliorare
  la qualità visiva.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Imposta Maschera di Opacità in Java XPS usando Aspose.Page Java
url: /it/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta Maschera di Opacità in Java XPS usando Aspose.Page Java

## Introduzione
Benvenuti alla nostra guida completa sulle **aspose page java** maschere di opacità. In questo tutorial imparerete a creare un documento XPS, aggiungere una canvas e applicare una maschera di opacità a un rettangolo—tutto con la potente API Aspose.Page Java. Alla fine sarete in grado di aggiungere rettangoli con maschera di opacità che conferiscono ai vostri file XPS un aspetto rifinito e semi‑trasparente.

## Risposte Rapide
- **Che cosa fa una maschera di opacità?** Definisce livelli di trasparenza variabili per una forma, consentendo al contenuto sottostante di trasparire.
- **Quale libreria è necessaria?** Aspose.Page per Java (aspose page java).
- **È necessaria una licenza?** Una licenza temporanea è sufficiente per i test; è richiesta una licenza completa per la produzione.
- **Quante righe di codice?** Circa 20 righe di Java più alcune istruzioni di configurazione.
- **Posso riutilizzare la maschera su più forme?** Sì, è possibile assegnare lo stesso ImageBrush a diversi percorsi.

## Cos'è una Maschera di Opacità in XPS?
Una maschera di opacità è una bitmap o un vettore che controlla l'alpha (trasparenza) di ogni pixel in una forma. Quando viene applicata a un rettangolo, parti del rettangolo diventano completamente opache, parzialmente trasparenti o completamente trasparenti, creando effetti visivi sofisticati.

## Perché usare Aspose.Page Java per le Maschere di Opacità?
- **API completa in stile .NET per Java** – modello di oggetti intuitivo.
- **Nessuna dipendenza esterna** – funziona con Java puro.
- **Rendering ad alta fedeltà** – le maschere vengono renderizzate esattamente come nella specifica XPS.
- **Cross‑platform** – funziona su Windows, Linux o macOS senza modifiche.

## Prerequisiti
- Una conoscenza di base della programmazione Java.  
- Libreria Aspose.Page per Java installata. È possibile scaricarla **[qui](https://releases.aspose.com/page/java/)**.  
- Una licenza valida per Aspose.Page. Se non ne possiedi una, ottieni una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)**.  
- Un ambiente di sviluppo in grado di compilare ed eseguire applicazioni Java (ad es., IntelliJ IDEA, Eclipse o VS Code).

## Importa Pacchetti
Inizia importando le classi necessarie dalla libreria Aspose.Page. Questo garantisce che l'API sia disponibile nel tuo progetto.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guida Passo‑Passo

### Passo 1: Crea un Nuovo Documento XPS
Per prima cosa, istanzia un nuovo documento XPS che conterrà tutti i nostri elementi grafici.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Passo 2: Aggiungi una Canvas
Una canvas funge da superficie di disegno all'interno della pagina XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Passo 3: Aggiungi un Rettangolo e Applica un Riempimento Solido
Qui creiamo un percorso rettangolare e gli assegniamo un riempimento rosso solido. Questo rettangolo riceverà in seguito la maschera di opacità.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Passo 4: Aggiungi una Maschera di Opacità Usando un ImageBrush
Carichiamo un'immagine TIFF, definiamo i rettangoli di origine e destinazione e impostiamo il brush in modalità tile in modo che la maschera si ripeta se necessario.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Passo 5: Salva il Documento XPS Resultante
Infine, salva il documento su disco. Il file di output conterrà il rettangolo con la maschera di opacità applicata.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Segui attentamente questi passaggi per incorporare la funzionalità **add opacity mask** nel tuo documento Java XPS usando Aspose.Page.

## Problemi Comuni & Risoluzione dei Problemi
- **Immagine non trovata** – Verifica che `dataDir` punti alla cartella corretta e che `R08SY_NN.tif` esista.
- **La maschera appare solida** – Assicurati che l'immagine di origine contenga effettivamente valori alpha variabili; un'immagine completamente opaca non mostrerà trasparenza.
- **Modalità tile non rispettata** – Il rettangolo di destinazione deve essere più piccolo del rettangolo di origine affinché il tiling sia evidente.

## Domande Frequenti

**D: Aspose.Page è compatibile con tutti gli ambienti di sviluppo Java?**  
R: Sì, Aspose.Page è progettato per funzionare senza problemi con vari IDE Java e strumenti di build.

**D: Posso usare Aspose.Page senza licenza?**  
R: Sebbene sia possibile valutare la libreria con una licenza temporanea, è necessaria una licenza completa per l'uso in produzione.

**D: Ci sono limitazioni nella versione di prova?**  
R: La versione di prova può imporre restrizioni di dimensione o funzionalità; consulta la documentazione ufficiale per i dettagli.

**D: Come posso ottenere supporto per Aspose.Page?**  
R: Visita il **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** per assistenza dalla community o acquista una licenza per supporto premium.

**D: Esiste una garanzia di rimborso per Aspose.Page?**  
R: Consulta la **[pagina di acquisto](https://purchase.aspose.com/buy)** per informazioni sulle politiche di rimborso.

---

**Ultimo Aggiornamento:** 2026-01-02  
**Testato Con:** Aspose.Page Java 24.11 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}