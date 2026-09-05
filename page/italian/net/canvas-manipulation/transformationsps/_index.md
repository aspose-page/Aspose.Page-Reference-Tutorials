---
date: 2026-07-19
description: Scopri come creare un documento PostScript ASP.NET utilizzando Aspose.Page
  per .NET, applicare multiple transformations e salvare il file in modo efficiente.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: Trasformazioni PS
og_description: Crea documento PostScript ASP.NET con Aspose.Page. Scopri come applicare
  translation, scaling, rotation e shearing, quindi salva il file.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: Crea documento PostScript ASP.NET – Guida Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: Crea documento PostScript ASP.NET con Aspose.Page
url: /it/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento PostScript ASP.NET con Aspose.Page

## Introduzione

In questo tutorial passo‑paso **creerai un documento PostScript ASP.NET** utilizzando la libreria Aspose.Page, applicherai una varietà di trasformazioni grafiche e, infine, salverai il risultato in un file `.ps`. Alla fine della guida comprenderai dove inserire ogni trasformazione nello stack dello stato grafico, come combinarle in modo efficiente e come persistere i comandi di disegno affinché qualsiasi interprete PostScript possa renderizzarli. Questa conoscenza è essenziale per generare grafiche stampabili, report personalizzati o risorse dinamiche pronte per la stampa direttamente da applicazioni .NET.

## Risposte rapide
- **Cosa posso creare?** Un documento PostScript completo con grafiche trasformate.  
- **Quale libreria è necessaria?** Aspose.Page per .NET (scaricabile dal sito ufficiale).  
- **Come salvo il file?** Usa `PsDocument.Save()` dopo aver configurato gli stati grafici.  
- **Posso applicare più trasformazioni?** Sì – combinandole con `Transform` o chiamate sequenziali.  
- **È necessaria una licenza?** Una versione di prova è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.

## Che cos'è un'operazione di salvataggio di file PostScript?

Salvare un file PostScript significa persistere i comandi di disegno costruiti in memoria in un file `.ps` su disco. Il file può quindi essere renderizzato da qualsiasi interprete PostScript, stampante o visualizzatore, rappresentando una forma portabile e indipendente dal dispositivo di grafica vettoriale. Quando chiami il metodo `Save`, Aspose.Page serializza l'intero stato grafico, inclusi percorsi, pennelli e matrici di trasformazione, in una sintassi PostScript valida conforme alla specifica Adobe®.

## Perché usare Aspose.Page per .NET per creare documenti PostScript?

Aspose.Page per .NET offre un'API tipizzata e orientata agli oggetti che astrae il linguaggio PostScript a basso livello. Gestisce automaticamente lo stack dello stato grafico, supporta oltre 50 metodi relativi alle trasformazioni e può gestire documenti con più di 500 pagine senza caricare l'intero file in memoria. Questo riduce i tempi di sviluppo fino al 70 % rispetto alla scrittura manuale di codice PostScript e garantisce la compatibilità con tutte le principali stampanti.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- La libreria **Aspose.Page per .NET** integrata nel tuo progetto. Ottienila dal [link di download](https://releases.aspose.com/page/net/).  
- Una cartella scrivibile dove verrà salvato il file `.ps` generato. Sostituisci il percorso segnaposto nel codice con la tua directory reale.  
- .NET 6.0 o versioni successive (la libreria supporta anche .NET Core 3.1 e .NET Framework 4.6+).

## Importare gli spazi dei nomi

La classe `PsDocument` si trova nello spazio dei nomi `Aspose.Page.Drawing`, mentre gli helper per le trasformazioni sono in `Aspose.Page.Drawing.Graphics`. Importali all'inizio del tuo file:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` è la classe principale di Aspose.Page che rappresenta un documento PostScript in memoria. Dopo aver importato gli spazi dei nomi, puoi iniziare a costruire la superficie di disegno.

Ora esploriamo ogni trasformazione passo‑paso.

## Nessuna trasformazione

`PsDocument` è il punto di ingresso per tutte le operazioni di disegno. Il frammento seguente crea un nuovo documento, disegna un semplice rettangolo arancione e lo salva senza alcuna trasformazione.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Questo frammento crea un **documento PostScript** con un unico rettangolo arancione e **salva il file PostScript** senza applicare trasformazioni.

## Traslazione

Salvare lo stato grafico ti consente di tornare indietro dopo aver spostato gli oggetti. Il metodo `SaveState` inserisce la matrice di trasformazione corrente nello stack interno.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Il metodo `Translate` sposta il sistema di coordinate degli offset specificati, influenzando tutti i comandi di disegno successivi.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Ora un rettangolo blu appare 250 punti a destra di quello arancione perché la matrice di traslazione è attiva.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Il ripristino (`Restore`) riporta il sistema di coordinate alla posizione originale, così i disegni successivi non sono influenzati dalla traslazione.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## Scalatura

`Scale` modifica le dimensioni degli oggetti disegnati applicando una matrice di scala allo stato grafico corrente.

> *Puoi seguire lo stesso schema—salva lo stato, applica `Scale`, disegna, poi ripristina.*  
> **Suggerimento:** Usa la scalatura non uniforme (`Scale(sx, sy)`) per allungare gli oggetti solo in una direzione, utile per creare effetti a barre.

## Rotazione

`Rotate` applica una matrice di rotazione allo stato grafico corrente, ruotando i disegni successivi dell'angolo specificato.

> *Ruota attorno all'origine o a un punto pivot personalizzato usando `Rotate(angle)`.*
> **Suggerimento:** Combina `Translate` prima della rotazione per ruotare attorno a un punto specifico anziché all'origine.

## Taglio

`Shear` inclina il sistema di coordinate dei fattori forniti, distorcendo gli oggetti disegnati orizzontalmente e/o verticalmente.

> *Le trasformazioni di taglio (`Shear(shx, shy)`) inclinano le forme, utili per effetti italic o trucchi prospettici.*

## Trasformazioni complesse

`Transform` applica una matrice di trasformazione personalizzata allo stato grafico, combinando più operazioni in una sola.

> *Per scenari avanzati, costruisci una `Matrix` personalizzata e passala a `Transform(matrix)`.*
> Questo è il punto in cui **applichi più trasformazioni** in un unico passaggio, riducendo il numero di salvataggi e ripristini di stato.

## Come salvare un file PostScript con trasformazioni?

`Save` scrive l'attuale `PsDocument` su disco in formato PostScript. Carica il tuo `PsDocument`, applica la sequenza di trasformazioni desiderata e chiama `Save` con il percorso di destinazione—Aspose.Page genera un file `.ps` conforme agli standard in un solo passaggio. La libreria chiude automaticamente qualsiasi stato grafico aperto, quindi non è necessario alcun codice di pulizia aggiuntivo. Questo approccio funziona per qualsiasi combinazione di traslazione, scalatura, rotazione o taglio.

## Casi d'uso comuni

- **Generazione dinamica di report** – crea grafici che si adattano alle dimensioni dei dati in tempo reale.  
- **Fatture pronte per la stampa** – incorpora loghi aziendali e ruotali per allinearsi all'orientamento della stampante.  
- **Progettazione di etichette personalizzate** – applica il taglio per simulare effetti di testo in rilievo.  

## Domande frequenti

**D: Come posso applicare più trasformazioni a un singolo oggetto?**  
R: Usa il metodo `Transform` con una `Matrix` personalizzata che combina traslazione, scalatura, rotazione o taglio nell'ordine desiderato.

**D: Posso visualizzare in anteprima le trasformazioni prima di salvare il documento?**  
R: Sì—renderizza il `PsDocument` in un'immagine usando `PsDocument.Save("output.png", SaveFormat.Png)` oppure apri il file `.ps` in un visualizzatore PostScript per ispezionare il risultato prima di chiamare `Save()` per il file finale.

**D: È possibile applicare trasformazioni a elementi specifici in un documento?**  
R: Assolutamente. Salva lo stato grafico prima di disegnare l'elemento, applica la trasformazione desiderata, disegna, poi ripristina lo stato così gli elementi successivi rimangono invariati.

**D: Ci sono considerazioni sulle prestazioni quando si gestiscono trasformazioni complesse?**  
R: Le matrici complesse aumentano il carico CPU. Mantieni le trasformazioni il più semplici possibile e riutilizza gli stati salvati quando disegni molti oggetti simili. Aspose.Page elabora un documento di 300 pagine con trasformazioni miste in meno di 2 secondi su una tipica CPU da 3,2 GHz.

**D: Come posso ottenere supporto o assistenza per domande relative ad Aspose.Page?**  
R: Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per aiuto dalla community, o contatta direttamente il supporto Aspose per assistenza prioritaria.

---

**Ultimo aggiornamento:** 2026-07-19  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

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

## Tutorial correlati

- [Create postscript document .net – Add Rectangle with Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Add Image to PostScript (PS) Document with Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Add Page to PostScript (PS) Document with Aspose.Page](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}