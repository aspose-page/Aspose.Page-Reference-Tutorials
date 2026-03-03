---
date: 2026-03-03
description: Scopri come ridimensionare le immagini EPS in .NET con Aspose.Page –
  una guida passo‑passo su come ridimensionare gli EPS usando punti, pollici, millimetri
  o percentuali.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Come ridimensionare le immagini EPS con Aspose.Page per .NET
url: /it/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ridimensionare le immagini EPS con Aspose.Page per .NET

## Introduzione

Stai cercando **come ridimensionare le immagini EPS** in modo fluido usando Aspose.Page per .NET? Questo tutorial è la tua guida completa per manipolare facilmente le dimensioni delle immagini EPS in varie unità come punti, pollici, millimetri e percentuali. Aspose.Page per .NET offre un potente set di strumenti e, in questo tutorial, ti guideremo passo passo attraverso il processo.

## Risposte rapide
- **Quale libreria gestisce il ridimensionamento EPS?** Aspose.Page for .NET  
- **Quali unità sono supportate?** Points, Inches, Millimeters, and Percents  
- **È necessaria una licenza per la produzione?** Yes – a commercial license is required  
- **Posso ridimensionare più file contemporaneamente?** Absolutely – just loop through the files  
- **.NET Core è supportato?** Yes, the API works with .NET Framework and .NET Core  

## Cos'è il ridimensionamento EPS?
Encapsulated PostScript (EPS) è un formato grafico basato su vettori comunemente usato nei flussi di lavoro di stampa e design. Ridimensionare un file EPS ne modifica il bounding box senza rasterizzare l'opera, preservando la nitidezza a qualsiasi scala.

## Perché ridimensionare le immagini EPS?
- **Mantenere la qualità di stampa:** Il ridimensionamento vettoriale mantiene i bordi nitidi.  
- **Adattare ai requisiti di layout:** Regola le dimensioni per corrispondere alle dimensioni della pagina o della tela.  
- **Automatizzare i lavori batch:** Ridimensiona programmaticamente decine di file in pochi secondi.  

## Prerequisiti

Prima di immergerti nella magia del ridimensionamento, assicurati di avere i seguenti prerequisiti in ordine:

- Aspose.Page for .NET Library: Assicurati di avere la libreria Aspose.Page per .NET installata. Puoi scaricarla da [qui](https://releases.aspose.com/page/net/).

- Document Directory: Crea una directory dove memorizzerai il tuo file EPS di input e i file ridimensionati di output.

Ora che hai tutto configurato, procediamo a importare gli spazi dei nomi necessari e ad approfondire la guida passo‑passo.

## Importare gli spazi dei nomi

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

## Come ridimensionare EPS in punti

I punti sono un'unità di misura standard nell'industria della stampa. L'esempio seguente raddoppia la larghezza e l'altezza originali.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## Come ridimensionare EPS in pollici

I pollici sono frequentemente usati dai grafici quando preparano risorse per la stampa.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## Come ridimensionare EPS in millimetri

I millimetri sono comuni nelle regioni che utilizzano il sistema metrico.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## Come ridimensionare EPS usando le percentuali

Il ridimensionamento basato su percentuali ti consente di scalare l'immagine rispetto alle sue dimensioni originali.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

Sentiti libero di integrare questi metodi nel tuo progetto, e potrai ridimensionare le immagini EPS senza sforzo. Sperimenta con diverse unità per ottenere le dimensioni desiderate.

## Problemi comuni e soluzioni
- **File non trovato:** Verifica che `dataDir` punti alla cartella corretta e che `input.eps` esista.  
- **Dimensione inaspettata:** Ricorda che `Units.Percents` si aspetta valori come 150 per il 150 % della dimensione originale.  
- **Eccezione di licenza:** Se visualizzi un errore di licenza, assicurati che un file di licenza Aspose.Page valido sia caricato prima di creare `PsDocument`.

## Conclusione

Congratulazioni! Hai padroneggiato **come ridimensionare le immagini EPS** con Aspose.Page per .NET. Questa potente libreria apre un mondo di possibilità per manipolare grafica vettoriale. Che tu stia progettando per la stampa o per i media digitali, Aspose.Page ti consente di ottenere risultati precisi e personalizzati.

## FAQ

### Q1: Posso ridimensionare più immagini EPS simultaneamente?

A1: Sì, puoi iterare su una raccolta di file EPS, applicando i metodi di ridimensionamento di conseguenza.

### Q2: Aspose.Page è compatibile con altri formati immagine?

A2: Aspose.Page si concentra principalmente sui formati PostScript ed EPS. Per altri formati immagine, considera l'uso di Aspose.Imaging.

### Q3: Ci sono considerazioni di licenza per progetti commerciali?

A3: Sì, assicurati di avere una licenza valida. Visita [qui](https://purchase.aspose.com/buy) per i dettagli sulla licenza.

### Q4: Posso provare Aspose.Page prima di acquistare?

A4: Assolutamente! Puoi ottenere una prova gratuita [qui](https://releases.aspose.com/).

### Q5: Dove posso cercare ulteriore aiuto o discutere problemi?

A5: Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per connetterti con la community e ottenere assistenza.

## Domande frequenti

**Q: Questo codice funziona con .NET Core 6?**  
A: Sì. L'API è compatibile con .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ e .NET 6+.

**Q: Come posso preservare il profilo colore originale?**  
A: Il metodo `ResizeEps` non altera i dati colore; modifica solo il bounding box.

**Q: È possibile ridimensionare un EPS senza caricare l'intero file in memoria?**  
A: Usare uno stream come mostrato mantiene basso l'uso della memoria; il documento viene elaborato al volo.

**Q: Posso concatenare più operazioni di ridimensionamento?**  
A: Assolutamente. Chiama `ResizeEps` in sequenza sulla stessa istanza di `PsDocument`.

**Q: Cosa succede alle immagini incorporate all'interno dell'EPS?**  
A: Vengono scalate proporzionalmente al contenuto vettoriale, preservando la qualità.

---

**Ultimo aggiornamento:** 2026-03-03  
**Testato con:** Aspose.Page 24.12 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}