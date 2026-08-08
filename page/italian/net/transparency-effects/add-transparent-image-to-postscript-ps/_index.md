---
date: 2026-03-26
description: Scopri come creare un documento PostScript in .NET e aggiungere un'immagine
  trasparente usando Aspose.Page. Questa guida passo‑passo copre i prerequisiti, il
  codice e i suggerimenti.
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: Creare un documento PostScript .NET con immagine trasparente (Aspose.Page)
url: /it/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento PostScript .NET con immagine trasparente (Aspose.Page)

## Introduzione

In questo tutorial imparerai **come creare un documento PostScript .NET** e incorporare un PNG trasparente usando Aspose.Page per .NET. Aggiungere immagini trasparenti ti consente di creare grafiche più ricche e stratificate—perfette per filigrane, sovrapposizioni o mock‑up UI all'interno di un file PS. Ti guideremo passo passo, dalla configurazione dell'ambiente al rendering di immagini sia opache che trasparenti.

## Risposte rapide
- **Cosa fa Aspose.Page?** Fornisce un'API completa per generare, modificare e renderizzare documenti PostScript (PS) e XPS in .NET.  
- **Posso aggiungere PNG trasparenti?** Sì—usa `DrawTransparentImage` per controllare l'opacità.  
- **Quali versioni di .NET sono supportate?** Tutte le recenti versioni di .NET Framework, .NET Core e .NET 5/6.  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per la valutazione; è richiesta una licenza per la produzione.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio base.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Aspose.Page per .NET** – scaricalo dal [download link](https://releases.aspose.com/page/net/).  
- Una cartella in cui conservare il documento PS e l'immagine da incorporare.  
- Un PNG traslucido (ad es. `mask1.png`) che verrà usato per lo strato trasparente.

## Importa spazi dei nomi

Per prima cosa, importa gli spazi dei nomi che contengono le classi di cui avremo bisogno. Questo ci dà accesso al modello di documento PS, alle utility grafiche e ai tipi di disegno .NET di base.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Passo 1: Configura la directory del documento

Definisci il percorso dove risiederanno l'immagine di origine e il file PS di output. Sostituisci il segnaposto con il percorso reale sul tuo computer.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Passo 2: Crea lo stream di output per il documento PostScript

Scriveremo il contenuto PS generato in uno stream di file. Questo stream verrà poi passato al costruttore `PsDocument`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## Passo 3: Imposta le opzioni di salvataggio e il colore di sfondo

Configura `PsSaveOptions` per definire come il file viene salvato. Impostare un colore di sfondo è utile quando desideri una tela solida dietro gli elementi trasparenti.

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## Passo 4: Crea un nuovo documento PS a 1 pagina

Crea il documento usando lo stream e le opzioni definite sopra. Il flag `false` indica ad Aspose.Page di non chiudere automaticamente lo stream.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 5: Salva lo stato grafico e trasla

Prima di disegnare, salviamo lo stato grafico corrente e trasliamo l'origine in modo che le nostre immagini appaiano nella posizione desiderata sulla pagina.

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## Come aggiungere un'immagine trasparente a un documento PostScript

### Passo 6: Aggiungi immagine RGB opaca

Per prima cosa aggiungiamo lo stesso PNG come immagine opaca normale. Questo dimostra la differenza visiva quando successivamente applichiamo la trasparenza.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### Passo 7: Aggiungi immagine trasparente

Ora usiamo `DrawTransparentImage` per renderizzare il PNG con un valore di opacità. Il terzo parametro (`255`) rappresenta opacità piena; valori più bassi aumentano la trasparenza. Qui è dove **impostiamo la trasparenza dell'immagine .NET**.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **Suggerimento:** Per rendere l'immagine trasparente al 50 %, passa `128` invece di `255`.

## Passo 8: Ripristina lo stato grafico e chiudi la pagina

Dopo il disegno, ripristina lo stato grafico precedente e chiudi la pagina per finalizzare il contenuto.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Passo 9: Salva il documento

Infine, salva il file PS su disco.

```csharp
document.Save();
```

Seguendo questi passaggi hai **creato un documento PostScript .NET** che contiene sia un'immagine opaca sia una trasparente, mostrando come **disegnare un'immagine trasparente C#** con Aspose.Page.

## Perché usare Aspose.Page per effetti di trasparenza?

- **Controllo totale** sullo stato grafico, matrici e livelli di opacità.  
- **Nessuna dipendenza esterna**—tutto gira all'interno di puro codice .NET.  
- **Supporto cross‑platform** ti consente di generare file PS su Windows, Linux o macOS.

## Problemi comuni e risoluzione

| Problema | Soluzione |
|----------|-----------|
| L'immagine appare completamente opaca anche dopo `DrawTransparentImage` | Assicurati che il valore alpha (terzo argomento) sia inferiore a `255`. |
| Il file PS mostra una pagina vuota | Verifica che il colore di sfondo sia impostato e che il percorso dello stream sia corretto. |
| Eccezione “File not found” | Controlla nuovamente `dataDir` e che `mask1.png` esista in quella cartella. |

## Domande frequenti

**D: Posso usare altri formati immagine oltre PNG per la trasparenza?**  
R: Sì—Aspose.Page supporta PNG, GIF e TIFF per il rendering trasparente.

**D: Aspose.Page è compatibile con l'ultima versione del framework .NET?**  
R: Assolutamente. La libreria è regolarmente aggiornata per .NET 6, .NET 7 e versioni successive.

**D: Posso applicare la trasparenza a un documento PS esistente?**  
R: Sì. Apri il documento con `PsDocument`, aggiungi una nuova pagina o modifica una esistente, poi usa lo stesso approccio `DrawTransparentImage`.

**D: Quali vantaggi offre Aspose.Page rispetto alle librerie grafiche generiche?**  
R: È progettato appositamente per PS/XPS, offrendo un controllo preciso su grafica vettoriale, font e gestione delle immagini senza necessità di un motore di rendering completo.

**D: Ci sono limiti al livello di trasparenza che posso impostare?**  
R: No. Puoi specificare qualsiasi valore alpha da `0` (completamente trasparente) a `255` (completamente opaco).

## Conclusione

Abbiamo dimostrato come **creare un documento PostScript .NET** e incorporare sia immagini opache che trasparenti usando Aspose.Page. Questa tecnica apre la porta a layout di documenti sofisticati, filigrane e grafiche a strati—tutto generato programmaticamente da C#.

---

**Ultimo aggiornamento:** 2026-03-26  
**Testato con:** Aspose.Page 24.12 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}