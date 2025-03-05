---
title: Aggiungi Circle Ellipse al documento XPS con Aspose.Page per .NET
linktitle: Aggiungi Ellisse circolare al documento XPS
second_title: API Aspose.Page .NET
description: Migliora i documenti XPS con vivaci gradienti radiali utilizzando Aspose.Page per .NET. Segui la nostra guida passo passo per ottenere effetti visivi sorprendenti.
type: docs
weight: 11
url: /it/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## introduzione

La creazione di documenti XPS visivamente accattivanti è un requisito comune in varie applicazioni. Aspose.Page per .NET fornisce un potente set di funzionalità per manipolare i documenti XPS in modo efficiente. In questo tutorial, ci concentreremo sull'aggiunta di un'ellisse circolare a un documento XPS utilizzando Aspose.Page per .NET. Segui i passaggi seguenti per migliorare i tuoi documenti XPS con vivaci gradienti radiali.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

-  Aspose.Page installato per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/page/net/).
- Un ambiente di sviluppo, preferibilmente Visual Studio o qualsiasi altro strumento di sviluppo .NET.
- Conoscenza base della programmazione C#.

## Importa spazi dei nomi

Per iniziare, includi gli spazi dei nomi necessari nel codice C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Ora suddividiamo l'esempio in più passaggi:

## Passaggio 1: impostare il documento

```csharp
// Inizio ex:1
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
// Crea un nuovo documento XPS
XpsDocument doc = new XpsDocument();
```

Qui, inizializziamo un nuovo documento XPS utilizzando Aspose.Page per .NET.

## Passaggio 2: definire l'ellisse del gradiente radiale

```csharp
// Ellisse accarezzata con gradiente radiale in basso a sinistra
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Questo passaggio prevede la definizione di un'ellisse con gradiente radiale con varie interruzioni di colore.

## Passaggio 3: imposta il pennello sfumatura radiale

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Qui impostiamo il tratto dell'ellisse su un pennello a gradiente radiale, fornendogli i parametri necessari.

## Passaggio 4: regola lo spessore del tratto

```csharp
path.StrokeThickness = 12f;
```

Questo passaggio prevede la regolazione dello spessore del tratto per una migliore visualizzazione.

## Passaggio 5: salvare il documento XPS risultante

```csharp
// Salva il documento XPS risultante
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// Fine Estesa:1
```

Infine, salva il documento XPS modificato nella posizione desiderata.

## Conclusione

Congratulazioni! Hai aggiunto con successo un'ellisse circolare con sfumature radiali al tuo documento XPS utilizzando Aspose.Page per .NET. Sperimenta parametri e colori diversi per ottenere gli effetti visivi desiderati nei tuoi documenti.

## Domande frequenti

### Q1: posso utilizzare Aspose.Page per .NET con altri formati di documenti?

A1: Aspose.Page per .NET si occupa specificamente della manipolazione dei documenti XPS. Per altri formati, considera l'utilizzo delle librerie Aspose correlate.

### Q2: È disponibile una licenza temporanea a scopo di test?

 R2: Sì, puoi ottenere una licenza temporanea per i test visitando[questo link](https://purchase.aspose.com/temporary-license/).

### Q3: Dove posso trovare ulteriore aiuto e discussioni?

 A3: Visita il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto e le discussioni della comunità.

### Q4: Sono disponibili documenti di esempio come riferimento?

 A4: Esplora il[documentazione](https://reference.aspose.com/page/net/) per esempi e linee guida esaustivi.

### Q5: Posso acquistare Aspose.Page per .NET?

 R5: Sì, puoi acquistare la libreria[Qui](https://purchase.aspose.com/buy).