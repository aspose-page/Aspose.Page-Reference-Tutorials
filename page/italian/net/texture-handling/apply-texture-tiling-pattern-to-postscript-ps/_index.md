---
date: 2026-03-26
description: Scopri come creare documenti PostScript .NET con pattern di piastrellatura
  di texture usando Aspose.Page. Segui la nostra guida passo‑passo per aggiungere
  texture ricche ai tuoi file PS.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Crea documento PostScript .NET con tessellazione di texture
url: /it/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento PostScript .NET con piastrellatura di texture

## Come creare un documento PostScript .NET con piastrellatura di texture

In questo tutorial imparerai a **creare un documento PostScript .NET** e ad arricchirlo con un motivo di piastrellatura di texture usando la libreria Aspose.Page. Ti guideremo passo dopo passo, dalla configurazione del progetto al riempimento e al contorno del testo con il pennello texture, così potrai produrre file PS visivamente accattivanti in pochi minuti.

## Risposte rapide
- **Quale libreria viene usata?** Aspose.Page per .NET  
- **Posso usare .NET Core?** Sì, la libreria supporta .NET Core e .NET 5/6  
- **Quali formati immagine funzionano per la texture?** Qualsiasi formato supportato da System.Drawing (BMP, PNG, JPEG, ecc.)  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio base  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza per la produzione  

## Prerequisiti

- [Visual Studio](https://visualstudio.microsoft.com/) installato sulla tua macchina.  
- Conoscenza di base della programmazione C#.  
- Scarica e installa la [libreria Aspose.Page per .NET](https://releases.aspose.com/page/net/).  
- Un file immagine per il motivo di texture (ad es., **TestTexture.bmp**).

## Importare gli spazi dei nomi

Nel tuo file C#, importa gli spazi dei nomi necessari affinché il compilatore sappia dove trovare i tipi che utilizzeremo:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Passo 1: Configurare la directory del documento

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Sostituisci **Your Document Directory** con la cartella in cui desideri salvare il file PS generato.

## Passo 2: Creare lo stream di output per il documento PS

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Questo blocco apre uno stream di file, configura la dimensione della pagina (A4 per impostazione predefinita) e crea una nuova istanza **PsDocument** su cui disegneremo.

## Passo 3: Applicare il motivo di piastrellatura di texture

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Qui carichiamo il bitmap, lo avvolgiamo in un **TextureBrush**, opzionalmente lo allunghiamo orizzontalmente e indichiamo al **PsDocument** di usare questo pennello per le operazioni di disegno successive.

## Passo 4: Creare il percorso rettangolare e riempirlo

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Viene definito un semplice rettangolo e riempito con il pennello texture impostato in precedenza.

## Passo 5: Impostare il contorno e disegnare

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Recuperiamo il paint corrente (il pennello texture), creiamo una penna rossa per il contorno e disegniamo il bordo del rettangolo.

## Passo 6: Riempire e tracciare il testo con il motivo di texture

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Questo passo dimostra la capacità di **riempire e tracciare il testo**: i caratteri “ABC” sono riempiti con il pennello texture e poi contornati, creando un effetto visivo sorprendente.

## Passo 7: Salvare e chiudere il documento

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

La chiusura della pagina finalizza i comandi di disegno e `Save()` scrive il file PostScript su disco.

## Problemi comuni e soluzioni

- **La texture appare allungata in modo errato** – Regola i valori della `Matrix` per controllare la scala nelle direzioni X/Y.  
- **Immagine non trovata** – Verifica che `dataDir` punti alla cartella corretta e che il nome del file corrisponda esattamente, compresa la differenza tra maiuscole e minuscole.  
- **I colori sembrano sbagliati** – Ricorda che PostScript utilizza uno spazio colore indipendente dal dispositivo; assicurati di usare oggetti `Color` che vengano mappati correttamente.

## Domande frequenti

**D:** Posso usare altri formati immagine per il motivo di texture?  
**R:** Sì, qualsiasi formato supportato da `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF, ecc.) funziona.

**D:** Aspose.Page è compatibile con .NET Core?  
**R:** Assolutamente. La libreria funziona su .NET Framework, .NET Core e .NET 5/6.

**D:** Come faccio a cambiare le dimensioni del rettangolo texturizzato?  
**R:** Modifica i valori di `RectangleF` nel passo di creazione del rettangolo (ad es., `new RectangleF(0, 0, 300, 150)`).

**D:** Posso applicare più motivi di texture in un unico documento?  
**R:** Sì. Basta creare un nuovo `TextureBrush` con un’immagine diversa e chiamare nuovamente `SetPaint` prima di disegnare la forma o il testo successivo.

**D:** Dove posso trovare altri esempi e la reference dell'API?  
**R:** Visita il [Forum Aspose.Page](https://forum.aspose.com/c/page/39) per l’aiuto della community e la [documentazione ufficiale](https://reference.aspose.com/page/net/) per un uso dettagliato dell’API.

## Conclusione

Ora sai come **creare un documento PostScript .NET** e applicare un motivo di piastrellatura di texture, inclusa la capacità di **riempire e tracciare il testo** con quella texture. Sperimenta con immagini diverse, matrici di scala e primitive di disegno per produrre file PS dal design personalizzato per report, volantini o qualsiasi output grafico intensivo.

---

**Ultimo aggiornamento:** 2026-03-26  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}