---
title: Mostra la pseudo-trasparenza in PostScript (PS) con Aspose.Page
linktitle: Mostra pseudo-trasparenza in PostScript (PS)
second_title: API Aspose.Page .NET
description: Esplora la potenza della pseudo-trasparenza in PostScript con Aspose.Page per .NET. Segui la nostra guida passo passo per documenti visivamente sbalorditivi.
type: docs
weight: 13
url: /it/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## introduzione

Desideri migliorare l'aspetto visivo dei tuoi documenti PostScript (PS) incorporando la pseudo-trasparenza? Aspose.Page per .NET fornisce una potente soluzione per ottenere questo effetto senza sforzo. In questo tutorial passo passo, ti guideremo attraverso il processo di visualizzazione della pseudo-trasparenza in PostScript utilizzando Aspose.Page.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

- Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page per .NET installata. Puoi scaricarlo da[Documentazione Aspose.Page](https://reference.aspose.com/page/net/).

- Directory dei documenti: imposta una directory in cui archiviare i documenti PostScript.

Ora che hai gli strumenti necessari nel tuo arsenale, esploriamo come mostrare la pseudo-trasparenza in PostScript utilizzando Aspose.Page.

## Importa spazi dei nomi

Prima di approfondire l'esempio, assicurati di importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Passaggio 1: crea il flusso di output per il documento PostScript

```csharp
// Inizio ex:1
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
//Crea flusso di output per il documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Crea opzioni di salvataggio con il formato A4
	PsSaveOptions options = new PsSaveOptions();

	// Crea un nuovo documento PS di 1 pagina
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passaggio 2: crea un rettangolo con riempimento sfumato opaco

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Passaggio 3: crea un rettangolo con riempimento sfumato traslucido

```csharp
	offsetX = 350;

	//Crea il percorso grafico dal primo rettangolo
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Crea colori del pennello con gradiente lineare la cui trasparenza non è 255, ma 150 e 50. Quindi sono traslucidi.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Passaggio 4: chiudi la pagina corrente e salva il documento

```csharp
	document.ClosePage();
	document.Save();
}
// Fine Estesa:1
```

Seguendo questi passaggi, puoi integrare perfettamente la pseudo-trasparenza nei tuoi documenti PostScript utilizzando Aspose.Page per .NET.

## Conclusione

In conclusione, Aspose.Page per .NET offre un modo semplice ed efficiente per migliorare gli elementi visivi dei tuoi documenti PostScript. I passaggi sopra descritti forniscono un percorso chiaro per incorporare la pseudo-trasparenza, consentendoti di creare output visivamente sorprendenti.

## Domande frequenti

### Q1: Aspose.Page è compatibile con tutte le versioni di .NET?

A1: Aspose.Page per .NET è compatibile con varie versioni del framework .NET, garantendo flessibilità e facilità di integrazione.

### Q2: Posso applicare la pseudotrasparenza ad altre forme oltre ai rettangoli?

R2: Sì, gli stessi principi possono essere applicati ad altre forme regolando di conseguenza GraphicsPath.

### Q3: Dove posso trovare ulteriori esempi e documentazione?

 A3: Esplora il[Documentazione Aspose.Page](https://reference.aspose.com/page/net/) per esempi completi e documentazione dettagliata.

### Q4: È disponibile una prova gratuita per Aspose.Page?

 A4: Sì, puoi accedere a una prova gratuita di Aspose.Page da[questo link](https://releases.aspose.com/).

### Q5: Come posso ottenere una licenza temporanea per Aspose.Page?

 A5: Visita[questo link](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea per Aspose.Page.