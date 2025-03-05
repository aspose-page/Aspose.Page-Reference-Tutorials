---
title: Aggiungi ellisse gradiente radiale con Aspose.Page
linktitle: Aggiungi Ellisse in Java XPS
second_title: API Java Aspose.Page
description: Esplora la guida passo passo sull'aggiunta di un'ellisse con gradiente radiale in Java XPS utilizzando Aspose.Page per Java. Migliora la creazione dei tuoi documenti senza sforzo.
type: docs
weight: 10
url: /it/java/xps-shapes/add-ellipse/
---
## introduzione
Benvenuti nella nostra guida passo passo sull'aggiunta di un'ellisse in Java XPS utilizzando Aspose.Page per Java. Aspose.Page è una potente libreria Java che consente agli sviluppatori di lavorare con documenti XPS senza sforzo. In questo tutorial, ti guideremo attraverso il processo di creazione di un'ellisse con tratto a gradiente radiale e di salvataggio come documento XPS.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo computer.
-  Aspose.Page per la libreria Java scaricata. Puoi prenderlo[Qui](https://releases.aspose.com/page/java/).
- Un editor di codice a tua scelta (Eclipse, IntelliJ, ecc.) per scrivere ed eseguire codice Java.
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
## Passaggio 1: impostare la directory dei documenti
Definisci il percorso della directory dei documenti in cui verrà salvato il documento XPS:
```java
String dataDir = "Your Document Directory";
```
## Passaggio 2: crea un documento XPS
Inizializza un nuovo documento XPS utilizzando il seguente codice:
```java
XpsDocument doc = new XpsDocument();
```
## Passaggio 3: definire le interruzioni del gradiente radiale
Crea un elenco di interruzioni della sfumatura per l'ellisse tracciata con sfumatura radiale:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Passaggio 4: crea la geometria del percorso
Definire un'ellisse tratteggiata con gradiente radiale utilizzando la geometria del percorso:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Passaggio 5: aggiungi tela e percorso
Aggiungi una nuova tela al documento e aggiungi il percorso con la geometria definita:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Passaggio 6: imposta tratto e sfumatura
Configura il tratto del tracciato con un pennello a gradiente radiale:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Passaggio 7: impostare lo spessore del tratto
Specificare lo spessore del tratto del tracciato:
```java
path.setStrokeThickness(12f);
```
## Passaggio 8: salva il documento
Salva il documento XPS risultante:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Congratulazioni! Hai aggiunto con successo un'ellisse con gradiente radiale in Java XPS utilizzando Aspose.Page per Java.
## Conclusione
In questo tutorial, abbiamo esplorato i passaggi per creare un documento XPS con un'ellisse con gradiente radiale visivamente accattivante. Aspose.Page per Java semplifica la manipolazione dei documenti XPS, fornendo agli sviluppatori un potente set di strumenti.
## Domande frequenti
### Posso utilizzare Aspose.Page per Java con altre librerie Java?
Sì, Aspose.Page per Java può essere integrato perfettamente con altre librerie Java.
### Aspose.Page è adatto per l'elaborazione di documenti su larga scala?
Assolutamente! Aspose.Page è progettato per gestire in modo efficiente l'elaborazione di documenti su larga scala.
### Dove posso trovare altri tutorial ed esempi per Aspose.Page per Java?
 Visitare il[Aspose.Page per la documentazione Java](https://reference.aspose.com/page/java/)per tutorial ed esempi completi.
### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Esistono forum della community per le discussioni su Aspose.Page?
 Sì, unisciti a[Forum della comunità Aspose.Page](https://forum.aspose.com/c/page/39) per interagire con altri sviluppatori e ottenere assistenza.