---
date: 2026-03-03
description: Scopri come utilizzare Aspose.Page per .NET per disporre a mosaico le
  immagini nei documenti XPS. Questa guida passo passo mostra come disporre le immagini
  in modo efficiente e migliorare l'appeal visivo.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Come usare Aspose.Page per aggiungere un'immagine a tasselli a un documento
  XPS
url: /it/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare Aspose.Page per aggiungere un'immagine a tasselli a un documento XPS

## Introduzione

Se ti stai chiedendo **come usare Aspose** per dare ai tuoi file XPS uno stile visivo più ricco, sei nel posto giusto. In questo tutorial vedremo passo passo i passaggi necessari per **tassellare un'immagine** all'interno di un documento XPS usando Aspose.Page per .NET. Alla fine avrai uno snippet riutilizzabile da inserire in qualsiasi progetto .NET per creare grafiche con immagine a tasselli al volo.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for .NET  
- **Quale metodo crea il pennello a tasselli?** `CreateImageBrush` con `TileMode = XpsTileMode.Tile`  
- **Posso controllare l'opacità?** Sì – imposta `path.Fill.Opacity` (ad es., 0.5f)  
- **Ho bisogno di una licenza per i test?** Una licenza temporanea funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Cos'è Aspose.Page e perché tassellare le immagini?

Aspose.Page è un'API potente che consente agli sviluppatori di generare, modificare e renderizzare XPS, PDF e altri formati basati su pagine senza dipendere da Microsoft Office. Tassellare un'immagine—ripetere una bitmap su una forma—ti aiuta a riempire ampie aree con motivi, filigrane o texture di sfondo mantenendo ridotto il peso del file.

## Come utilizzare Aspose.Page per tassellare le immagini nei documenti XPS

Di seguito trovi un esempio completo, pronto per l'esecuzione. Ogni passaggio è spiegato in linguaggio semplice prima del relativo blocco di codice, così puoi capire **perché** ogni riga è importante.

### Prerequisiti

- **Aspose.Page for .NET** – scarica e aggiungi il riferimento alla libreria dal sito ufficiale [qui](https://reference.aspose.com/page/net/).  
- **Ambiente di sviluppo** – Visual Studio (qualsiasi edizione) o un altro IDE .NET a tua scelta.

### Importare i namespace

Per prima cosa, importa i namespace necessari in modo che il compilatore sappia dove trovare le classi XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Passo 1: Definire la directory del documento

Specifica dove verranno salvati il file XPS generato e l'immagine di origine. Sostituisci il segnaposto con una cartella reale sul tuo computer.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Passo 2: Creare un nuovo documento XPS

Istanzia un documento XPS vuoto che conterrà la grafica a tasselli.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Passo 3: Aggiungere un'immagine a tasselli

Qui creiamo un percorso rettangolare, lo riempiamo con un `ImageBrush` e impostiamo il pennello in modalità tassello. La proprietà `TileMode` indica al motore di ripetere l'immagine sia orizzontalmente sia verticalmente. Regola le coordinate del rettangolo o l'immagine di origine secondo le tue esigenze.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Passo 4: Salvare il documento XPS risultante

Infine, scrivi il documento su disco. Il file di output può essere aperto con qualsiasi visualizzatore XPS o ulteriormente elaborato con Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Problemi comuni e suggerimenti

- **Errori di percorso** – Assicurati che `dataDir` termini con una barra finale o utilizza `Path.Combine` per evitare problemi di separatore mancante.  
- **Discrepanze nelle dimensioni dell'immagine** – L'immagine di origine deve essere sufficientemente grande per l'area di tassellatura; altrimenti il motivo potrebbe apparire allungato.  
- **Opacità non visibile** – Alcuni visualizzatori ignorano l'opacità su XPS; prova con un visualizzatore che supporti pienamente il rendering XPS (ad es., XPS Viewer su Windows).

## Domande frequenti

### Q1: Aspose.Page è compatibile con tutti gli ambienti di sviluppo .NET?
A: Sì, Aspose.Page funziona con Visual Studio, Rider, VS Code e qualsiasi IDE che supporti .NET.

### Q2: Posso regolare l'opacità dell'immagine a tasselli?
A: Assolutamente. L'esempio imposta `path.Fill.Opacity = 0.5f;`—puoi modificare il valore float tra 0 (trasparente) e 1 (opaco).

### Q3: Esistono altri modalità di tassellatura disponibili in Aspose.Page per .NET?
A: Sì. Oltre a `XpsTileMode.Tile`, puoi usare `FlipX`, `FlipY` e `FlipXY` per creare motivi specchiati.

### Q4: Come gestire le licenze temporanee per Aspose.Page?
A: Consulta la pagina della [licenza temporanea](https://purchase.aspose.com/temporary-license/) sul sito Aspose per i dettagli su come ottenere e applicare una licenza di prova.

### Q5: Dove posso chiedere aiuto o entrare in contatto con la community di Aspose.Page?
A: Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per porre domande, condividere snippet e apprendere da altri sviluppatori.

### Q6: Posso usare questo approccio per creare un effetto filigrana?
A: Sì. Abbassando l'opacità e scegliendo un'immagine semitrasparente, il pennello a tasselli funziona perfettamente come filigrana ripetuta.

## Conclusione

Ora sai **come usare Aspose** per aggiungere un'immagine a tasselli a un documento XPS, controllarne l'opacità e salvare il risultato per ulteriori utilizzi. Questa tecnica è ideale per motivi di sfondo, filigrane o qualsiasi situazione in cui una grafica ripetuta aggiunge interesse visivo senza gonfiare le dimensioni del file. Sentiti libero di sperimentare con forme, immagini e modalità di tassellatura diverse per adattarle alle esigenze del tuo progetto.

---

**Ultimo aggiornamento:** 2026-03-03  
**Testato con:** Aspose.Page for .NET (ultima release)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}