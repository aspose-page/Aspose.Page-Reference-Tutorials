---
title: Aggiungi rettangolo al documento XPS con Aspose.Page per .NET
linktitle: Aggiungi rettangolo al documento XPS
second_title: API Aspose.Page .NET
description: Migliora la creazione di documenti con Aspose.Page per .NET. Scopri come aggiungere rettangoli ai documenti XPS in questo tutorial passo passo.
weight: 13
url: /it/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi rettangolo al documento XPS con Aspose.Page per .NET

## introduzione

Aspose.Page per .NET è una potente libreria che fornisce una varietà di funzionalità per lavorare con documenti XPS (XML Paper Specifica) nelle applicazioni .NET. In questo tutorial, ci concentreremo sull'aggiunta di un rettangolo a un documento XPS utilizzando Aspose.Page per .NET. Segui questa guida passo passo per migliorare il processo di creazione dei documenti.

## Prerequisiti

Prima di iniziare con questo tutorial, assicurati di disporre dei seguenti prerequisiti:

1.  Libreria Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page per .NET installata nel tuo ambiente di sviluppo. Puoi scaricarlo[Qui](https://releases.aspose.com/page/net/).

2. Directory dei documenti: imposta una directory in cui desideri archiviare i tuoi documenti XPS.

## Importa spazi dei nomi

Nella tua applicazione .NET, includi gli spazi dei nomi necessari per utilizzare le funzionalità Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Passaggio 1: impostare la directory dei documenti

```csharp
// Inizio ex:3
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
// Fine Estesa:3
```

## Passaggio 2: crea un nuovo documento XPS

```csharp
// Inizio ex:4
// Crea un nuovo documento XPS
XpsDocument doc = new XpsDocument();
// Fine Estesa:4
```

## Passaggio 3: aggiungi un rettangolo

```csharp
// Inizio ex:5
// Rettangolo tracciato in tinta unita CMYK (blu) in basso a sinistra
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// Fine Estesa:5
```

## Passaggio 4: salva il documento

```csharp
// Inizio ex:6
// Salva il documento XPS risultante
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// Fine Estesa:6
```

Congratulazioni! Hai aggiunto con successo un rettangolo a un documento XPS utilizzando Aspose.Page per .NET.

## Conclusione

Aspose.Page per .NET semplifica le attività di manipolazione dei documenti, consentendo agli sviluppatori di creare e modificare documenti XPS senza sforzo. Questa guida passo passo mostra come aggiungere un rettangolo al tuo documento XPS, fornendo una solida base per ulteriori esplorazioni.

## Domande frequenti

### Q1: Aspose.Page è compatibile con tutte le applicazioni .NET?

A1: Sì, Aspose.Page è progettato per funzionare perfettamente con tutte le applicazioni .NET.

### Q2: Dove posso trovare la documentazione per Aspose.Page per .NET?

 A2: La documentazione è disponibile[Qui](https://reference.aspose.com/page/net/).

### Q3: Posso provare Aspose.Page per .NET gratuitamente prima dell'acquisto?

 R3: Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).

### Q4: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

 A4: Visita[questo link](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea.

### Q5: Dove posso cercare il supporto della comunità o porre domande relative a Aspose.Page per .NET?

 A5: Visita il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il sostegno della comunità.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
