---
date: 2026-03-29
description: Scopri come utilizzare un pennello a gradiente lineare in C# per creare
  pseudo‑trasparenza in PostScript con Aspose.Page per .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Pennello a Gradiente Lineare C# per Pseudo‑trasparenza in PS
url: /it/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pennello a Gradiente Lineare C# per Pseudo‑Trasparenza in PostScript (PS)

## Introduzione

Se hai bisogno di aggiungere un effetto di trasparenza sottile ai tuoi file PostScript (PS), il **linear gradient brush C#** è lo strumento perfetto. Aspose.Page per .NET semplifica la pittura di rettangoli con riempimenti a gradiente sia opachi che traslucidi, conferendo ai tuoi documenti un aspetto moderno e stratificato. In questo tutorial illustreremo passo passo le operazioni necessarie per creare una pseudo‑trasparenza usando un linear gradient brush in C#.

## Risposte Rapide
- **Quale libreria fornisce il linear gradient brush?** Aspose.Page for .NET
- **Quale classe grafica crea il gradiente?** `LinearGradientBrush`
- **Posso controllare l'opacità per colore?** Yes, using `Color.FromArgb(alpha, …)`
- **È necessaria una licenza per la produzione?** A valid Aspose.Page license is required
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Cos'è un linear gradient brush C#?

`LinearGradientBrush` è un oggetto GDI+ che dipinge una transizione fluida tra due colori lungo una linea retta. Quando specifichi il canale alfa (0‑255) per ogni colore, puoi creare gradienti traslucidi — esattamente ciò di cui abbiamo bisogno per la pseudo‑trasparenza in PostScript.

## Perché usare un linear gradient brush C# per la pseudo‑trasparenza?

- **Controllo fine dell'opacità:** Regola l'alfa di ogni colore per ottenere il livello di trasparenza desiderato.  
- **Rendering indipendente dal dispositivo:** Il pennello funziona allo stesso modo su schermo, PDF, EPS e output PS.  
- **API semplice:** Poche righe di codice C# producono effetti visivi di livello professionale.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

- Aspose.Page per .NET installato. Puoi scaricarlo dalla [documentazione Aspose.Page](https://reference.aspose.com/page/net/).
- Una cartella scrivibile dove verrà salvato il documento PostScript generato.

Ora che hai gli strumenti necessari, iniziamo a creare i rettangoli pseudo‑trasparenti.

## Importa Namespace

Prima di iniziare, importa i namespace che contengono le classi che utilizzeremo:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Passo 1: Crea lo stream di output per il documento PostScript

Iniziamo creando uno stream di file che conterrà il file PS risultante, quindi inizializziamo il `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 2: Crea un rettangolo con un riempimento a gradiente **opaco**

Qui creiamo un `LinearGradientBrush` i cui colori sono completamente opachi (alpha = 255). Questo rettangolo servirà come livello di sfondo.

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

## Passo 3: Crea un rettangolo con un riempimento a gradiente **traslucido**

Ora utilizziamo un **linear gradient brush C#** con valori alfa inferiori a 255 (ad esempio 150 e 50). Questo rende il rettangolo parzialmente trasparente, ottenendo l'effetto di pseudo‑trasparenza.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Passo 4: Chiudi la pagina e salva il documento

Infine completiamo la pagina e scriviamo il file PS su disco.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Seguendo questi quattro passaggi puoi fondere senza soluzione di continuità rettangoli opachi e traslucidi, creando un convincente effetto pseudo‑trasparente in qualsiasi output PostScript.

## Problemi Comuni e Soluzioni

| Problema | Perché accade | Correzione |
|----------|----------------|------------|
| I colori appaiono completamente opachi | Valore alfa impostato a 255 per errore | Use `Color.FromArgb(alpha, …)` with `alpha` < 255 |
| Il gradiente è deformato in modo errato | Matrice di trasformazione errata | Verify the matrix parameters match the rectangle dimensions |
| Il file di output è vuoto | Stream non chiuso o `Save()` non chiamato | Ensure `document.ClosePage()` and `document.Save()` are executed inside the `using` block |

## Domande Frequenti

**Q: Aspose.Page è compatibile con tutte le versioni di .NET?**  
A: Aspose.Page per .NET è compatibile con varie versioni del framework .NET, garantendo flessibilità e facilità di integrazione.

**Q: Posso applicare la pseudo‑trasparenza ad altre forme oltre ai rettangoli?**  
A: Sì, gli stessi principi possono essere applicati a qualsiasi forma regolando di conseguenza il `GraphicsPath`.

**Q: Dove posso trovare esempi e documentazione aggiuntivi?**  
A: Esplora la [documentazione Aspose.Page](https://reference.aspose.com/page/net/) per esempi completi e riferimenti API dettagliati.

**Q: È disponibile una versione di prova gratuita per Aspose.Page?**  
A: Sì, puoi accedere a una prova gratuita di Aspose.Page da [questo link](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per Aspose.Page?**  
A: Visita [questo link](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea per Aspose.Page.

---

**Ultimo Aggiornamento:** 2026-03-29  
**Testato Con:** Aspose.Page 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}