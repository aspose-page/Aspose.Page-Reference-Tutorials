---
title: Aggiungi gradiente orizzontale in Java XPS
linktitle: Aggiungi gradiente orizzontale in Java XPS
second_title: API Java Aspose.Page
description: Scopri come aggiungere uno straordinario gradiente orizzontale ai documenti XPS in Java utilizzando Aspose.Page. Segui la nostra guida passo passo per un'integrazione perfetta.
type: docs
weight: 11
url: /it/java/xps-gradient-addition/horizontal/
---
## introduzione
Benvenuti in questa guida passo passo sull'aggiunta di un gradiente orizzontale in Java XPS utilizzando Aspose.Page per Java. Aspose.Page per Java è una potente libreria che consente agli sviluppatori di lavorare con documenti XPS (XML Paper Specifica) senza problemi.
In questo tutorial ti guideremo attraverso il processo di creazione di un'applicazione Java per aggiungere un gradiente orizzontale a un documento XPS. Segui i passaggi seguenti per raggiungere questo obiettivo con facilità.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
1. Ambiente di sviluppo Java: assicurati di avere Java installato sul tuo sistema. In caso contrario, scarica e installa l'ultima versione di Java da[java.com](https://www.java.com).
2.  Aspose.Page per la libreria Java: è necessario disporre della libreria Aspose.Page per Java. Puoi scaricarlo da[Aspose.Page per la documentazione Java](https://reference.aspose.com/page/java/).
## Importa pacchetti
Inizia importando i pacchetti necessari per la tua applicazione Java. Includi la libreria Aspose.Page per Java nel tuo progetto. Puoi farlo aggiungendo le seguenti righe di codice:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Passaggio 1: inizializza il documento
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
//Inizializza il documento
XpsDocument doc = new XpsDocument();
```
## Passaggio 2: crea un gradiente orizzontale
```java
// Gradiente orizzontale
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Passaggio 3: aggiungi percorso con sfumatura
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Passaggio 4: salva il documento
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Ripeti questi passaggi secondo necessità, regolando i parametri in base ai tuoi requisiti specifici.
## Conclusione
Congratulazioni! Hai aggiunto con successo un gradiente orizzontale a un documento XPS utilizzando Aspose.Page per Java. Questo tutorial ha fornito una guida completa per gli sviluppatori che desiderano migliorare le proprie applicazioni Java con effetti sfumati.
## Domande frequenti
### D: Posso applicare più sfumature in un singolo documento XPS?
Sì, puoi aggiungere più tracciati con gradienti diversi per creare disegni complessi.
### D: Aspose.Page è compatibile con le ultime versioni Java?
Aspose.Page per Java viene regolarmente aggiornato per garantire la compatibilità con le ultime versioni Java.
### D: Ci sono altri tipi di gradienti disponibili in Aspose.Page?
Sì, oltre ai gradienti lineari, Aspose.Page supporta i gradienti radiali per effetti più diversi.
### D: Posso personalizzare i colori e le posizioni delle interruzioni del gradiente?
Assolutamente! Hai il pieno controllo sui colori e sulle posizioni di ogni interruzione del gradiente.
### D: Esiste un forum della community per Aspose.Page dove posso cercare aiuto?
 Sì, puoi visitare il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per connettersi con la comunità e ottenere assistenza.