---
title: Aggiungi oggetto trasparente al documento XPS con Aspose.Page
linktitle: Aggiungi oggetto trasparente al documento XPS
second_title: API Aspose.Page .NET
description: Scopri come aggiungere oggetti trasparenti ai documenti XPS in .NET utilizzando Aspose.Page. Migliora l'attrattiva visiva con una guida passo passo.
type: docs
weight: 11
url: /it/net/transparency-effects/add-transparent-object-to-xps-document/
---
## introduzione

In questo tutorial esploreremo come aggiungere oggetti trasparenti a un documento XPS utilizzando Aspose.Page per .NET. La trasparenza nei documenti XPS può migliorare l'attrattiva visiva e trasmettere le informazioni in modo efficace. Suddivideremo il processo in passaggi gestibili, garantendo chiarezza e facilità di comprensione.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

-  Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page per .NET installata. Puoi scaricarlo da[Aspose.Page per la documentazione .NET](https://reference.aspose.com/page/net/).

## Importa spazi dei nomi

Per iniziare, includi gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ora procediamo con la guida passo passo.

## Passaggio 1: crea un nuovo documento XPS

```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
// Crea un nuovo documento XPS
XpsDocument doc = new XpsDocument();
```

Questo codice inizializza un nuovo documento XPS utilizzando Aspose.Page per .NET.

## Passaggio 2: dimostrare trasparenza

```csharp
// Giusto per dimostrare trasparenza
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Queste linee creano percorsi trasparenti per mostrare l'effetto della trasparenza nel documento.

## Passaggio 3: crea un percorso con una geometria rettangolare chiusa

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Qui creiamo un tracciato con una geometria rettangolare chiusa, impostiamo un pennello blu a tinta unita per riempirlo e lo aggiungiamo alla pagina corrente.

## Passaggio 4: manipola percorsi e colori

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Questo passaggio dimostra come è possibile manipolare i percorsi e modificare i colori.

## Passaggio 5: clona e trasforma i percorsi

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Clona e trasforma i percorsi, spostando e cambiando il colore del percorso clonato.

## Passaggio 6: ripetere e modificare i percorsi

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Ripeti il processo, creando un nuovo percorso basato su quello precedente, con modifiche.

## Passaggio 7: gestisci l'opacità

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Dimostrare come l'opacità può essere gestita in modo indipendente per percorsi diversi.

## Passaggio 8: salva il documento XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Infine, salva il documento XPS risultante con la trasparenza applicata.

## Conclusione

L'aggiunta di oggetti trasparenti ai documenti XPS utilizzando Aspose.Page per .NET fornisce un modo versatile per migliorare le presentazioni visive. Sperimenta diverse geometrie, colori e opacità per ottenere l'effetto desiderato.

## Domande frequenti

### Q1: posso applicare la trasparenza a qualsiasi oggetto in un documento XPS?

R1: Sì, la trasparenza può essere applicata a vari oggetti come tracciati, forme e immagini in un documento XPS.

### Q2: Come posso regolare l'opacità di un elemento specifico?

A2: puoi impostare la proprietà di opacità del riempimento o del tratto per regolare la trasparenza di un elemento specifico.

### Q3: Aspose.Page è compatibile con .NET Core?

A3: Sì, Aspose.Page supporta .NET Core, consentendo lo sviluppo multipiattaforma.

### Q4: Posso esportare documenti XPS in altri formati utilizzando Aspose.Page?

A4: Aspose.Page fornisce funzionalità per esportare documenti XPS in vari formati, inclusi PDF e immagini.

### Q5: Dove posso trovare ulteriore supporto e discussioni nella community?

 R5: Per ulteriore supporto e discussioni nella community, visitare il sito[Aspose.Page Forum](https://forum.aspose.com/c/page/39).