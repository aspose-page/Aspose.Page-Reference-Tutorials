---
date: 2026-02-25
description: Scopri come creare un documento XPS e applicare un gradiente lineare
  con Aspose.Page per .NET. Segui la nostra guida passo‑passo per salvare il file
  XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Crea documento XPS con gradiente verticale usando Aspose.Page
url: /it/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 container.

Make sure to keep all shortcodes exactly as they appear.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi Gradiente Verticale a XPS con Aspose.Page per .NET

## Introduzione

In questo tutorial **creerai un documento XPS** con un gradiente verticale uniforme. Aggiungere gradienti è un modo comune per rendere i file XPS più professionali—perfetto per report, brochure o qualsiasi grafica stampabile. Ti guideremo passo passo, dalla configurazione del progetto al salvataggio del file XPS finale, così potrai applicare rapidamente un gradiente lineare a qualsiasi percorso.

## Risposte Rapide
- **Di cosa tratta questo tutorial?** Aggiungere un gradiente lineare verticale a un percorso in un documento XPS.  
- **Quale libreria è necessaria?** Aspose.Page per .NET.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio base.  
- **Posso salvare il risultato come file XPS?** Sì, il metodo `Save` scrive il file su disco.

## Cos'è un gradiente verticale in XPS?

Un gradiente verticale è una transizione di colore che va dalla parte superiore di una forma fino alla parte inferiore. In XPS, ciò si ottiene con un **linear gradient brush** che definisce i punti di inizio e fine, più una raccolta di gradient stop che controllano il colore in posizioni specifiche.

## Perché usare Aspose.Page per creare documenti XPS con gradienti?

- **Integrazione completa con .NET** – funziona con .NET Framework, .NET Core e .NET 5/6+.  
- **Nessuna dipendenza esterna** – tutto il rendering è gestito dalla libreria.  
- **Alta fedeltà** – i gradienti vengono renderizzati esattamente come definiti, rispettando la specifica XPS.  
- **Facile da mantenere** – modello di oggetti chiaro per percorsi, pennelli e colori.

## Prerequisiti

- Aspose.Page for .NET Library: Assicurati di avere la libreria Aspose.Page for .NET installata nel tuo ambiente di sviluppo. Puoi scaricarla [qui](https://releases.aspose.com/page/net/).
- Development Environment: Configura un ambiente di sviluppo .NET con l'IDE preferito, ad esempio Visual Studio.

Ora che abbiamo tutto pronto, immergiamoci nel codice.

## Importa gli Spazi dei Nomi

Nella tua applicazione .NET, includi gli spazi dei nomi necessari per accedere alle classi e ai metodi di Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Passo 1: Configura la Cartella del Documento

Definisci la cartella in cui verrà salvato il file XPS generato.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Passo 2: Crea un Nuovo Documento XPS

Istanzia un nuovo documento XPS che in seguito popoleremo con un percorso riempito con un gradiente.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Passo 3: Definisci i Gradient Stop

I gradient stop determinano i colori e le loro posizioni lungo la linea del gradiente. Qui creiamo cinque stop per produrre una transizione verticale fluida.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Passo 4: Crea un Percorso con Gradiente

Disegniamo un percorso a forma di rettangolo e applichiamo un **linear gradient brush** che si estende verticalmente dal punto (10, 110) al punto (10, 200). Il pennello riceve i gradient stop definiti in precedenza.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Passo 5: Salva il Documento XPS Resultante

Infine, scrivi il documento XPS su disco. Questo passaggio di **salvataggio del file XPS** produce `AddVerticalGradient_outXPS.xps` nella cartella specificata.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Consiglio:** Verifica l'output aprendo il file XPS in Windows XPS Viewer o in qualsiasi visualizzatore di terze parti per assicurarti che il gradiente appaia come previsto.

## Problemi Comuni & Risoluzione

| Sintomo | Probabile Causa | Soluzione |
|---------|----------------|-----------|
| Il gradiente appare come colore solido | Gradient stop non aggiunti al pennello | Assicurati che `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` venga eseguito. |
| File non trovato al salvataggio | `dataDir` punta a una cartella inesistente | Crea prima la directory o usa un percorso assoluto. |
| I colori appaiono diversi | I valori di colore usano l'ordine ARGB; verifica l'ordine dei canali | Usa `CreateColor(alpha, red, green, blue)` correttamente. |

## Domande Frequenti

**D: Aspose.Page è compatibile con Visual Studio 2019?**  
R: Sì, Aspose.Page è compatibile con Visual Studio 2019. Assicurati di avere installata la versione corretta della libreria.

**D: Posso usare Aspose.Page per progetti commerciali?**  
R: Sì, Aspose.Page può essere usato per progetti commerciali. Visita [qui](https://purchase.aspose.com/buy) per esplorare le opzioni di licenza.

**D: È disponibile una versione di prova gratuita?**  
R: Sì, puoi ottenere una versione di prova gratuita di Aspose.Page [qui](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione di Aspose.Page?**  
R: La documentazione è disponibile [qui](https://reference.aspose.com/page/net/).

**D: Come posso ottenere supporto o fare domande?**  
R: Visita il [forum di Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto della community.

## Conclusione

Ora sai come **creare un documento XPS**, **applicare un gradiente lineare** e **salvare un file XPS** usando Aspose.Page per .NET. Questo approccio ti offre il pieno controllo dello stile visivo negli output XPS, facendo risaltare i tuoi documenti stampabili.

---  

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}