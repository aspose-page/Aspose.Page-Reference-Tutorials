---
title: Ritaglio di XPS con Aspose.Page per .NET
linktitle: Ritaglio dell'XPS
second_title: API Aspose.Page .NET
description: Esplora la potenza di Aspose.Page per .NET in questa guida passo passo su come ritagliare documenti XPS. Crea, manipola e salva file XPS senza sforzo.
type: docs
weight: 11
url: /it/net/canvas-manipulation/clippingxps/
---
## introduzione

Benvenuti in questo tutorial completo sul ritaglio di XPS utilizzando Aspose.Page per .NET! In questa guida ti guideremo attraverso il processo di creazione, manipolazione e salvataggio di documenti XPS utilizzando Aspose.Page per .NET. XPS, o XML PaperSpecific, è un formato di documento standardizzato e aperto e Aspose.Page per .NET fornisce potenti strumenti per lavorare con documenti XPS nelle applicazioni .NET.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:

- Visual Studio installato sul tuo computer.
-  Libreria Aspose.Page per .NET aggiunta al tuo progetto. Puoi scaricarlo[Qui](https://releases.aspose.com/page/net/).
- Conoscenza base del linguaggio di programmazione C#.

## Importa spazi dei nomi

Per utilizzare Aspose.Page per le funzionalità .NET, è necessario importare gli spazi dei nomi richiesti nel progetto. Segui questi passi:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ora suddividiamo il codice di esempio che hai fornito in più passaggi.

## Passaggio 1: impostare il percorso della directory del documento.

```csharp
string dataDir = "Your Document Directory";
```

Assicurati di sostituire "La tua directory dei documenti" con il percorso effettivo della directory dei documenti.

## Passaggio 2: crea un nuovo documento XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Questo crea un nuovo documento XPS con cui lavorerai.

## Passaggio 3: crea la tela principale.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Questo passaggio crea l'area di disegno principale, comune a tutti gli elementi della pagina.

## Passaggio 4: imposta gli offset sinistro e superiore nell'area di disegno principale.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Regola gli offset sinistro e superiore secondo le tue esigenze.

## Passaggio 5: creare una geometria del percorso rettangolare.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Questo crea una geometria del percorso per un rettangolo.

## Passaggio 6: crea un riempimento per i rettangoli.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Definire il colore di riempimento per i rettangoli.

## Passaggio 7: aggiungi un'altra tela con clip alla tela principale.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Questo passaggio aggiunge un'altra tela alla tela principale.

## Passaggio 8: crea una geometria circolare per la clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Questo crea una geometria di clip circolare e la applica alla seconda tela.

## Passaggio 9: crea un rettangolo nella seconda tela e riempilo.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Questo passaggio crea un rettangolo nella seconda tela e lo riempie.

## Passaggio 10: aggiungi la seconda tela con un rettangolo tratteggiato alla tela principale.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Ciò aggiunge un'altra tela alla tela principale.

## Passaggio 11: crea un rettangolo nella terza tela e accarezzalo.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Questo crea un rettangolo nella terza tela e vi applica un tratto.

## Passaggio 12: salva il documento XPS risultante.

```csharp
doc.Save(dataDir + "output2.xps");
```

Ciò salva il documento XPS nella directory specificata.

## Conclusione

Congratulazioni! Hai imparato con successo come ritagliare XPS utilizzando Aspose.Page per .NET. Questa guida fornisce una panoramica dettagliata dei passaggi coinvolti nel processo.

## Domande frequenti

### Q1: posso utilizzare Aspose.Page per .NET con altri formati di documenti?

A1: Aspose.Page per .NET si concentra principalmente sui documenti XPS, ma Aspose fornisce altre librerie per vari formati di documenti.

### Q2: Aspose.Page per .NET è adatto ai principianti?

A2: Sì, Aspose.Page per .NET è progettato per essere facile da usare e i principianti possono comprenderne rapidamente le funzionalità con la documentazione adeguata.

### Q3: Dove posso trovare altri esempi e risorse?

 A3: Visita il[documentazione](https://reference.aspose.com/page/net/) E[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per ampie risorse ed esempi.

### Q4: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

 A4: Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

### Q5: È disponibile una prova gratuita per Aspose.Page per .NET?

 R5: Sì, puoi esplorare la prova gratuita[Qui](https://releases.aspose.com/).