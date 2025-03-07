---
title: Aggiungi gradiente orizzontale a XPS con Aspose.Page per .NET
linktitle: Aggiungi gradiente orizzontale a XPS
second_title: API Aspose.Page .NET
description: Scopri come aggiungere splendidi gradienti orizzontali ai tuoi documenti XPS utilizzando Aspose.Page per .NET. Aumenta l'attrattiva visiva senza sforzo.
weight: 13
url: /it/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi gradiente orizzontale a XPS con Aspose.Page per .NET

## introduzione

In questo tutorial esploreremo come migliorare i documenti XPS aggiungendo un gradiente orizzontale utilizzando Aspose.Page per .NET. Aspose.Page per .NET è una potente libreria che fornisce una gestione fluida dei documenti XPS (XML Paper Specifica) nelle applicazioni .NET. L'aggiunta di sfumature può conferire fascino visivo ai tuoi documenti e questa guida ti guiderà attraverso il processo passo dopo passo.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1.  Libreria Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page per .NET installata nel tuo ambiente di sviluppo. Puoi scaricarlo da[Aspose.Page per la documentazione .NET](https://reference.aspose.com/page/net/).

2. Ambiente di sviluppo: configura un ambiente di sviluppo adatto, incluso un editor di codice come Visual Studio.

## Importa spazi dei nomi

Inizia importando gli spazi dei nomi necessari nel tuo progetto. Questi spazi dei nomi sono essenziali per lavorare con Aspose.Page per .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Ora suddividiamo l'esempio fornito in più passaggi.

## Passaggio 1: impostare il percorso della directory dei documenti

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

## Passaggio 3: inizializza gli arresti del gradiente

```csharp
// Inizio ex:5
// Inizializza l'elenco di XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// Fine Estesa:5
```

## Passaggio 4: crea un nuovo percorso

```csharp
// Inizio ex:6
//Crea un nuovo percorso definendo la geometria sotto forma di abbreviazione
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Fine Estesa:6
```

## Passaggio 5: salvare il documento XPS risultante

```csharp
// Inizio ex:7
// Salva il documento XPS risultante
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// Fine Estesa:7
```

Ora hai aggiunto con successo un gradiente orizzontale al tuo documento XPS utilizzando Aspose.Page per .NET.

## Conclusione

Migliorare i tuoi documenti XPS con sfumature non solo ne migliora l'attrattiva visiva, ma offre anche un'esperienza utente più coinvolgente. Aspose.Page per .NET semplifica questo processo, consentendoti di ottenere risultati professionali senza sforzo.

## Domande frequenti

### Q1: Dove posso trovare la documentazione Aspose.Page per .NET?

 A1: È possibile trovare la documentazione[Qui](https://reference.aspose.com/page/net/).

### Q2: Come posso scaricare Aspose.Page per .NET?

 A2: È possibile scaricare la libreria da[Aspose.Page per la pagina di download di .NET](https://releases.aspose.com/page/net/).

### Q3: Dove posso acquistare Aspose.Page per .NET?

 A3: È possibile acquistare Aspose.Page per .NET da[pagina di acquisto](https://purchase.aspose.com/buy).

### Q4: È disponibile una prova gratuita?

 R4: Sì, puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).

### Q5: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

 A5: È possibile ottenere una licenza temporanea da[questo link](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
