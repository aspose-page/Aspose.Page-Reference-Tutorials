---
date: 2026-04-03
description: Scopri come aggiungere un rettangolo trasparente e applicare un Grid
  Visual Brush in .NET usando Aspose.Page per creare documenti XPS sorprendenti.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Applica pennello visivo della griglia
second_title: Aspose.Page .NET API
title: Aggiungi rettangolo trasparente usando Grid Visual Brush (.NET)
url: /it/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi Rettangolo Trasparente usando Grid Visual Brush (.NET)

## Introduzione

Se stai cercando di **aggiungere un rettangolo trasparente** a un documento XPS applicando anche un elegante Grid Visual Brush, sei nel posto giusto. In questo tutorial percorreremo passo passo le operazioni necessarie con Aspose.Page per .NET, così potrai creare documenti visivamente ricchi che si distinguono. Alla fine avrai un esempio completo e funzionante che dimostra entrambe le tecniche in un unico flusso di lavoro facile da seguire.

## Risposte Rapide
- **Che cosa fa un rettangolo trasparente?** Aggiunge una sovrapposizione semi‑opaca che consente al contenuto di sfondo di mostrarsi.  
- **Quale API crea il brush?** `XpsDocument.CreateVisualBrush` crea il Grid Visual Brush.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per i test; è necessaria una licenza commerciale per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio base.

## Cos'è un Rettangolo Trasparente in XPS?
Un rettangolo trasparente è semplicemente una forma il cui colore di riempimento include un componente alfa inferiore a 1.0, consentendo ai grafici sottostanti di essere parzialmente visibili. È perfetto per evidenziare sezioni senza oscurare completamente lo sfondo.

## Perché usare un Grid Visual Brush?
Un Grid Visual Brush ti consente di tassellare un piccolo grafico vettoriale su un'area più ampia, creando motivi come griglie, tratteggi o texture personalizzate. Combinarlo con un rettangolo trasparente ti offre effetti visivi a strati leggeri e indipendenti dalla risoluzione.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

- **Aspose.Page per .NET** – è possibile scaricarlo [qui](https://releases.aspose.com/page/net/).
- Un ambiente di sviluppo .NET (Visual Studio, VS Code o qualsiasi IDE preferito).
- Una cartella dove verranno salvati i file XPS generati.

## Importa Namespace

Nel tuo file C#, importa i namespace richiesti:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ora suddividiamo la soluzione in passaggi chiari e numerati.

## Passo 1: Inizializza XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Iniziamo creando un'istanza di `XpsDocument`, che conterrà tutte le operazioni di disegno successive.

## Passo 2: Crea la Geometria della Griglia Magenta

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Questa geometria definisce il contorno della griglia che il visual brush riempirà.

## Passo 3: Progetta il VisualBrush della Griglia Magenta

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Qui disegniamo una piccola tessera magenta che verrà ripetuta sulla griglia.

## Passo 4: Applica VisualBrush alla Griglia

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

La chiamata `CreateVisualBrush` collega la tessera magenta alla geometria della griglia e abilita il tiling.

## Passo 5: Aggiungi la Griglia al Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Posizioniamo la griglia tassellata su un canvas e applichiamo una trasformazione di traslazione affinché appaia nella posizione desiderata.

## Passo 6: Aggiungi Rettangolo Trasparente

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

In questo passo **aggiungiamo un rettangolo trasparente** (la forma rossa con `Opacity = 0.7f`). Regola il valore di opacità per controllare quanto il rettangolo sia trasparente.

## Passo 7: Salva il Documento

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Il file XPS viene scritto nella cartella specificata in precedenza.

## Casi d'Uso Comuni

- **Evidenziazione di Report:** Sovrapponi un rettangolo semi‑trasparente per enfatizzare un grafico o una tabella.  
- **Effetti di Filigrana:** Combina una griglia tassellata con una sovrapposizione trasparente per un branding discreto.  
- **PDF/XPS Interattivi:** Usa il pattern come sfondo per i campi del modulo mantenendo l'interfaccia leggibile.

## Suggerimenti per la Risoluzione dei Problemi

- **Opacità non visibile?** Assicurati che il visualizzatore supporti la trasparenza XPS; alcuni visualizzatori più vecchi potrebbero ignorare la proprietà `Opacity`.  
- **Dimensione della tessera errata?** Verifica che il rettangolo sorgente (`new RectangleF(0f, 0f, 10f, 10f)`) corrisponda alle dimensioni della tessera vettoriale.  
- **File non salvato?** Controlla che `dataDir` punti a una directory esistente e scrivibile.

## Domande Frequenti

**D: Posso usare Aspose.Page per .NET sia in applicazioni web che desktop?**  
R: Sì, la libreria funziona su tutti i tipi di applicazioni .NET.

**D: È disponibile una versione di prova prima dell'acquisto?**  
R: Assolutamente, puoi accedere alla prova gratuita [qui](https://releases.aspose.com/).

**D: Dove posso trovare supporto aggiuntivo o discussioni della community?**  
R: Visita il [Forum Aspose.Page](https://forum.aspose.com/c/page/39) per ricevere aiuto dalla community e dagli ingegneri Aspose.

**D: Come posso ottenere una licenza temporanea per la valutazione?**  
R: Puoi acquisire una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Quale altra documentazione è disponibile per Aspose.Page per .NET?**  
R: Esplora la documentazione completa [qui](https://reference.aspose.com/page/net/).

---

**Ultimo Aggiornamento:** 2026-04-03  
**Testato Con:** Aspose.Page 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}