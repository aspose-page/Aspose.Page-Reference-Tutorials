---
date: 2026-05-25
description: Impara come aggiungere gradient ai documenti XPS in Java usando Aspose.Page.
  Questa guida passo‑passo mostra come aggiungere un diagonal gradient, applicare
  linear gradient brushes e produrre file XPS professionali.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Aggiungi Diagonal Gradient in Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Come aggiungere Gradient: Diagonal Gradient in Java XPS'
url: /it/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un gradiente: gradiente diagonale in Java XPS

## Introduzione

Nello sviluppo Java moderno, padroneggiare **come aggiungere un gradiente** ai documenti XPS conferisce ai tuoi report un aspetto rifinito e accattivante che si distingue. Questo tutorial ti guida nella creazione di un file XPS da zero, nell'aggiunta di un gradiente diagonale e nel salvataggio del risultato—tutto con Aspose.Page per Java. Capirai perché i gradienti sono importanti, vedrai le chiamate API esatte e otterrai consigli pratici per evitare errori comuni.

## Risposte rapide
- **Qual è la libreria principale?** Aspose.Page for Java  
- **Quale metodo aggiunge il gradiente?** `createLinearGradientBrush` con gradient stops  
- **Ho bisogno di una licenza?** Una versione di prova funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un gradiente diagonale di base  
- **Posso usarlo con altri framework Java?** Sì, l'API è indipendente dal framework  

## Cos'è un gradiente diagonale in un documento XPS?
Un gradiente diagonale è una transizione di colore fluida che va da un angolo di una forma all'angolo opposto, creando un effetto visivo inclinato. In XPS, questo effetto è definito da un linear gradient brush contenente gradient stops ordinati che specificano i colori e le posizioni relative lungo la linea diagonale.

## Perché aggiungere un gradiente diagonale con Aspose.Page?
Aspose.Page offre **100 % di fedeltà di rendering** per i gradienti su più di 20 visualizzatori XPS, e supporta **30+ funzionalità XPS** come testo, immagini e forme vettoriali. L'API astrae il markup XPS complesso, permettendoti di concentrarti sul design garantendo che lo stesso file abbia un aspetto identico su piattaforme Windows, macOS e Linux.

## Prerequisiti
- Conoscenze di base di programmazione Java.  
- JDK installato sulla tua macchina.  
- Libreria Aspose.Page per Java – scaricala **[qui](https://releases.aspose.com/page/java/)**.  
- Un IDE come IntelliJ IDEA o Eclipse.

## Importa pacchetti
Inizia importando le classi di cui avrai bisogno. Queste importazioni ti danno accesso a geometria, gestione dei gradienti e creazione di documenti XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Passo 1: Configura il tuo progetto
Crea un nuovo progetto Java nel tuo IDE preferito e aggiungi i file JAR di Aspose.Page al percorso di compilazione del progetto.

## Passo 2: Definisci la directory del documento
Specifica dove verrà salvato il file XPS generato.

```java
String dataDir = "Your Document Directory";
```

## Passo 3: Crea il documento XPS
`XpsDocument` è l'oggetto principale che rappresenta un file XPS in memoria. Istanziandolo ottieni una tela su cui aggiungere pagine, forme e pennelli.

```java
XpsDocument doc = new XpsDocument();
```

## Passo 4: Aggiungi il percorso del gradiente diagonale
Crea un percorso rettangolare che riceverà il gradiente. La geometria del percorso utilizza un semplice comando move‑line‑close.  
XpsPath definisce una forma vettoriale nel documento XPS, come un rettangolo o una geometria personalizzata.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Passo 5: Definisci i gradient stop lineari
Imposta i colori e le loro posizioni. Ogni stop definisce un punto nel gradiente dove appare un colore specifico.  
XpsGradientStop rappresenta un singolo stop di colore in un gradiente, specificando un colore e il suo offset.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Passo 6: Applica il gradiente lineare al percorso
`XpsLinearGradientBrush` è il tipo di pennello di Aspose.Page per transizioni di colore lineari. Accetta due punti che definiscono la direzione del gradiente e una collezione di gradient stop che determinano i colori lungo quella linea.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Passo 7: Salva il documento
Salva il file XPS su disco. Il file conterrà il rettangolo riempito con il gradiente diagonale che hai definito.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Come aggiungere un gradiente in Java XPS?
Carica lo XpsDocument, crea un `XpsLinearGradientBrush` con punto di partenza `(0,0)` e punto finale `(width,height)`, aggiungi i gradient stop, assegna il pennello alla proprietà `Fill` di una forma e infine chiama `save`. Questo flusso conciso ti consente di incorporare un gradiente diagonale con poche chiamate API, mantenendo il codice pulito e manutenibile.

## Problemi comuni e consigli
- **Direzione del gradiente** – assicurati che i punti di inizio e fine del pennello riflettano la diagonale desiderata; scambiarli inverte il gradiente.  
- **Precisione del colore** – Aspose utilizza ARGB; includi il canale alfa se hai bisogno di trasparenza.  
- **Percorso del file** – usa sempre un percorso assoluto o verifica che il percorso relativo punti a una directory esistente e scrivibile.

## FAQ aggiuntive

**Q: Come aggiungere un gradiente a una forma XPS esistente?**  
A: Crea un `XpsLinearGradientBrush`, definisci i gradient stop e assegnalo alla proprietà `Fill` della forma come mostrato al Passo 6.

**Q: Cosa fa realmente **apply linear gradient** dietro le quinte?**  
A: Genera una definizione di pennello nel pacchetto XPS che fa riferimento ai punti di inizio/fine e a una collezione di gradient stop, che il visualizzatore rende come una transizione di colore fluida.

**Q: Esiste un modo rapido per **how to use aspose** per altre funzionalità XPS?**  
A: Sì, l'API Aspose.Page include metodi per aggiungere immagini, testo e forme personalizzate—basta esplorare la classe `XpsDocument` per ulteriori helper.

**Q: Posso **add gradient path** a forme non rettangolari?**  
A: Assolutamente. Definisci qualsiasi geometria usando `createPathGeometry` e poi imposta il suo `Fill` a un pennello gradiente.

**Q: Il gradiente influisce significativamente sulla dimensione del file?**  
A: Solo marginalmente; le definizioni dei gradienti sono voci XML leggere all'interno del pacchetto XPS.

---

**Ultimo aggiornamento:** 2026-05-25  
**Testato con:** Aspose.Page for Java 24.11  
**Autore:** Aspose

## Tutorial correlati

- [Aggiunta di gradiente XPS con Aspose Page](/page/java/xps-gradient-addition/)
- [Aggiunta di testo XPS in Java - Tutorial Aspose.Page](/page/java/xps-text-manipulation/add-text/)
- [Come aggiungere un'immagine ai documenti XPS Java – Guida semplice con Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}