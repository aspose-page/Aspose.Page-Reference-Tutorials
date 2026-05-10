---
date: 2026-03-13
description: Scopri come aggiungere gradienti ai documenti XPS in Java usando Aspose.Page
  e come personalizzare le fermate del gradiente per effetti orizzontali mozzafiato.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Come aggiungere un gradiente – Gradiente orizzontale in Java XPS
url: /it/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un gradiente – Gradiente orizzontale in Java XPS

## Introduzione
Benvenuti a questa guida passo‑a‑passo su **come aggiungere un gradiente** a un documento XPS usando Java. In questo tutorial imparerai a inserire un gradiente orizzontale, perché è importante per una finitura visiva e come **personalizzare i gradient stop** per un controllo preciso dei colori. Aspose.Page per Java rende il lavoro con i documenti XPS (XML Paper Specification) semplice, permettendoti di concentrarti sul design anziché sulla gestione a basso livello dei file.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page per Java  
- **Quale versione di Java funziona?** Qualsiasi runtime Java 8+  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione  
- **Posso cambiare la direzione del gradiente?** Sì – basta modificare i punti di inizio/fine del pennello lineare  
- **È possibile aggiungere più gradienti?** Assolutamente – ripeti i passaggi di creazione del percorso con pennelli diversi  

## Cos'è un gradiente orizzontale in XPS?
Un gradiente orizzontale è una transizione fluida di colori da sinistra a destra su una forma. In XPS è rappresentato da un pennello gradiente lineare che interpola tra i **gradient stop** definiti. Questo effetto visivo è comunemente usato per banner, pulsanti e riempimenti di sfondo.

## Perché usare Aspose.Page per Java?
- **Supporto completo XPS** – crea, modifica e renderizza senza strumenti di terze parti.  
- **API semplice** – oggetti di alto livello come `XpsDocument`, `XpsPath` e `XpsGradientBrush` nascondono la complessità XML.  
- **Prestazioni** – ottimizzato per documenti di grandi dimensioni e elaborazione batch.  

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Ambiente di sviluppo Java** – Installa l'ultima JDK da [java.com](https://www.java.com).  
2. **Libreria Aspose.Page per Java** – Scarica il JAR dalla [documentazione Aspose.Page per Java](https://reference.aspose.com/page/java/).  

## Importa i pacchetti
Inizia importando le classi necessarie. Queste importazioni ti danno accesso alla creazione del documento, alla gestione dei gradienti e alla geometria di base.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Passo 1: Inizializza il documento XPS
Crea una nuova istanza di `XpsDocument` e indica la cartella in cui vuoi salvare il risultato.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Passo 2: Crea un gradiente orizzontale
Definisci un elenco di **gradient stop** che controllano colore e posizione di ciascun punto di transizione. L'esempio qui sotto costruisce un gradiente vivace simile a un arcobaleno.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Come personalizzare i gradient stop
- **Colore** – Usa `doc.createColor(alpha, red, green, blue)` per impostare qualsiasi valore ARGB.  
- **Posizione** – Il secondo argomento (`float` tra `0` e `1`) definisce dove appare lo stop lungo la linea del gradiente. Regola questi valori per spostare i colori a sinistra o a destra.

## Passo 3: Aggiungi un percorso con gradiente
Crea un percorso rettangolare, applica una trasformazione se necessario e riempilo con il pennello gradiente lineare. Il pennello utilizza due punti (`(10,0)` a `(228,0)`) per produrre un effetto orizzontale. Poiché le coordinate Y sono identiche, questo pennello agisce come un **pennello gradiente orizzontale**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Suggerimento professionale:** Riutilizzare lo stesso elenco `stops` per più percorsi può migliorare le prestazioni, ma ricordati di chiamare `clear()` prima di aggiungere nuovi stop.

## Passo 4: Salva il documento
Persisti il file XPS su disco. Ora puoi aprirlo con qualsiasi visualizzatore XPS per vedere il gradiente orizzontale in azione.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Come applicare più gradienti
Se desideri **applicare più gradienti** nello stesso documento XPS, ripeti semplicemente i passaggi “Crea un gradiente orizzontale” e “Aggiungi un percorso con gradiente” per ogni nuova forma. Usa un nuovo elenco di oggetti `XpsGradientStop` (o svuota l'elenco esistente) e assegna un nuovo `LinearGradientBrush` con i propri punti di inizio/fine. Questo approccio ti consente di sovrapporre gradienti, creare sfondi complessi o evidenziare diversi elementi UI in una singola pagina.

## Perché è importante – Vantaggi del pennello gradiente orizzontale
- **Profondità visiva:** Un pennello gradiente orizzontale aggiunge una sottile sensazione tridimensionale senza immagini aggiuntive.  
- **Efficienza delle dimensioni del file:** I gradienti sono memorizzati come definizioni vettoriali, mantenendo il file XPS leggero.  
- **Scalabilità:** Poiché il gradiente è basato su vettori, si scala perfettamente su display ad alta risoluzione.  

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| Il gradiente appare solido | Nessun gradient stop aggiunto o pennello non impostato | Assicurati che `path.setFill(...)` utilizzi un `LinearGradientBrush` e che i gradient stop siano aggiunti tramite `getGradientStops().addAll(stops)`. |
| I colori appaiono attenuati | Valore alpha errato (primo parametro) | Usa `255` per colori completamente opachi a meno che non sia desiderata la trasparenza. |
| La dimensione del percorso è errata | I valori della matrice di trasformazione sono errati | Regola i parametri della matrice (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Domande frequenti

**D: Posso applicare più gradienti in un singolo documento XPS?**  
R: Sì, puoi aggiungere più percorsi, ciascuno con il proprio pennello gradiente, per creare design a strati complessi.

**D: Aspose.Page è compatibile con le ultime versioni di Java?**  
R: Aspose.Page per Java è aggiornato regolarmente e funziona con Java 8 e versioni successive.

**D: Ci sono altri tipi di gradiente disponibili in Aspose.Page?**  
R: Oltre ai gradienti lineari, Aspose.Page supporta anche i gradienti radiali per transizioni di colore circolari.

**D: Posso personalizzare i colori e le posizioni dei gradient stop?**  
R: Assolutamente! Hai il pieno controllo su ogni colore ARGB del stop e sulla sua posizione relativa (intervallo 0‑1).

**D: Esiste un forum della community per Aspose.Page dove posso chiedere aiuto?**  
R: Sì, puoi visitare il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per connetterti con la community e ottenere assistenza.

---

**Ultimo aggiornamento:** 2026-03-13  
**Testato con:** Aspose.Page per Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}