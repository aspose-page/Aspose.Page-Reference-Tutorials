---
title: Applica il motivo di piastrellatura della trama a PostScript (PS) con Aspose.Page
linktitle: Applica motivo di affiancamento texture a PostScript (PS)
second_title: API Aspose.Page .NET
description: Migliora i tuoi documenti PostScript (PS) con modelli di piastrellatura di texture utilizzando Aspose.Page per .NET. Segui la nostra guida passo passo per un tocco creativo.
weight: 10
url: /it/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Applica il motivo di piastrellatura della trama a PostScript (PS) con Aspose.Page

## introduzione

Benvenuti in questo tutorial passo passo su come applicare un modello di piastrellatura della trama a un documento PostScript (PS) utilizzando Aspose.Page per .NET. Aspose.Page è una potente libreria che ti consente di lavorare con vari formati di documenti e in questo tutorial esploreremo come migliorare i tuoi documenti PS aggiungendo modelli di piastrellatura delle texture.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di avere quanto segue:

- [Studio visivo](https://visualstudio.microsoft.com/) installato sulla tua macchina.
- Conoscenza base della programmazione C#.
-  Scarica e installa il[Aspose.Page per la libreria .NET](https://releases.aspose.com/page/net/).
- Un file immagine per il modello di texture (ad esempio, "TestTexture.bmp").

## Importa spazi dei nomi

Nel codice C# assicurati di importare gli spazi dei nomi necessari:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Suddividiamo l'esempio fornito in più passaggi per guidarti attraverso il processo.

## Passaggio 1: impostare la directory dei documenti

```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
```

Assicurati di sostituire "La tua directory dei documenti" con il percorso in cui desideri salvare il tuo documento PS.

## Passaggio 2: crea il flusso di output per il documento PS

```csharp
// Crea flusso di output per il documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Crea opzioni di salvataggio con il formato A4
    PsSaveOptions options = new PsSaveOptions();

    // Crea un nuovo documento PS di 1 pagina
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Questo passaggio configura il flusso di output per il documento PS, inclusa la definizione della dimensione del documento.

## Passaggio 3: applicare il motivo di piastrellatura della trama

```csharp
// Crea un oggetto Bitmap dal file immagine
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Crea un pennello texture dall'immagine
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Aggiungi il ridimensionamento nella direzione X al modello
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Imposta questo pennello texture come vernice corrente
    document.SetPaint(brush);
}
```

Questo passaggio prevede la creazione di un pennello texture da un'immagine e l'impostazione come disegno corrente per il documento.

## Passaggio 4: crea un percorso rettangolare e riempilo

```csharp
// Crea un percorso rettangolare
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Riempi il rettangolo
document.Fill(path);
```

Qui definiamo un tracciato rettangolare e lo riempiamo con il pennello texture precedentemente impostato.

## Passaggio 5: imposta tratto e disegno

```csharp
// Ottieni la vernice attuale
Brush paint = document.GetPaint();

// Imposta il tratto rosso
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Traccia il rettangolo
document.Draw(path);
```

Questo passaggio prevede l'impostazione delle proprietà del tratto e il disegno del rettangolo delineato.

## Passaggio 6: riempire e delineare il testo con il motivo texture

```csharp
// Riempi il testo con un motivo a trama
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Testo del contorno con motivo a trama
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Infine, riempiamo e delineamo il testo con il motivo texture, migliorando l'impatto visivo del tuo documento.

## Passaggio 7: salva e chiudi il documento

```csharp
// Chiudi la pagina corrente
document.ClosePage();

// Salva il documento
document.Save();
```

Assicurati di chiudere la pagina corrente e salvare il documento per applicare le modifiche.

## Conclusione

Congratulazioni! Hai imparato con successo come applicare un modello di piastrellatura della trama a un documento PostScript utilizzando Aspose.Page per .NET. Sperimenta immagini e modelli diversi per personalizzare ulteriormente i tuoi documenti PS.

## Domande frequenti

### Q1: Posso utilizzare altri formati di immagine per il motivo della trama?

A1: Sì, Aspose.Page supporta vari formati di immagine. Garantire la compatibilità con la documentazione della biblioteca.

### Q2: Aspose.Page è compatibile con .NET Core?

A2: Sì, Aspose.Page è compatibile sia con .NET Framework che con .NET Core.

### Q3: Come posso regolare la dimensione del rettangolo con texture?

 A3: Modifica le dimensioni in`RectangleF` parametri durante la creazione del percorso.

### Q4: Posso aggiungere più motivi di texture a un singolo documento?

R4: Sì, puoi ripetere il processo con immagini e percorsi diversi.

### Q5: Dove posso trovare risorse e supporto aggiuntivi?

 A5: Visita il[Aspose.Page Forum](https://forum.aspose.com/c/page/39) per il supporto della comunità ed esplorare il[documentazione](https://reference.aspose.com/page/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
