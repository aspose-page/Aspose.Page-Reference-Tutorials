---
date: 2026-01-05
description: Scopri come trasformare i documenti XPS senza sforzo con Aspose.Page
  per .NET. Segui la nostra guida passo‑passo per trasformazioni fluide.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Come trasformare XPS con Aspose.Page per .NET
url: /it/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come trasformare XPS con Aspose.Page per .NET

## Introduzione

Benvenuti nel mondo di Aspose.Page per .NET, una potente libreria che consente di eseguire varie trasformazioni sui documenti XPS senza sforzo. **In questo tutorial scoprirete come trasformare i documenti XPS usando Aspose.Page per .NET**, sia che siate sviluppatori esperti o alle prime armi. Vi guideremo passo dopo passo, spiegheremo il motivo di ogni trasformazione e vi forniremo consigli pratici da applicare nei progetti reali.

## Risposte rapide
- **Cosa è possibile ottenere?** Creare, traslare, scalare e ruotare gli elementi della tela XPS programmaticamente.  
- **Quale libreria è necessaria?** Aspose.Page per .NET (ultima versione).  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Piattaforme supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per le trasformazioni di base mostrate qui.

## Cos'è “how to transform xps”?
L'espressione *how to transform xps* si riferisce alla modifica programmatica del layout, delle dimensioni e dell'orientamento degli elementi all'interno di un documento XPS (XML Paper Specification). Con Aspose.Page è possibile applicare trasformazioni basate su matrici alle tele, ottenendo un controllo dettagliato su posizionamento, scala e rotazione senza dover modificare manualmente l'XML di XPS.

## Perché usare Aspose.Page per le trasformazioni XPS?
- **Integrazione completa con .NET** – funziona senza problemi con Visual Studio, Rider e altri IDE.  
- **Nessuna dipendenza esterna** – l'API gestisce tutti i dettagli di basso livello di XPS per voi.  
- **Supporto ricco alle trasformazioni** – traslare, scalare, ruotare e combinare più trasformazioni in una singola chiamata.  
- **Ottimizzata per le prestazioni** – adatta alla generazione di report, fatture o qualsiasi grafica stampabile al volo.

## Prerequisiti

Prima di iniziare, assicuratevi di avere:

- **Libreria Aspose.Page per .NET** – scaricatela e installatela dalla documentazione ufficiale: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Ambiente di sviluppo** – Visual Studio, Visual Studio Code o qualsiasi altro IDE compatibile con .NET.  
- **Cartella dei documenti** – una directory sul vostro computer dove leggere/scrivere i file XPS. Sostituite il segnaposto nel codice con il percorso reale.

Ora che tutto è pronto, immergiamoci nel codice.

## Importare i namespace

Per prima cosa, importate i namespace che espongono le classi Aspose.Page necessarie:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Come trasformare XPS – Guida passo‑per‑passo

### Passo 1: Creare un nuovo documento XPS

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Spiegazione*: Definiamo la cartella che contiene i file di origine e di output, quindi istanziamo un `XpsDocument` vuoto. Questo oggetto sarà la tela per tutte le trasformazioni successive.

### Passo 2: Creare una tela principale

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Perché è importante*: La tela principale funge da contenitore per tutte le altre tele. Applicando un piccolo offset garantiamo che il contenuto non venga tagliato ai bordi della pagina.

### Passo 3: Creare una geometria di percorso rettangolare

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Consiglio*: La stringa del percorso segue la sintassi standard di XPS (`M` per move, `L` per line, `Z` per close). Modificate le coordinate per cambiare le dimensioni del rettangolo.

### Passo 4: Aggiungere un riempimento per i rettangoli

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Suggerimento professionale*: Usate `CreateColor` con valori RGB per abbinare la palette del vostro brand.

### Passo 5: Aggiungere una nuova tela senza trasformazioni

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Qui posizioniamo semplicemente un rettangolo sulla pagina senza alcuna trasformazione aggiuntiva—utile come elemento di riferimento.

### Passo 6: Aggiungere una nuova tela con trasformazione di traslazione

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Cosa succede?* La prima matrice sposta il rettangolo verso il basso di 200 unità. La chiamata successiva a `Translate` lo sposta di 500 unità a destra, dimostrando come più traslazioni possano essere concatenate.

### Passo 7: Aggiungere una nuova tela con doppia trasformazione di scala

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Perché scalare?* Una scala di 2 raddoppia larghezza e altezza del rettangolo, permettendovi di creare grafiche più grandi senza ridefinire la geometria.

### Passo 8: Aggiungere una nuova tela con trasformazione di rotazione attorno a un punto

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Insight chiave*: `RotateAround` ruota la tela attorno a un punto personalizzato (qui (100, 50)), offrendo un controllo preciso sui punti di ancoraggio della rotazione.

### Passo 9: Salvare il documento XPS risultante

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Dopo aver applicato tutte le trasformazioni, il documento viene salvato in `output1.xps`. Aprite il file con qualsiasi visualizzatore XPS per vedere i rettangoli impilati con le rispettive traslazioni, scalature e rotazioni.

## Problemi comuni e risoluzione

| Sintomo | Probabile causa | Soluzione |
|---------|----------------|-----------|
| File di output vuoto | `dataDir` punta a una cartella inesistente | Verificate che la directory esista o usate un percorso assoluto |
| Rettangoli non posizionati come previsto | Valori della matrice errati | Controllate l'ordine delle chiamate `Translate`, `Scale` e `RotateAround` |
| I colori appaiono errati | Valori RGB fuori dal range 0‑255 | Usate valori byte validi per ciascun canale |

## Domande frequenti

**D: Aspose.Page per .NET è compatibile con tutti gli ambienti di sviluppo .NET?**  
R: Sì, funziona senza problemi con Visual Studio, Visual Studio Code, Rider e qualsiasi IDE che supporti .NET.

**D: Dove posso trovare esempi aggiuntivi e la documentazione API dettagliata?**  
R: Visitate la documentazione ufficiale su [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**D: Posso provare Aspose.Page prima di acquistare una licenza?**  
R: Assolutamente sì. Una versione di prova gratuita è disponibile qui: [Aspose.Page Free Trial](https://releases.aspose.com/).

**D: Come ottengo una licenza temporanea per i test?**  
R: Potete richiederla tramite la pagina della licenza temporanea: [Temporary License](https://purchase.aspose.com/temporary-license/).

**D: Dove acquisto una licenza completa?**  
R: Acquistate direttamente dallo store Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Ultimo aggiornamento:** 2026-01-05  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}