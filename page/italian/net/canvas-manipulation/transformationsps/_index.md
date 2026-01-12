---
date: 2026-01-12
description: Scopri come salvare un file PostScript e creare un documento PostScript
  usando Aspose.Page per .NET, e applicare più trasformazioni per grafica dinamica.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Salva file PostScript con le trasformazioni di Aspose.Page (.NET)
url: /it/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva file PostScript con le trasformazioni Aspose.Page (.NET)

## Introduzione

In questo tutorial scoprirai come **salvare un file PostScript** lavorando con Aspose.Page per .NET. Vedremo come creare un documento PostScript, applicare più trasformazioni come traslazione, scalatura, rotazione e inclinazione, e infine salvare il risultato. Alla fine sarai in grado di creare grafiche dinamiche programmaticamente e saprai esattamente dove posizionare ogni trasformazione nello stato grafico.

## Risposte rapide
- **Cosa posso creare?** Un documento PostScript completo con grafiche trasformate.  
- **Quale libreria è necessaria?** Aspose.Page per .NET (scaricabile dal sito ufficiale).  
- **Come salvo il file?** Usa `PsDocument.Save()` dopo aver configurato gli stati grafici.  
- **Posso applicare più trasformazioni?** Sì – combinandole con `Transform` o chiamate sequenziali.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.

## Che cos'è un'operazione di “salvataggio file PostScript”?

Salvare un file PostScript significa persistere i comandi di disegno che hai costruito in memoria in un file `.ps` su disco. Il file può quindi essere renderizzato da qualsiasi interprete PostScript, stampante o visualizzatore.

## Perché usare Aspose.Page per .NET per creare un documento PostScript?

Aspose.Page fornisce un'API di alto livello, indipendente dal dispositivo, che astrae la sintassi di basso livello del PostScript. Ottieni:

- Oggetti C# tipizzati per percorsi, pennelli e trasformazioni.  
- Gestione automatica dello stack dello stato grafico (save/restore).  
- Supporto completo per matrici di trasformazione complesse senza calcoli manuali.  

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Libreria Aspose.Page per .NET** integrata nel tuo progetto. Scaricala dal [download link](https://releases.aspose.com/page/net/).  
- Una cartella scrivibile dove verrà salvato il file `.ps` generato. Sostituisci il percorso segnaposto nel codice con la tua directory reale.

## Importa spazi dei nomi

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ora esploriamo ogni passaggio di trasformazione passo‑per‑passo.

## Nessuna trasformazione

### Passo 1: Crea stream di output

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Questo frammento crea un **documento PostScript** con un unico rettangolo arancione e **salva il file PostScript** senza applicare alcuna trasformazione.

## Traslazione

### Passo 1: Salva stato grafico

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Salvare lo stato grafico ti permette di tornare indietro dopo aver spostato gli oggetti.

### Passo 2: Trasla stato grafico

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

La traslazione sposta tutto ciò che viene disegnato dopo questa chiamata di 250 unità verso destra.

### Passo 3: Riempi rettangolo con trasformazione di traslazione

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Ora un rettangolo blu appare 250 punti a destra di quello arancione.

### Passo 4: Ripristina stato grafico

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Il ripristino riporta il sistema di coordinate alla sua posizione originale, così i disegni successivi non sono influenzati dalla traslazione.

## Scalatura

> *Puoi seguire lo stesso schema—salva lo stato, applica `Scale`, disegna, poi ripristina.*  
> **Suggerimento:** Usa la scalatura non uniforme (`Scale(sx, sy)`) per allungare gli oggetti solo in una direzione.

## Rotazione

> *Ruota attorno all'origine o a un punto di pivot personalizzato usando `Rotate(angle)`. *  
> **Suggerimento:** Combina `Translate` prima della rotazione per ruotare attorno a un punto specifico.

## Inclinazione

> *Le trasformazioni di inclinazione (`Shear(shx, shy)`) inclinano le forme, utili per effetti in corsivo.*  

## Trasformazioni complesse

> *Per scenari avanzati, crea una `Matrix` personalizzata e passala a `Transform(matrix)`. *  
> Qui è dove **applichi più trasformazioni** in un unico passaggio.

## Conclusione

Hai imparato come **salvare un file PostScript**, **creare un documento PostScript** e **applicare più trasformazioni** usando Aspose.Page per .NET. Sperimenta con diversi ordini di trasformazione, combinandoli, e osserva come le grafiche evolvono.

## Domande frequenti

**D: Come posso applicare più trasformazioni a un singolo oggetto?**  
R: Usa il metodo `Transform` con una `Matrix` personalizzata che combina traslazione, scalatura, rotazione o inclinazione nell'ordine necessario.

**D: Posso visualizzare in anteprima le trasformazioni prima di salvare il documento?**  
R: Sì—renderizza il `PsDocument` in un'immagine o usa un visualizzatore PostScript per ispezionare l'output prima di chiamare `Save()`.

**D: È possibile applicare trasformazioni a elementi specifici in un documento?**  
R: Assolutamente. Salva lo stato grafico prima di disegnare l'elemento, applica la trasformazione desiderata, disegna, poi ripristina lo stato.

**D: Ci sono considerazioni sulle prestazioni quando si gestiscono trasformazioni complesse?**  
R: Le matrici complesse aumentano il carico CPU. Mantieni le trasformazioni il più semplici possibile e riutilizza gli stati salvati quando disegni molti oggetti simili.

**D: Come posso ottenere supporto o assistenza per domande relative ad Aspose.Page?**  
R: Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per aiuto dalla community, o contatta direttamente il supporto Aspose.

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}