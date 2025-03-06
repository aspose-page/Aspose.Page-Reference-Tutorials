---
title: Ridimensiona le immagini EPS con Aspose.Page per .NET
linktitle: Ridimensiona le immagini EPS
second_title: API Aspose.Page .NET
description: Esplora il processo continuo di ridimensionamento delle immagini EPS in .NET utilizzando Aspose.Page. Ottieni precisione in punti, pollici, millimetri e percentuali senza sforzo.
weight: 11
url: /it/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ridimensiona le immagini EPS con Aspose.Page per .NET

## introduzione

Stai cercando di ridimensionare le immagini EPS senza problemi utilizzando Aspose.Page per .NET? Questo tutorial è la tua guida completa per manipolare facilmente le dimensioni delle immagini EPS in varie unità come punti, pollici, millimetri e percentuali. Aspose.Page per .NET fornisce un potente set di strumenti e in questo tutorial ti guideremo attraverso il processo passo dopo passo.

## Prerequisiti

Prima di immergerti nella magia del ridimensionamento, assicurati di disporre dei seguenti prerequisiti:

-  Libreria Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page per .NET installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/page/net/).

- Directory dei documenti: crea una directory in cui memorizzerai il file EPS di input e i file di output ridimensionati.

Ora che hai configurato tutto, procediamo con l'importazione degli spazi dei nomi necessari e approfondiamo la guida passo passo.

## Importa spazi dei nomi

Nel tuo progetto .NET, inizia importando gli spazi dei nomi necessari per lavorare con Aspose.Page. Aggiungi il seguente codice all'inizio del tuo file:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Passaggio 1: ridimensionamento in punti

Iniziamo ridimensionando un'immagine EPS in punti. I punti sono un'unità di misura standard nel settore della stampa.

```csharp
public static void ResizeInPoints()
{
    // La tua directory di documenti
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Passaggio 2: ridimensionamento in pollici

Ora ridimensioniamo un'immagine EPS in pollici, un'unità comune utilizzata nella progettazione grafica.

```csharp
public static void ResizeInInches()
{
    // La tua directory di documenti
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Passaggio 3: ridimensionamento in millimetri

Ora ridimensioniamo un'immagine EPS in millimetri, un'altra unità ampiamente utilizzata nella progettazione e nella stampa.

```csharp
public static void ResizeInMillimeters()
{
    // La tua directory di documenti
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Passaggio 4: ridimensionamento in percentuale

Infine, ridimensioniamo un'immagine EPS utilizzando le percentuali, fornendo un approccio flessibile per regolare le dimensioni dell'immagine.

```csharp
public static void ResizeInPercents()
{
    // La tua directory di documenti
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Sentiti libero di integrare questi metodi nel tuo progetto e ridimensionerai le immagini EPS senza sforzo. Sperimenta unità diverse per ottenere le dimensioni desiderate.

## Conclusione

Congratulazioni! Hai imparato l'arte di ridimensionare le immagini EPS con Aspose.Page per .NET. Questa potente libreria apre un mondo di possibilità per manipolare la grafica vettoriale. Che tu stia progettando per la stampa o per i media digitali, Aspose.Page ti consente di ottenere risultati precisi e personalizzati.

## Domande frequenti

### Q1: Posso ridimensionare più immagini EPS contemporaneamente?

R1: Sì, puoi scorrere una raccolta di file EPS, applicando di conseguenza i metodi di ridimensionamento.

### Q2: Aspose.Page è compatibile con altri formati di immagine?

A2: Aspose.Page si concentra principalmente sui formati PostScript ed EPS. Per altri formati di immagine, considera l'utilizzo di Aspose.Imaging.

### Q3: Esistono considerazioni sulla licenza per i progetti commerciali?

 R3: Sì, assicurati di avere una licenza valida. Visita[Qui](https://purchase.aspose.com/buy) per i dettagli sulla licenza.

### Q4: Posso provare Aspose.Page prima dell'acquisto?

 A4: Assolutamente! Puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).

### Q5: Dove posso cercare ulteriore aiuto o discutere i problemi?

 A5: Visita il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per connettersi con la comunità e ottenere assistenza.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
