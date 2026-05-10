---
date: 2026-02-23
description: Impara a creare documenti XPS con gradiente diagonale usando Aspose.Page
  per .NET e migliora le tue presentazioni visive senza sforzo.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Crea XPS a gradiente diagonale con Aspose.Page per .NET
url: /it/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

 extra spaces.

Let's construct final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea XPS con gradiente diagonale con Aspose.Page per .NET

## Introduzione

Se hai bisogno di **creare XPS con gradiente diagonale** che catturino l'attenzione, Aspose.Page per .NET lo rende semplice. In questo tutorial imparerai come aggiungere un gradiente diagonale a un documento XPS, passo dopo passo, usando l'API di Aspose.Page. Alla fine avrai un modello riutilizzabile che potrai adattare a qualsiasi forma o combinazione di colori.

## Risposte rapide
- **Cosa fa il metodo API?** Crea un pennello a gradiente lineare che si estende diagonalmente lungo un percorso.  
- **Quale classe rappresenta il documento XPS?** `XpsDocument`.  
- **È necessaria una licenza per eseguire il campione?** Una versione di prova gratuita funziona per lo sviluppo; è richiesta una licenza per la produzione.  
- **Posso modificare la direzione del gradiente?** Sì—regola i valori `PointF` di inizio e fine.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è **create diagonal gradient xps**?
Un gradiente diagonale è una transizione di colore fluida che va da un angolo di una forma all'angolo opposto. In XPS, questo effetto si ottiene applicando un `LinearGradientBrush` alla proprietà di riempimento di un percorso. La libreria Aspose.Page astrae il markup XPS a basso livello, permettendoti di concentrarti su colori e geometria.

## Perché usare Aspose.Page per i gradienti diagonali?
- **Rendering ad alta fedeltà** – l'output corrisponde esattamente alla specifica XPS.  
- **Integrazione completa con .NET** – funziona con C#, VB.NET e qualsiasi linguaggio .NET.  
- **Nessuna dipendenza esterna** – tutto è gestito in‑processo, senza COM o Office richiesti.  
- **Scalabile a documenti complessi** – puoi combinare più gradienti, immagini e testo nella stessa pagina.

## Prerequisiti

1. **Libreria Aspose.Page per .NET** – scaricala [qui](https://releases.aspose.com/page/net/).  
2. **Ambiente di sviluppo** – Visual Studio, Rider o qualsiasi editor che supporti progetti .NET.  

Ora, immergiamoci nel codice.

## Importare gli spazi dei nomi

Nel tuo progetto .NET, includi gli spazi dei nomi necessari dalla libreria Aspose.Page per accedere alle classi e ai metodi richiesti. Aggiungi i seguenti spazi dei nomi all'inizio del tuo codice:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Passo 1: Impostare la directory del documento

Inizia specificando il percorso della tua directory dei documenti. Qui verrà salvato il documento XPS risultante con il gradiente diagonale.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Passo 2: Creare un nuovo documento XPS

Inizializza un nuovo `XpsDocument` usando la libreria Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Passo 3: Definire i colori del gradiente

Crea un elenco di oggetti `XpsGradientStop`, ciascuno rappresentante un colore nel gradiente diagonale.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Passo 4: Aggiungere un gradiente diagonale a un percorso

Crea un nuovo percorso con una geometria definita e applica il gradiente diagonale. Regola la trasformazione di rendering e le proprietà di riempimento secondo necessità.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Passo 5: Salvare il documento XPS risultante

Infine, salva il documento XPS modificato nella directory specificata.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Hai ora creato con successo un file **XPS con gradiente diagonale**. Sentiti libero di sperimentare con diversi stop di colore, stringhe di geometria o matrici di trasformazione per ottenere una varietà di effetti visivi.

## Problemi comuni e soluzioni
- **Gradiente non visibile** – Verifica che la geometria del percorso sia chiusa e che i punti di inizio/fine del pennello siano all'interno dei limiti del percorso.  
- **Colori errati** – Assicurati di usare `CreateColor` con i valori ARGB corretti; il metodo si aspetta valori nell'intervallo 0‑255.  
- **File non salvato** – Controlla che `dataDir` punti a una cartella esistente e che l'applicazione abbia i permessi di scrittura.

## Domande frequenti

**D: Posso applicare più gradienti a diverse parti del documento?**  
R: Sì, puoi creare più percorsi e applicare gradienti distinti a ciascuno.

**D: Esistono stili di gradiente predefiniti disponibili?**  
R: Aspose.Page consente gradienti personalizzati, offrendoti il pieno controllo sulle transizioni di colore.

**D: Posso usare Aspose.Page per .NET con altri formati di documento?**  
R: Aspose.Page si concentra principalmente sulla manipolazione di documenti XPS.

**D: Come posso gestire gli errori relativi all'elaborazione del documento?**  
R: Consulta la [documentazione](https://reference.aspose.com/page/net/) per le migliori pratiche di gestione degli errori.

**D: È disponibile una versione di prova prima dell'acquisto?**  
R: Sì, puoi esplorare la [versione di prova gratuita](https://releases.aspose.com/) per provare Aspose.Page per .NET.

**D: Come posso cambiare la direzione del gradiente in verticale o orizzontale?**  
R: Modifica gli argomenti `PointF` in `CreateLinearGradientBrush` per impostare nuovi punti di inizio e fine.

**D: La libreria supporta la trasparenza nei gradienti?**  
R: Sì—include un valore alfa quando crei i colori con `CreateColor`.

## Conclusione

Aspose.Page per .NET semplifica il processo di arricchire i documenti XPS con gradienti diagonali. Questa guida ti ha accompagnato passo passo, dalla configurazione dei prerequisiti al salvataggio del file finale. Continua a sperimentare con forme e palette di colori diverse per far risaltare davvero i tuoi report, brochure o fatture XPS.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-02-23  
**Testato con:** Aspose.Page 24.11 for .NET  
**Autore:** Aspose