---
date: 2026-02-23
description: Scopri come aggiungere un gradiente ai file PostScript, salvare il file
  PostScript con dimensione pagina A4 e riempire un rettangolo con gradiente utilizzando
  Aspose.Page per .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Come aggiungere un gradiente – Gradiente diagonale in PostScript (PS) con Aspose.Page
  .NET
url: /it/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un gradiente: gradiente diagonale a PostScript (PS) con Aspose.Page .NET

## Introduzione

Aggiungere un gradiente diagonale a un documento PostScript (PS) può migliorare notevolmente l'appeal visivo, soprattutto quando è necessario **come aggiungere gradiente** effetti nei report tecnici, brochure o applicazioni ad alta intensità grafica. In questo tutorial vedrai esattamente come aggiungere un gradiente a un file PostScript, impostare una dimensione di pagina A4 e riempire un rettangolo con una transizione di colore fluida usando Aspose.Page per .NET.

## Risposte rapide
- **Qual è la libreria richiesta?** Aspose.Page for .NET  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Posso cambiare la direzione del gradiente?** Sì – ruota la trasformazione del pennello come mostrato nel codice  
- **Come salvo il risultato?** Usa `PsDocument.Save()` che scrive un file PostScript su disco  
- **È necessaria una licenza per la produzione?** Sì, una licenza commerciale sblocca tutte le funzionalità  

## Cos'è un gradiente diagonale in PostScript?

Un gradiente diagonale è una transizione di colore lineare che corre ad un angolo (tipicamente 45°) attraverso una forma. In PostScript, ciò si ottiene applicando un `LinearGradientBrush` con una matrice di trasformazione personalizzata che ruota, scala e trasla il gradiente per corrispondere al rettangolo desiderato.

## Perché usare Aspose.Page per riempimenti a gradiente?

Aspose.Page astrae i comandi PostScript a basso livello, consentendoti di lavorare con oggetti grafici .NET familiari. Puoi creare riempimenti complessi, impostare le dimensioni della pagina ed esportare direttamente a un **save PostScript file** senza dover gestire la sintassi PS grezza.

## Prerequisiti

- **Aspose.Page for .NET Library** – scaricala [qui](https://releases.aspose.com/page/net/).  
- **Document Directory** – una cartella dove verrà scritto il file `*.ps` generato.

Ora che abbiamo coperto le basi, procediamo passo passo attraverso l'implementazione.

## Importa spazi dei nomi

Per prima cosa, importa gli spazi dei nomi che ti danno accesso al dispositivo EPS, alle utility di disegno e alle classi I/O.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Passo 1: Crea lo stream di output per il documento PostScript (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Passo 2: Imposta la dimensione della pagina A4 (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Passo 3: Crea un nuovo documento PS a 1 pagina

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 4: Definisci i parametri del rettangolo

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Passo 5: Crea il percorso grafico

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Passo 6: Crea il pennello a gradiente lineare (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Passo 7: Crea la trasformazione per il pennello

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Passo 8: Applica le trasformazioni al pennello (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Passo 9: Imposta la trasformazione sul pennello

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Passo 10: Imposta il colore e riempi il rettangolo

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Passo 11: Chiudi la pagina corrente

```csharp
	//Close current page
	document.ClosePage();
```

## Passo 12: Salva il documento (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Come salvare il file PostScript

La chiamata `PsDocument.Save()` scrive il contenuto PostScript completo nello stream aperto nel **Passo 1**. Dopo il completamento del blocco `using`, il file `DiagonaGradient_outPS.ps` sarà disponibile nella directory specificata.

## Casi d'uso comuni

- **Technical documentation** che necessita di una sfumatura di sfondo sottile.  
- **Marketing brochures** dove un gradiente diagonale aggiunge un aspetto moderno.  
- **Automated report generators** che producono file PS stampabili al volo.  

## Risoluzione dei problemi e consigli

- **Incorrect colors** – verifica i valori ARGB passati a `LinearGradientBrush`.  
- **Gradient not visible** – assicurati che la matrice di trasformazione ruoti e scala correttamente; la chiamata `Rotate(-45)` imposta l'angolo diagonale.  
- **File not created** – verifica che `dataDir` punti a una cartella esistente e che l'applicazione abbia i permessi di scrittura.  

## Domande frequenti

**Q: Aspose.Page è compatibile con tutti i framework .NET?**  
A: Aspose.Page supporta un'ampia gamma di versioni .NET, dal .NET Framework 4.5+ al .NET 6+, garantendo una vasta compatibilità.

**Q: Posso personalizzare i colori del gradiente in Aspose.Page?**  
A: Sì, puoi specificare qualsiasi colore ARGB quando costruisci `LinearGradientBrush`, dandoti il pieno controllo sui colori di inizio e fine.

**Q: È disponibile una versione di prova per Aspose.Page?**  
A: Sì, puoi esplorare le funzionalità di Aspose.Page scaricando la versione di prova [qui](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per Aspose.Page?**  
A: Ottieni una licenza temporanea per Aspose.Page [qui](https://purchase.aspose.com/temporary-license/) per sbloccare funzionalità aggiuntive durante la valutazione.

**Q: Dove posso trovare supporto della community per Aspose.Page?**  
A: Interagisci con la community di Aspose.Page sul [forum](https://forum.aspose.com/c/page/39) per assistenza e discussioni.

---

**Ultimo aggiornamento:** 2026-02-23  
**Testato con:** Aspose.Page for .NET (latest stable release)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}