---
date: 2026-04-30
description: Scopri come creare un documento XPS in Java e aggiungere una maschera
  di opacità usando Aspose.Page Java. Guida passo‑passo con esempi di codice.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Imposta maschera di opacità in Java XPS
second_title: Aspose.Page Java API
title: Creare documento XPS in Java – Impostare la maschera di opacità con Aspose.Page
url: /it/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta Maschera di Opacità in Java XPS usando Aspose.Page Java

## Introduzione
In questo tutorial **creerai XPS document Java** file e imparerai come applicare una maschera di opacità che conferisce ai tuoi grafici un aspetto rifinito e semi‑trasparente. Percorreremo l'intero processo — dall'inizializzazione di un documento XPS, aggiunta di una canvas, disegno di un rettangolo, fino all'applicazione di una maschera di opacità basata su immagine — usando l'intuitiva API Aspose.Page Java. Alla fine, sarai in grado di generare file XPS professionali in modo programmatico e riutilizzare la maschera su qualsiasi forma tu abbia bisogno.

## Risposte Rapide
- **Che cosa fa una maschera di opacità?** Definisce diversi livelli di trasparenza per una forma, consentendo al contenuto sottostante di trasparire.  
- **Quale libreria è necessaria?** Aspose.Page per Java (aspose page java).  
- **Ho bisogno di una licenza?** Una licenza temporanea funziona per i test; è necessaria una licenza completa per la produzione.  
- **Quante righe di codice?** Circa 20 righe di Java più alcune istruzioni di configurazione.  
- **Posso riutilizzare la maschera su più forme?** Sì, puoi assegnare lo stesso `ImageBrush` a diversi percorsi.

## Cos'è una Maschera di Opacità in XPS?
Una maschera di opacità è una bitmap o un vettore che controlla l'alpha (trasparenza) di ogni pixel in una forma. Quando viene applicata a un rettangolo, parti del rettangolo diventano completamente opache, parzialmente trasparenti o completamente trasparenti, creando effetti visivi sofisticati senza strati di disegno aggiuntivi.

## Perché usare Aspose.Page Java per **create XPS document java**?
- **Pure Java API** – Nessuna dipendenza nativa, quindi lo stesso codice funziona su Windows, Linux o macOS.  
- **Full XPS spec compliance** – Le maschere vengono renderizzate esattamente come definito dallo standard XPS.  
- **Object‑oriented design** – Simile a .NET, rendendo facile l'apprendimento se hai usato Aspose in altri linguaggi.  
- **High performance** – Ottimizzato per documenti di grandi dimensioni e elaborazione batch.

## Casi d'Uso Comuni
- **Watermarking** – Applica un logo semi‑trasparente su tutte le pagine.  
- **Dynamic theming** – Cambia lo stile visivo degli elementi UI nei report generati.  
- **Print‑ready previews** – Mostra come apparirà un design con opacità variabile prima di inviarlo alla stampante.

## Prerequisiti
Prima di iniziare, assicurati di avere:
- Una conoscenza di base della programmazione Java.  
- Libreria Aspose.Page per Java installata. Puoi scaricarla **[qui](https://releases.aspose.com/page/java/)**.  
- Una licenza valida per Aspose.Page. Se non ne possiedi una, ottieni una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)**.  
- Un ambiente di sviluppo in grado di compilare ed eseguire applicazioni Java (ad esempio, IntelliJ IDEA, Eclipse o VS Code).

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
Per prima cosa, istanzia un nuovo documento XPS che conterrà tutti i nostri grafici.

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
Carichiamo un'immagine TIFF, definiamo i rettangoli di origine e destinazione, e impostiamo il brush in modalità tile in modo che la maschera si ripeta se necessario.

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

## Problemi Comuni & Risoluzione
- **Image not found** – Verifica che `dataDir` punti alla cartella corretta e che `R08SY_NN.tif` esista.  
- **Mask appears solid** – Assicurati che l'immagine di origine contenga effettivamente valori alpha variabili; un'immagine completamente opaca non mostrerà trasparenza.  
- **Tile mode not respected** – Il rettangolo di destinazione deve essere più piccolo del rettangolo di origine affinché il tiling sia evidente.

## Domande Frequenti

**Q: Aspose.Page è compatibile con tutti gli ambienti di sviluppo Java?**  
A: Sì, Aspose.Page è progettato per funzionare senza problemi con vari IDE Java e strumenti di build.

**Q: Posso usare Aspose.Page senza licenza?**  
A: Sebbene tu possa valutare la libreria con una licenza temporanea, è necessaria una licenza completa per l'uso in produzione.

**Q: Ci sono limitazioni nella versione di prova?**  
A: La versione di prova può imporre restrizioni di dimensione o funzionalità; consulta la documentazione ufficiale per i dettagli.

**Q: Come posso ottenere supporto per Aspose.Page?**  
A: Visita il **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** per assistenza della community o acquista una licenza per supporto premium.

**Q: Esiste una garanzia di rimborso per Aspose.Page?**  
A: Consulta la **[pagina di acquisto](https://purchase.aspose.com/buy)** per informazioni sulle politiche di rimborso.

---

**Ultimo Aggiornamento:** 2026-04-30  
**Testato Con:** Aspose.Page Java 24.11 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}