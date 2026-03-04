---
date: 2025-12-25
description: Scopri come aggiungere un gradiente verticale in Java XPS usando Aspose.Page.
  Segui questa guida passo passo per migliorare l'aspetto visivo del tuo documento.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Come aggiungere un gradiente verticale in Java XPS
url: /it/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un gradiente verticale in Java XPS

## Introduzione
In questo tutorial scoprirai **come aggiungere un gradiente verticale** ai documenti XPS quando lavori con Java. Applicare un gradiente verticale può migliorare notevolmente l'impatto visivo dei tuoi report, fatture o qualsiasi contenuto stampabile. Ti guideremo passo passo, dalla configurazione del progetto al salvataggio del file XPS finale, utilizzando la potente libreria Aspose.Page for Java.

## Risposte rapide
- **Che cosa fa un gradiente verticale?** Crea una transizione di colore fluida dall'alto al basso di una forma.  
- **Quale libreria è necessaria?** Aspose.Page for Java (scaricabile dal sito ufficiale).  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **È compatibile con Java 8+?** Sì, l'API supporta Java 8 e versioni successive.  
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti una volta che l'ambiente è configurato.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere quanto segue:

- Un ambiente di sviluppo Java funzionante (JDK 8 o più recente).  
- Libreria Aspose.Page for Java. Puoi scaricarla da [qui](https://releases.aspose.com/page/java/).  
- Una comprensione di base dei concetti di programmazione Java.  

## Importa i pacchetti
Inizia importando i pacchetti necessari per il tuo progetto Java. Assicurati che la libreria Aspose.Page for Java sia aggiunta al classpath del tuo progetto.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## Passo 1: Inizializza il documento
Inizia creando un nuovo documento XPS. Questo oggetto conterrà tutti gli elementi di disegno che aggiungerai in seguito.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## Passo 2: Crea un percorso con un gradiente verticale
Successivamente, definisci un percorso rettangolare e applica un gradiente lineare verticale. Le fermate del gradiente determinano i colori e le loro posizioni lungo l'asse verticale.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Passo 3: Salva il documento
Infine, scrivi il file XPS su disco. Il file risultante conterrà il rettangolo riempito con il gradiente verticale che hai definito.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Congratulazioni! Hai appreso con successo **come aggiungere un gradiente verticale** a un documento Java XPS utilizzando Aspose.Page.

## Perché usare un gradiente verticale?
- **Estetica migliorata:** I gradienti aggiungono profondità e un aspetto moderno alle forme statiche.  
- **Coerenza del brand:** Abbina i colori aziendali in modo fluido tra le pagine.  
- **Facile personalizzazione:** Cambia i colori o le posizioni delle fermate senza ridisegnare le grafiche.

## Problemi comuni e risoluzione
- **Gradiente non visibile:** Verifica che i punti di inizio e fine del `LinearGradientBrush` siano impostati correttamente per un'orientazione verticale.  
- **File non salvato:** Assicurati che `dataDir` punti a una cartella scrivibile e che tu abbia i permessi per scrivere i file.  
- **Libreria non trovata:** Controlla che il JAR di Aspose.Page sia incluso nel percorso di compilazione del tuo progetto.

## Domande frequenti

**D: Posso usare Aspose.Page for Java in progetti commerciali?**  
R: Sì, Aspose.Page for Java è disponibile per uso commerciale. Puoi acquistarlo [qui](https://purchase.aspose.com/buy).

**D: È disponibile una versione di prova gratuita per Aspose.Page for Java?**  
R: Sì, puoi accedere a una prova gratuita [qui](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione per Aspose.Page for Java?**  
R: La documentazione è disponibile [qui](https://reference.aspose.com/page/java/).

**D: Come posso ottenere una licenza temporanea per Aspose.Page for Java?**  
R: Ottieni una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Hai bisogno di aiuto o hai domande?**  
R: Visita il [forum](https://forum.aspose.com/c/page/39) della community Aspose.Page.

---

**Ultimo aggiornamento:** 2025-12-25  
**Testato con:** Aspose.Page for Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}