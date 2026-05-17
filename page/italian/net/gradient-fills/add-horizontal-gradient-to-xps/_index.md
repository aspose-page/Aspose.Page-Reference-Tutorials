---
date: 2026-02-25
description: Scopri come creare un gradiente XPS con riempimento orizzontale usando
  Aspose.Page per .NET. Eleva l'appeal visivo senza sforzo nei tuoi documenti.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Crea gradiente XPS: riempimento orizzontale con Aspose.Page per .NET'
url: /it/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un Gradiente XPS – Aggiungi un Gradiente Orizzontale a XPS con Aspose.Page per .NET

## Introduzione

In questo tutorial **creerai riempimenti a gradiente XPS** che scorrono orizzontalmente attraverso le tue pagine. Aggiungere un gradiente orizzontale può rendere immediatamente un documento XPS più curato e accattivante, soprattutto per report, brochure o qualsiasi output ricco di contenuti visivi. Ti guideremo attraverso l’intero processo usando Aspose.Page per .NET, dalla configurazione dell’ambiente al salvataggio del file XPS finale.

## Risposte Rapide
- **Cosa copre questo tutorial?** Aggiungere un gradiente orizzontale a un documento XPS con Aspose.Page per .NET.  
- **Quale libreria è necessaria?** Aspose.Page per .NET (qualsiasi versione recente).  
- **È necessaria una licenza?** Una versione di prova funziona per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Quanto tempo richiede l’implementazione?** Circa 5–10 minuti per un gradiente di base.  
- **Posso cambiare la direzione del gradiente?** Sì – modifica i punti di inizio/fine del `LinearGradientBrush`.

## Come creare un gradiente XPS con Aspose.Page per .NET

Di seguito trovi una guida passo‑passo che spiega **perché** esiste ogni riga di codice, non solo **cosa** fa. Sentiti libero di seguirla in Visual Studio o nel tuo editor .NET preferito.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. **Libreria Aspose.Page per .NET:** Verifica di aver installato la libreria Aspose.Page per .NET nel tuo ambiente di sviluppo. Puoi scaricarla dalla [Documentazione di Aspose.Page per .NET](https://reference.aspose.com/page/net/).

2. **Ambiente di sviluppo:** Configura un ambiente di sviluppo adeguato, includendo un editor di codice come Visual Studio.

## Importare i Namespace

Inizia importando i namespace necessari nel tuo progetto. Questi namespace sono essenziali per lavorare con Aspose.Page per .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Ora, analizziamo l’esempio fornito suddividendolo in più passaggi.

## Passo 1: Impostare il Percorso della Cartella del Documento

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Passo 2: Creare un Nuovo Documento XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Passo 3: Inizializzare le Fermate del Gradiente

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Passo 4: Creare un Nuovo Percorso

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Passo 5: Salvare il Documento XPS Resultante

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Ora hai aggiunto con successo un gradiente orizzontale al tuo documento XPS usando Aspose.Page per .NET.

## Problemi Comuni e Soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| Il gradiente appare come colore solido | Fermate del gradiente non aggiunte correttamente | Assicurati che `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` venga eseguito dopo aver impostato il brush. |
| Il file salvato è vuoto | `dataDir` punta a una cartella inesistente | Verifica che la cartella esista o utilizza un percorso assoluto. |
| Errore di compilazione su `PointF` | Riferimento a `System.Drawing` mancante | Aggiungi un riferimento a `System.Drawing.Common` (per .NET Core/5+). |

## FAQ

### Q1: Dove posso trovare la documentazione di Aspose.Page per .NET?

A1: Puoi trovare la documentazione [qui](https://reference.aspose.com/page/net/).

### Q2: Come scarico Aspose.Page per .NET?

A2: Puoi scaricare la libreria dalla [pagina di download di Aspose.Page per .NET](https://releases.aspose.com/page/net/).

### Q3: Dove posso acquistare Aspose.Page per .NET?

A3: Puoi acquistare Aspose.Page per .NET dalla [pagina di acquisto](https://purchase.aspose.com/buy).

### Q4: È disponibile una versione di prova gratuita?

A4: Sì, puoi ottenere una prova gratuita [qui](https://releases.aspose.com/).

### Q5: Come ottengo una licenza temporanea per Aspose.Page per .NET?

A5: Puoi ottenere una licenza temporanea da [questo link](https://purchase.aspose.com/temporary-license/).

## Domande Frequenti

**D: Posso usare questa tecnica di gradiente con documenti XPS che contengono già immagini?**  
R: Assolutamente. Il gradiente viene applicato a un livello di percorso, quindi le immagini esistenti rimangono intatte.

**D: È possibile creare un gradiente verticale invece?**  
R: Sì. Cambia i punti di inizio e fine del `LinearGradientBrush` in modo che abbiano coordinate Y diverse mantenendo X costante.

**D: Aspose.Page supporta .NET Core?**  
R: La libreria è pienamente compatibile con .NET Core, .NET 5 e versioni successive.

**D: Come posso riutilizzare lo stesso gradiente su più pagine?**  
R: Crea una sola volta lo `XpsLinearGradientBrush`, memorizzalo in una variabile e assegnalo ai percorsi di ciascuna pagina.

## Conclusione

Arricchire i tuoi documenti XPS con i gradienti non solo migliora l’aspetto visivo, ma offre anche un’esperienza utente più coinvolgente. Con Aspose.Page per .NET, puoi **creare riempimenti a gradiente XPS** rapidamente e in modo affidabile, conferendo ai tuoi report, brochure o e‑book una finitura professionale.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-02-25  
**Testato con:** Aspose.Page per .NET 24.11  
**Autore:** Aspose  

---