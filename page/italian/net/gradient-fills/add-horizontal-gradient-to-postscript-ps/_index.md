---
date: 2026-02-25
description: Migliora i documenti PostScript con un rettangolo a gradiente lineare
  utilizzando Aspose.Page per .NET. Segui la nostra guida passo‑passo per imparare
  il riempimento a gradiente del testo e il gradiente del contorno del testo.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aggiungi un rettangolo con gradiente lineare a PostScript (PS) con Aspose.Page
url: /it/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere un rettangolo a gradiente lineare a PostScript (PS) con Aspose.Page

## Introduzione

Benvenuti a questo tutorial completo su come aggiungere un **rettangolo a gradiente lineare** ai documenti PostScript (PS) utilizzando Aspose.Page per .NET. Aspose.Page è una libreria potente che consente di creare, modificare e renderizzare documenti in una varietà di formati, e oggi ci concentreremo su come introdurre gradienti accattivanti nei vostri file PS.

### Risposte rapide
- **Che cosa fa il rettangolo a gradiente lineare?** Riempie un'area rettangolare con una transizione di colore fluida da un lato all'altro.  
- **Quale API gestisce il riempimento del testo con gradiente?** `LinearGradientBrush` combinato con `SetPaint` e `FillAndStrokeText`.  
- **Posso delineare il testo con un gradiente?** Sì—usa `SetStroke` con un pennello a gradiente e chiama `OutlineText`.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale di Aspose.Page per uso non di valutazione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Prerequisiti

Prima di immergerci, assicurati di avere:

- Aspose.Page for .NET Library: Assicurati che la libreria sia referenziata nel tuo progetto. Puoi scaricarla dalla [documentazione di Aspose.Page per .NET](https://reference.aspose.com/page/net/).
- Cartella dei documenti: Crea una cartella sul disco dove verrà salvato il file PS generato e sostituisci **“Your Document Directory”** nel codice con quel percorso.

## Importare gli spazi dei nomi

Per iniziare, importa gli spazi dei nomi che ti danno accesso alle classi di disegno e specifiche per PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Che cos'è un rettangolo a gradiente lineare?

Un **rettangolo a gradiente lineare** è semplicemente una forma rettangolare il cui interno è dipinto con un gradiente lineare—i colori passano gradualmente lungo una linea retta, tipicamente da sinistra a destra (orizzontale) o dall'alto verso il basso (verticale). In Aspose.Page ottieni questo combinando un `GraphicsPath` che definisce il rettangolo con un `LinearGradientBrush` che descrive la transizione di colore.

## Perché utilizzare il riempimento del testo con gradiente e il contorno del testo con gradiente?

- **Appeal visivo:** Il testo riempito con gradiente aggiunge profondità e uno stile moderno a report, fatture o materiali promozionali.  
- **Coerenza del brand:** Abbina i colori aziendali con valori ARGB precisi.  
- **Versatilità:** Lo stesso pennello può essere riutilizzato per riempimenti di forme, riempimenti di testo e gradienti di contorno, riducendo la duplicazione del codice.

## Passo 1: Configurare il documento

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 2: Definire il rettangolo a gradiente e i colori

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Passo 3: Impostare la trasformazione per il pennello

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Passo 4: Impostare il Paint e riempire il rettangolo

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Come applicare il riempimento del testo con gradiente

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Utilizzare il contorno del testo con gradiente

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Passo 7: Chiudere la pagina corrente e salvare il documento

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Congratulazioni! Hai aggiunto con successo un **rettangolo a gradiente lineare** a un documento PostScript e hai utilizzato lo stesso pennello per **riempimento del testo con gradiente** e per un **contorno del testo con gradiente**.

## Casistiche comuni e consigli

- **Intestazioni di report:** Riempire grandi blocchi di testo con gradienti per evidenziare i titoli delle sezioni.  
- **Loghi aziendali:** Ricreare forme di logo con forme riempite a gradiente per un branding coerente.  
- **Consiglio professionale:** Riutilizza la stessa istanza di `LinearGradientBrush` per più chiamate di disegno per mantenere i colori perfettamente allineati tra forme e testo.

## Domande frequenti

### Q1: Posso applicare gradienti ad altre forme oltre ai rettangoli?
**A:** Sì, puoi applicare gradienti a qualsiasi forma definita da un `GraphicsPath`. Basta aggiungere cerchi, poligoni o percorsi personalizzati prima di chiamare `document.Fill(path)`.

### Q2: Come posso cambiare i colori del gradiente?
**A:** Modifica i valori `Color.FromArgb` quando costruisci il `LinearGradientBrush`. Il primo colore è l'inizio, il secondo è la fine del gradiente.

### Q3: Aspose.Page è compatibile con diversi formati di documento?
**A:** Assolutamente. Aspose.Page supporta XPS, PS, PDF e diversi altri formati vettoriali. Controlla la documentazione ufficiale per l'elenco completo.

### Q4: Posso usare Aspose.Page per progetti commerciali?
**A:** Sì, è disponibile una licenza commerciale. Vedi la pagina di acquisto per i dettagli: [qui](https://purchase.aspose.com/buy).

### Q5: Dove posso trovare supporto dalla community?
**A:** Unisciti al forum della community di Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Ultimo aggiornamento:** 2026-02-25  
**Testato con:** Aspose.Page 24.10 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}