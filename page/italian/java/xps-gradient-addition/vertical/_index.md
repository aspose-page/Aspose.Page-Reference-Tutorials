---
title: Aggiungi gradiente verticale in Java XPS
linktitle: Aggiungi gradiente verticale in Java XPS
second_title: API Java Aspose.Page
description: Scopri come aggiungere un gradiente verticale ai documenti Java XPS con Aspose.Page. Migliora l'attrattiva visiva senza sforzo. Guida passo passo all'interno.
weight: 12
url: /it/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi gradiente verticale in Java XPS

## introduzione
In questo tutorial esploreremo come aggiungere un gradiente verticale in Java XPS utilizzando Aspose.Page per Java. L'aggiunta di sfumature ai tuoi documenti XPS può migliorare l'attrattiva visiva dei tuoi contenuti, rendendoli più accattivanti ed esteticamente gradevoli.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Un ambiente di sviluppo Java funzionante.
-  Aspose.Page per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/page/java/).
- Una conoscenza di base della programmazione Java.
## Importa pacchetti
Inizia importando i pacchetti necessari per il tuo progetto Java. Assicurati di aver incluso la libreria Aspose.Page per Java nelle dipendenze del tuo progetto.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
        
// Importa Aspose.Page per Java
```
## Passaggio 1: inizializzare il documento
Inizia inizializzando il documento XPS. Ciò pone le basi per l'aggiunta di elementi come tracciati e sfumature al tuo documento.
```java
// Inizializza il documento
XpsDocument doc = new XpsDocument();
```
## Passaggio 2: crea un percorso con gradiente verticale
Ora creiamo un percorso con un gradiente verticale. Ciò comporta la definizione della geometria del percorso e la specifica delle interruzioni del gradiente.
```java
// Crea un percorso con la geometria
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Definire le interruzioni del gradiente verticale
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Applica il gradiente verticale al tracciato
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Passaggio 3: salva il documento
Infine, salva il documento XPS con il gradiente verticale aggiunto nella directory desiderata.
```java
// Salva il documento
doc.save(dataDir + "VerticalGradient.xps");
```
Congratulazioni! Hai aggiunto con successo un gradiente verticale al tuo documento Java XPS utilizzando Aspose.Page.
## Conclusione
Migliorare i tuoi documenti XPS con gradienti può migliorarne significativamente l'attrattiva visiva. Aspose.Page per Java semplifica questo processo, permettendoti di creare documenti straordinari con facilità.

### Domande frequenti
### Posso utilizzare Aspose.Page per Java in progetti commerciali?
 Sì, Aspose.Page per Java è disponibile per uso commerciale. Puoi acquistarlo[Qui](https://purchase.aspose.com/buy).
### È disponibile una prova gratuita per Aspose.Page per Java?
 Sì, puoi accedere a una prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Page per Java?
 La documentazione è disponibile[Qui](https://reference.aspose.com/page/java/).
### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
 Ottieni una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Hai bisogno di aiuto o hai domande?
 Visita la comunità Aspose.Page[Forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
