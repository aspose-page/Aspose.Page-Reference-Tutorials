---
date: 2025-12-25
description: Scopri come aggiungere un gradiente ai documenti XPS in Java usando Aspose.Page
  e come personalizzare le fermate del gradiente per effetti orizzontali sorprendenti.
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
Benvenuti a questa guida passo‑passo su **come aggiungere un gradiente** a un documento XPS usando Java. In questo tutorial imparerete a inserire un gradiente orizzontale, perché è importante per la rifinitura visiva e come **personalizzare gli stop del gradiente** per un controllo preciso dei colori. Aspose.Page per Java rende il lavoro con i documenti XPS (XML Paper Specification) semplice, permettendovi di concentrarvi sul design anziché sulla gestione a basso livello del file.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page per Java  
- **Quale versione di Java funziona?** Qualsiasi runtime Java 8+  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione  
- **Posso cambiare la direzione del gradiente?** Sì – basta modificare i punti di inizio/fine del pennello lineare  
- **È possibile aggiungere più gradienti?** Assolutamente – ripetete i passaggi di creazione del percorso con pennelli diversi  

## Che cos'è un gradiente orizzontale in XPS?
Un gradiente orizzontale è una transizione fluida di colori da sinistra a destra su una forma. In XPS è rappresentato da un pennello a gradiente lineare che interpola tra gli **stop del gradiente** definiti. Questo effetto visivo è comunemente usato per banner, pulsanti e riempimenti di sfondo.

## Perché usare Aspose.Page per Java?
- **Supporto completo XPS** – crea, modifica e renderizza senza strumenti di terze parti.  
- **API semplice** – oggetti di alto livello come `XpsDocument`, `XpsPath` e `XpsGradientBrush` nascondono la complessità XML.  
- **Prestazioni** – ottimizzato per documenti di grandi dimensioni e elaborazione batch.  

## Prerequisiti
Prima di iniziare, assicuratevi di avere:

1. **Ambiente di sviluppo Java** – Installate l'ultima JDK da [java.com](https://www.java.com).  
2. **Libreria Aspose.Page per Java** – Scaricate il JAR dalla [documentazione di Aspose.Page per Java](https://reference.aspose.com/page/java/).  

## Importare i pacchetti
Iniziate importando le classi necessarie. Queste importazioni vi danno accesso alla creazione del documento, alla gestione dei gradienti e alla geometria di base.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Passo 1: Inizializzare il documento XPS
Create una nuova istanza di `XpsDocument` e specificate la cartella in cui salvare il risultato.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Passo 2: Creare un gradiente orizzontale
Definite un elenco di **stop del gradiente** che controllano il colore e la posizione di ogni punto di transizione. L'esempio qui sotto costruisce un gradiente vivace simile a un arcobaleno.

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

### Come personalizzare gli stop del gradiente
- **Colore** – Usate `doc.createColor(alpha, red, green, blue)` per impostare qualsiasi valore ARGB.  
- **Posizione** – Il secondo argomento (`float` tra `0` e `1`) definisce dove lo stop appare lungo la linea del gradiente. Regolate questi valori per spostare i colori a sinistra o a destra.

## Passo 3: Aggiungere il percorso con il gradiente
Create un percorso rettangolare, applicate una trasformazione se necessario e riempitelo con il pennello a gradiente lineare. Il pennello utilizza due punti (`(10,0)` a `(228,0)`) per produrre l'effetto orizzontale.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Consiglio professionale:** Riutilizzare lo stesso elenco `stops` per più percorsi può migliorare le prestazioni, ma ricordate di chiamare `clear()` prima di aggiungere nuovi stop.

## Passo 4: Salvare il documento
Persistete il file XPS su disco. Ora potete aprirlo con qualsiasi visualizzatore XPS per vedere il gradiente orizzontale in azione.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| Il gradiente appare solido | Nessuno stop di gradiente aggiunto o pennello non impostato | Assicuratevi che `path.setFill(...)` utilizzi un `LinearGradientBrush` e che gli stop siano aggiunti tramite `getGradientStops().addAll(stops)`. |
| I colori appaiono attenuati | Valore alpha errato (primo parametro) | Usate `255` per colori completamente opachi, a meno che non desideriate trasparenza. |
| La dimensione del percorso è errata | I valori della matrice di trasformazione sono errati | Regolate i parametri della matrice (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Domande frequenti

**D: Posso applicare più gradienti in un unico documento XPS?**  
R: Sì, potete aggiungere più percorsi, ciascuno con il proprio pennello a gradiente, per creare design stratificati complessi.

**D: Aspose.Page è compatibile con le versioni più recenti di Java?**  
R: Aspose.Page per Java è regolarmente aggiornato e funziona con Java 8 e versioni successive.

**D: Esistono altri tipi di gradiente disponibili in Aspose.Page?**  
R: Oltre ai gradienti lineari, Aspose.Page supporta anche i gradienti radiali per transizioni di colore circolari.

**D: Posso personalizzare i colori e le posizioni degli stop del gradiente?**  
R: Assolutamente! Avete il pieno controllo su ogni colore ARGB dello stop e sulla sua posizione relativa (intervallo 0‑1).

**D: Esiste un forum della community per Aspose.Page dove posso chiedere aiuto?**  
R: Sì, potete visitare il [forum di Aspose.Page](https://forum.aspose.com/c/page/39) per connettervi con la community e ricevere assistenza.

---

**Ultimo aggiornamento:** 2025-12-25  
**Testato con:** Aspose.Page per Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}