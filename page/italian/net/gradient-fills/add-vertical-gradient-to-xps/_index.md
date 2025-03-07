---
title: Aggiungi gradiente verticale a XPS con Aspose.Page per .NET
linktitle: Aggiungi gradiente verticale a XPS
second_title: API Aspose.Page .NET
description: Scopri come migliorare i documenti XPS con gradienti verticali utilizzando Aspose.Page per .NET. Segui la nostra guida passo passo per un'integrazione perfetta.
weight: 15
url: /it/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi gradiente verticale a XPS con Aspose.Page per .NET

## introduzione

Benvenuti in questo tutorial passo passo su come aggiungere un gradiente verticale a un documento XPS utilizzando Aspose.Page per .NET. Aspose.Page è una potente API che ti consente di lavorare con file XPS (XML Paper Specifica) nelle tue applicazioni .NET. In questo tutorial ti guideremo attraverso il processo di creazione di un nuovo documento XPS, aggiungendo un gradiente verticale a un tracciato e salvando il risultato.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:

-  Libreria Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page per .NET installata nel tuo ambiente di sviluppo. Puoi scaricarlo[Qui](https://releases.aspose.com/page/net/).

- Ambiente di sviluppo: configura un ambiente di sviluppo .NET con il tuo IDE preferito, come Visual Studio.

Ora iniziamo con l'aggiunta di un gradiente verticale a un documento XPS utilizzando Aspose.Page per .NET.

## Importa spazi dei nomi

Nella tua applicazione .NET, includi gli spazi dei nomi necessari per accedere alle classi e ai metodi Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Passaggio 1: imposta la directory dei documenti

Prima di iniziare, imposta il percorso della directory dei documenti in cui desideri salvare il documento XPS risultante.

```csharp
// Inizio ex:3
string dataDir = "Your Document Directory";
// Fine Estesa:3
```

## Passaggio 2: crea un nuovo documento XPS

Inizializza un nuovo documento XPS utilizzando il seguente codice:

```csharp
// Inizio ex:4
XpsDocument doc = new XpsDocument();
// Fine Estesa:4
```

## Passaggio 3: definire le interruzioni del gradiente

Crea un elenco di interruzioni del gradiente, specificando il colore e la posizione per ciascuna interruzione. In questo esempio definiamo un gradiente verticale con cinque fermate.

```csharp
// Inizio ex:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// Fine Estesa:5
```

## Passaggio 4: crea un percorso con gradiente

Definisci un percorso specificandone la geometria e applicagli un pennello a gradiente lineare.

```csharp
// Inizio ex:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Fine Estesa:6
```

## Passaggio 5: salvare il documento XPS risultante

Salva il documento XPS modificato nella directory specificata.

```csharp
// Inizio ex:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// Fine Estesa:7
```

Congratulazioni! Hai aggiunto con successo un gradiente verticale a un documento XPS utilizzando Aspose.Page per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato come sfruttare Aspose.Page per .NET per migliorare i documenti XPS con gradienti verticali. Aspose.Page semplifica attività complesse, fornendo agli sviluppatori un modo semplice per manipolare i file XPS nelle loro applicazioni .NET.

## Domande frequenti

### Q1: Aspose.Page è compatibile con Visual Studio 2019?

A1: Sì, Aspose.Page è compatibile con Visual Studio 2019. Assicurati di avere la versione corretta della libreria installata.

### Q2: Posso utilizzare Aspose.Page per progetti commerciali?

 A2: Sì, Aspose.Page può essere utilizzato per progetti commerciali. Visita[Qui](https://purchase.aspose.com/buy) per esplorare le opzioni di licenza.

### Q3: È disponibile una prova gratuita?

 A3: Sì, puoi ottenere una prova gratuita di Aspose.Page[Qui](https://releases.aspose.com/).

### Q4: Dove posso trovare la documentazione Aspose.Page?

 A4: La documentazione è disponibile[Qui](https://reference.aspose.com/page/net/).

### Q5: Come posso ottenere supporto o porre domande?

 A5: Visita il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il sostegno della comunità.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
