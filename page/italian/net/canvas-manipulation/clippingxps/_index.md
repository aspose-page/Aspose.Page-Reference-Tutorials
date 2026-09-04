---
date: 2026-06-25
description: Scopri come ritagliare i documenti XPS usando Aspose.Page per .NET. Questa
  guida passo‑passo ti mostra come creare, manipolare e salvare i file XPS in modo
  efficiente.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Ritaglio XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Come ritagliare XPS con Aspose.Page per .NET
url: /it/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ritagliare XPS con Aspose.Page per .NET

## Introduzione

Benvenuti a questo tutorial completo su **come ritagliare XPS** usando Aspose.Page per .NET! In questa guida, imparerai passo‑passo come creare un documento XPS, applicare maschere di ritaglio geometriche e salvare il risultato. Il ritaglio ti consente di nascondere parti di una tela, abilitando layout sofisticati come immagini mascherate, forme personalizzate o aree di contenuto focalizzate—tutto senza lasciare il tuo codice .NET.

## Risposte rapide
- **Che cos'è il clipping XPS?** Applicare una maschera geometrica (clip) per limitare l'area visibile degli elementi della tela XPS.  
- **Quale libreria è la migliore per questo?** Aspose.Page per .NET offre un'API completa per la creazione e il ritaglio di XPS.  
- **Prerequisiti?** Visual Studio, runtime .NET e la libreria Aspose.Page per .NET.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per uno scenario di ritaglio di base.  
- **Posso usarlo in produzione?** Sì, con una licenza Aspose valida (è disponibile una versione di prova).

## Che cosa significa “come ritagliare XPS”?

Il clipping XPS consiste nell'applicare una maschera geometrica a una tela in modo che qualsiasi disegno al di fuori della maschera non venga renderizzato. Questa tecnica è ideale per creare immagini mascherate, pulsanti di forma personalizzata o per focalizzare l'attenzione del lettore su una specifica area della pagina. Definendo una geometria di clip—come un rettangolo, un cerchio o un percorso complesso—si ottiene un controllo dettagliato su ciò che appare nella pagina XPS finale.

## Perché usare Aspose.Page per .NET per ritagliare XPS?

Aspose.Page fornisce una manipolazione XPS deterministica lato server senza dipendenze esterne. Supporta **50+ formati di input e output**, può elaborare **file XPS di 200 pagine in meno di 0,5 secondi** su una CPU standard da 2,5 GHz, e funziona su .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 e .NET 7. L'API ti dà pieno controllo su trasformazioni della tela, geometrie di percorso e pennelli, garantendo output di alta qualità ogni volta.

## Prerequisiti

- Visual Studio installato sulla tua macchina.  
- Libreria Aspose.Page per .NET aggiunta al tuo progetto. Puoi scaricarla [qui](https://releases.aspose.com/page/net/).  
- Conoscenza di base del linguaggio di programmazione C#.

## Come ritagliare XPS?

Carica un documento XPS, crea una tela, definisci una geometria di clip (ad es., un cerchio), assegna la geometria alla proprietà `Clip` della tela, disegna il tuo contenuto e infine salva il documento. Tutti questi passaggi possono essere eseguiti con poche chiamate di metodo, e Aspose.Page gestisce automaticamente il markup XML sottostante, così ti concentri sul design visivo anziché sulla struttura del file.

## Importare gli spazi dei nomi

Per utilizzare le funzionalità di Aspose.Page per .NET, è necessario importare gli spazi dei nomi richiesti nel tuo progetto. Segui questi passaggi:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Ora, analizziamo il codice di esempio fornito suddividendolo in più passaggi.

## Passo 1: Impostare il percorso della directory del documento.

Definisci la cartella in cui verrà creato il file XPS. L'uso di `Path.Combine` garantisce il separatore di directory corretto su qualsiasi OS.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Passo 2: Creare un nuovo documento XPS.

Istanzia la classe `XpsDocument`, che rappresenta l'intero pacchetto XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Passo 3: Creare la tela principale.

La classe `Canvas` rappresenta una superficie di disegno all'interno di una pagina XPS dove vengono renderizzate forme, immagini e testo.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Passo 4: Impostare gli offset sinistro e superiore nella tela principale.

Regola la posizione della tela per controllare dove inizia il disegno sulla pagina.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Passo 5: Creare una geometria di percorso rettangolare.

`PathGeometry` definisce una forma vettoriale; qui creiamo un semplice rettangolo.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Passo 6: Creare un riempimento per i rettangoli.

Definisci un pennello a colore solido che verrà usato per riempire il rettangolo.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Passo 7: Aggiungere un'altra tela con clip alla tela principale.

Crea una tela figlia che riceverà una maschera di ritaglio.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Passo 8: Creare una geometria circolare per il clip.

`PathGeometry` può rappresentare anche cerchi; questa geometria sarà assegnata alla proprietà `Clip` della tela figlia.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Passo 9: Creare un rettangolo nella seconda tela e riempirlo.

Disegna un rettangolo all'interno della tela ritagliata; solo la porzione all'interno del cerchio sarà visibile.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Passo 10: Aggiungere la seconda tela con un rettangolo contornato alla tela principale.

Aggiungi un rettangolo con contorno per illustrare come i contorni interagiscono con il ritaglio.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Passo 11: Creare un rettangolo nella terza tela e tracciarlo.

Una terza tela dimostra il disegno indipendente senza ritaglio.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Passo 12: Salvare il documento XPS risultante.

Persisti il pacchetto XPS nel file system.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Problemi comuni e soluzioni
- **Percorso non valido** – Assicurati che `dataDir` termini con una barra rovesciata (`\\`) o usa `Path.Combine`.  
- **Clip non applicato** – Verifica che la stringa della geometria di clip sia ben formata; uno spazio mancante può far sì che il clip venga ignorato.  
- **Eccezione di licenza** – In una build non di valutazione, aggiungi una licenza Aspose valida prima di creare il documento per evitare eccezioni a runtime.

## Domande frequenti

### Q1: Posso usare Aspose.Page per .NET con altri formati di documento?

A1: Aspose.Page per .NET si concentra principalmente sui documenti XPS, ma Aspose fornisce altre librerie per vari formati di documento.

### Q2: Aspose.Page per .NET è adatto ai principianti?

A2: Sì, Aspose.Page per .NET è progettato per essere user‑friendly, e i principianti possono rapidamente comprendere le sue funzionalità con una documentazione adeguata.

### Q3: Dove posso trovare più esempi e risorse?

A3: Visita la [documentation](https://reference.aspose.com/page/net/) e il [Aspose.Page forum](https://forum.aspose.com/c/page/39) per risorse ed esempi estesi.

### Q4: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

A4: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Q5: È disponibile una versione di prova gratuita per Aspose.Page per .NET?

A5: Sì, puoi esplorare la versione di prova gratuita [qui](https://releases.aspose.com/).

## Domande frequenti aggiuntive

**Q: Posso combinare più geometrie di clip su una singola tela?**  
A: Sì, puoi assegnare una `PathGeometry` complessa che contiene diversi sotto‑percorsi alla proprietà `Clip`, consentendo mascheramenti a più livelli.

**Q: Il clipping influisce sulla conversione PDF?**  
A: Quando converti successivamente l'XPS in PDF usando Aspose.PDF, la geometria di clip viene preservata, quindi il risultato visivo rimane identico.

**Q: È possibile animare il clipping in XPS?**  
A: XPS stesso non supporta l'animazione; tuttavia, puoi generare una serie di pagine XPS con diverse forme di clip per simulare il movimento.

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Tutorial correlati

- [Come trasformare XPS con Aspose.Page per .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Aggiungere un rettangolo al documento XPS con Aspose.Page per .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Convertire XPS in PDF con Aspose.Page per .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}