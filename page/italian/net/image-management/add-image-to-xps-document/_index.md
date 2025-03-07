---
title: Aggiungi immagine al documento XPS con Aspose.Page per .NET
linktitle: Aggiungi immagine al documento XPS
second_title: API Aspose.Page .NET
description: Esplora la perfetta integrazione delle immagini nei documenti XPS con Aspose.Page per .NET. Segui la nostra guida passo passo per un'esperienza di sviluppo fluida.
weight: 11
url: /it/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi immagine al documento XPS con Aspose.Page per .NET

## introduzione

Nel mondo dello sviluppo .NET, incorporare immagini nei documenti XPS è un requisito comune. Aspose.Page per .NET semplifica questo processo, offrendo un potente toolkit per manipolare e migliorare i documenti XPS senza sforzo. Questo tutorial ti guiderà attraverso i passaggi per aggiungere un'immagine a un documento XPS utilizzando Aspose.Page per .NET.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:

1.  Aspose.Page per .NET Library: scarica e installa la libreria da[Aspose.Page Documentazione .NET](https://reference.aspose.com/page/net/).

2. Ambiente di sviluppo: configura un ambiente di sviluppo .NET, come Visual Studio.

3. Immagine di esempio: disponi di un file di immagine di esempio (ad esempio, "QL_logo_color.tif") che desideri aggiungere al documento XPS.

## Importa spazi dei nomi

Inizia importando gli spazi dei nomi necessari nel tuo progetto .NET. Questi spazi dei nomi sono vitali per utilizzare le funzionalità fornite da Aspose.Page per .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Passaggio 1: imposta la directory dei documenti

Inizia specificando il percorso della directory dei documenti. Questo passaggio garantisce che il tuo progetto sappia dove individuare e salvare i file.

```csharp
// Inizio ex:1
string dataDir = "Your Document Directory";
// Fine Estesa:1
```

## Passaggio 2: crea un documento XPS

Crea un nuovo documento XPS utilizzando Aspose.Page per .NET.

```csharp
// Inizio ex:1
XpsDocument doc = new XpsDocument();
// Fine Estesa:1
```

## Passaggio 3: aggiungi immagine al documento XPS

Ora aggiungiamo l'immagine al documento XPS. In questo esempio, utilizzeremo un'immagine di esempio denominata "QL_logo_color.tif".

```csharp
// Inizio ex:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// Fine Estesa:1
```

## Passaggio 4: salvare il documento XPS risultante

Salva il documento XPS con l'immagine aggiunta.

```csharp
// Inizio ex:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// Fine Estesa:1
```

Ora hai aggiunto con successo un'immagine a un documento XPS utilizzando Aspose.Page per .NET!

## Conclusione

In questo tutorial, abbiamo esplorato come sfruttare Aspose.Page per .NET per incorporare perfettamente immagini nei documenti XPS. Questa guida passo passo garantisce un processo di integrazione fluido, migliorando le tue capacità di sviluppo .NET.

## Domande frequenti

### Q1: Aspose.Page per .NET è compatibile con le ultime versioni di .NET framework?

 A1: Aspose.Page per .NET è progettato per essere compatibile con un'ampia gamma di versioni di .NET framework, comprese le versioni più recenti. Fare riferimento al[documentazione](https://reference.aspose.com/page/net/) per dettagli specifici.

### Q2: Posso utilizzare Aspose.Page per .NET in ambienti Windows e Linux?

A2: Sì, Aspose.Page per .NET è indipendente dalla piattaforma, rendendolo adatto all'uso sia in ambienti Windows che Linux.

### Q3: Sono disponibili opzioni di licenza per Aspose.Page per .NET?

 R3: Sì, puoi esplorare le opzioni di licenza ed effettuare un acquisto[Qui](https://purchase.aspose.com/buy).

### Q4: È disponibile una prova gratuita per Aspose.Page per .NET?

 A4: Sì, puoi provare Aspose.Page per .NET gratuitamente accedendo a[prova gratuita](https://releases.aspose.com/).

### Q5: Dove posso chiedere assistenza o interagire con la comunità per Aspose.Page per .NET?

 A5: Visita il[Aspose.Page per il forum .NET](https://forum.aspose.com/c/page/39) per connettersi con la comunità e ottenere supporto.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
