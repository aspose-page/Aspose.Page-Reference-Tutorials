---
date: 2026-04-24
description: Scopri come creare un documento XPS in Java con un'ellisse a gradiente
  radiale. Questa guida passo passo mostra come impostare lo spessore del tratto e
  definire la geometria del percorso usando Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Aggiungi ellisse in Java XPS
second_title: Aspose.Page Java API
title: Crea documento XPS Java – Aggiungi ellisse con gradiente radiale
url: /it/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi ellisse con gradiente radiale con Aspose.Page

## Introduzione
In questo tutorial, imparerai a **create XPS document Java** con una splendida ellisse contornata da un gradiente radiale usando Aspose.Page per Java. Aspose.Page è una libreria robusta che astrae i dettagli a basso livello di XPS, permettendoti di concentrarti sul design piuttosto che sulle complessità del formato file. Alla fine di questa guida avrai un file XPS pronto all'uso che potrai incorporare in report, fatture o in qualsiasi flusso di lavoro di generazione di documenti.

## Risposte rapide
- **What does this code produce?** Un file XPS a pagina singola contenente un'ellisse contornata da un gradiente radiale multicolore.  
- **Which primary API is used?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, ecc.).  
- **Do I need a license to run the sample?** Una licenza temporanea funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **What are the key properties we set?** Pennello di contorno (gradiente radiale), metodo di diffusione, fermate del gradiente e spessore del contorno.  
- **Can I change the ellipse size?** Sì – modifica la stringa della geometria del percorso o le coordinate del pennello del gradiente.

## Cos'è “create XPS document Java”?
Creare un documento XPS in Java significa generare programmaticamente un file XML Paper Specification (XPS) — un formato di documento a layout fisso simile a PDF — direttamente dal codice Java. Aspose.Page fornisce un modello di oggetti di alto livello (`XpsDocument`, `XpsCanvas`, ecc.) che astrae il markup XML, rendendo il processo semplice come lavorare con oggetti Java standard.

## Perché usare un'ellisse con gradiente radiale?
Un gradiente radiale conferisce una sensazione tridimensionale, perfetta per evidenziare visualmente, loghi o elementi decorativi nei report. Rispetto a un contorno a tinta unita, il gradiente aggiunge profondità senza aumentare significativamente la dimensione del file, e il formato XPS preserva la qualità vettoriale per qualsiasi ridimensionamento.

## Prerequisiti
- Java Development Kit (JDK) installato sulla tua macchina.
- Libreria Aspose.Page per Java scaricata. Puoi ottenerla [qui](https://releases.aspose.com/page/java/).
- Un editor di codice a tua scelta (Eclipse, IntelliJ, ecc.) per scrivere ed eseguire il codice Java.

## Importa pacchetti
Assicurati di aver importato i pacchetti necessari nel tuo progetto Java per utilizzare Aspose.Page. Aggiungi le seguenti istruzioni di importazione all'inizio del tuo file Java:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Passo 1: Configura la directory del documento
Definisci il percorso della tua directory dei documenti dove verrà salvato il documento XPS:

```java
String dataDir = "Your Document Directory";
```

## Passo 2: Crea documento XPS
Inizializza un nuovo documento XPS usando il seguente codice:

```java
XpsDocument doc = new XpsDocument();
```

## Passo 3: Definisci le fermate del gradiente radiale
Crea un elenco di fermate del gradiente per l'ellisse contornata da un gradiente radiale:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Passo 4: Crea la geometria del percorso
Definisci un'ellisse contornata da un gradiente radiale usando la geometria del percorso:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Passo 5: Aggiungi canvas e percorso
Aggiungi un nuovo canvas al documento e aggiungi il percorso con la geometria definita:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Passo 6: Imposta contorno e gradiente
Configura il contorno del percorso con un pennello a gradiente radiale:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Passo 7: Imposta spessore del contorno
Specifica lo **spessore del contorno** del percorso:

```java
path.setStrokeThickness(12f);
```

## Passo 8: Salva il documento
Salva il documento XPS risultante:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Congratulazioni! Hai aggiunto con successo un'ellisse contornata da un gradiente radiale mentre **crei un documento XPS Java** con Aspose.Page.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **Ellipse appears flat** | Uso di `XpsSpreadMethod.Pad` invece di `Reflect` | Cambia il metodo di diffusione in `XpsSpreadMethod.Reflect` come mostrato al Passo 6. |
| **No output file** | `dataDir` punta a una cartella inesistente | Assicurati che la directory esista o usa un percorso assoluto. |
| **Gradient colors look off** | Ordine errato delle fermate del gradiente | Verifica che i valori `offset` (0 → 1) aumentino monotonicamente. |
| **Compilation errors** | JAR di Aspose.Page mancanti nel classpath | Aggiungi `aspose-page-xx.jar` alle dipendenze del tuo progetto. |

## Domande frequenti

**Q: Posso usare Aspose.Page per Java con altre librerie Java?**  
A: Sì, Aspose.Page per Java può essere integrato con altre librerie Java senza problemi.

**Q: Aspose.Page è adatto per l'elaborazione di documenti su larga scala?**  
A: Assolutamente! Aspose.Page è progettato per gestire efficientemente l'elaborazione di documenti su larga scala.

**Q: Dove posso trovare più tutorial ed esempi per Aspose.Page per Java?**  
A: Visita la [documentazione di Aspose.Page per Java](https://reference.aspose.com/page/java/) per tutorial ed esempi completi.

**Q: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
A: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**Q: Esistono forum della community per le discussioni su Aspose.Page?**  
A: Sì, unisciti al [forum della community di Aspose.Page](https://forum.aspose.com/c/page/39) per interagire con altri sviluppatori e ottenere assistenza.

---

**Ultimo aggiornamento:** 2026-04-24  
**Testato con:** Aspose.Page per Java 24.11 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}