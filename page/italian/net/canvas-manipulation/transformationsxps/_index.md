---
title: Trasformazioni XPS con Aspose.Page per .NET
linktitle: Trasformazioni XPS
second_title: API Aspose.Page .NET
description: Trasforma i documenti XPS senza sforzo con Aspose.Page per .NET. Segui la nostra guida passo passo per trasformazioni senza interruzioni.
type: docs
weight: 13
url: /it/net/canvas-manipulation/transformationsxps/
---
## introduzione

Benvenuto nel mondo di Aspose.Page per .NET, una potente libreria che ti consente di eseguire varie trasformazioni su documenti XPS senza sforzo. In questo tutorial, approfondiremo il processo di trasformazione dei documenti XPS utilizzando Aspose.Page per .NET. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida ti guiderà attraverso ogni passaggio, assicurandoti di comprendere facilmente i concetti.

## Prerequisiti

Prima di iniziare, assicurati di avere a disposizione quanto segue:

-  Aspose.Page per .NET Library: scarica e installa la libreria da[Aspose.Page per la documentazione .NET](https://reference.aspose.com/page/net/).

- Ambiente di sviluppo: configura un ambiente di sviluppo compatibile, come Visual Studio o qualsiasi altro strumento di sviluppo .NET.

- La tua directory dei documenti: sostituisci il segnaposto nel codice con il percorso effettivo della directory dei documenti.

Ora passiamo al tutorial!

## Importa spazi dei nomi

Innanzitutto, assicurati di importare gli spazi dei nomi necessari per rendere disponibili le funzionalità Aspose.Page per .NET nel tuo codice. Aggiungi i seguenti spazi dei nomi all'inizio dello script:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Passaggio 1: crea un nuovo documento XPS

```csharp
// Inizio ex:1
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";

// Crea un nuovo documento XPS
XpsDocument doc = new XpsDocument();
```

## Passaggio 2: crea una tela principale

```csharp
// Crea l'area di disegno principale, comune a tutti gli elementi della pagina
XpsCanvas canvas1 = doc.AddCanvas();

// Crea offset sinistro e superiore nella tela principale
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Passaggio 3: creare una geometria del percorso rettangolare

```csharp
// Crea una geometria del percorso rettangolare
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Passaggio 4: aggiungi un riempimento per i rettangoli

```csharp
// Crea un riempimento per i rettangoli
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Passaggio 5: aggiungi una nuova tela senza trasformazioni

```csharp
// Aggiungi una nuova tela senza alcuna trasformazione alla tela principale
XpsCanvas canvas2 = canvas1.AddCanvas();

// Crea un rettangolo in questa tela e riempilo
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Passaggio 6: aggiungi una nuova tela con la trasformazione Traduci

```csharp
// Aggiungi una nuova tela con trasformazione di traduzione nella tela principale
XpsCanvas canvas3 = canvas1.AddCanvas();

// Traduci questa tela per posizionare un nuovo rettangolo sotto il rettangolo precedente
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Traduci questa tela sul lato destro della pagina
canvas3.RenderTransform.Translate(500, 0);

// Crea un rettangolo in questa tela e riempilo
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Passaggio 7: aggiungi una nuova tela con trasformazione a doppia scala

```csharp
//Aggiungi una nuova tela con trasformazione su doppia scala alla tela principale
XpsCanvas canvas4 = canvas1.AddCanvas();

// Traduci questa tela per posizionare un nuovo rettangolo sotto il rettangolo precedente
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Ridimensiona questa tela
canvas4.RenderTransform.Scale(2, 2);

// Crea un rettangolo in questa tela e riempilo
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Passaggio 8: aggiungi una nuova tela con trasformazione di rotazione attorno a un punto

```csharp
// Aggiungi una nuova tela con rotazione attorno a una trasformazione di punti nella tela principale
XpsCanvas canvas5 = canvas1.AddCanvas();

// Traduci questa tela per posizionare un nuovo rettangolo sotto il rettangolo precedente
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Ruota questa tela attorno a un punto di 45 gradi
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Crea un rettangolo in questa tela e riempilo
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Passaggio 9: salvare il documento XPS risultante

```csharp
// Salva il documento XPS risultante
doc.Save(dataDir + "output1.xps");
// Fine Estesa:1
```

## Conclusione

Congratulazioni! Hai trasformato con successo un documento XPS utilizzando Aspose.Page per .NET. Questa guida illustra i passaggi essenziali, dall'impostazione dei prerequisiti all'esecuzione di varie trasformazioni. Sperimenta queste tecniche e sblocca tutto il potenziale di Aspose.Page per .NET nei tuoi progetti.

## Domande frequenti

### Q1: Aspose.Page per .NET è compatibile con tutti gli ambienti di sviluppo .NET?

A1: Sì, Aspose.Page per .NET è progettato per funzionare perfettamente con vari ambienti di sviluppo .NET, incluso Visual Studio.

### Q2: Dove posso trovare ulteriori esempi e documentazione per Aspose.Page per .NET?

 A2: Visita il[Aspose.Page per la documentazione .NET](https://reference.aspose.com/page/net/) per documentazione completa ed esempi.

### Q3: Posso provare Aspose.Page per .NET prima dell'acquisto?

 R3: Sì, puoi esplorare una versione di prova gratuita visitando[Prova gratuita di Aspose.Page](https://releases.aspose.com/).

### Q4: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

 A4: Ottieni una licenza temporanea visitando[Licenza temporanea](https://purchase.aspose.com/temporary-license/).

### Q5: Dove posso acquistare Aspose.Page per .NET?

 A5: Acquista Aspose.Page per .NET su[Aspose.Page Acquista](https://purchase.aspose.com/buy).