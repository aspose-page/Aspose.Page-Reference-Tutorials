---
date: 2026-01-05
description: Scopri come ritagliare documenti XPS usando Aspose.Page per .NET. Questa
  guida passo‑passo ti mostra come creare, manipolare e salvare file XPS in modo efficiente.
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: Come ritagliare XPS con Aspose.Page per .NET
url: /it/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ritagliare XPS con Aspose.Page per .NET

## Introduzione

Benvenuti a questo tutorial completo su **come ritagliare XPS** usando Aspose.Page per .NET! In questa guida, vi accompagneremo attraverso il processo di creazione, manipolazione e salvataggio dei documenti XPS con la libreria. XPS, o XML Paper Specification, è un formato di documento standardizzato e aperto, e Aspose.Page per .NET fornisce potenti strumenti per lavorare con i documenti XPS nelle vostre applicazioni .NET.

## Risposte rapide
- **Che cos'è il clipping XPS?** Applicare una maschera geometrica (clip) per limitare l'area visibile degli elementi della tela XPS.  
- **Quale libreria è la migliore per questo?** Aspose.Page per .NET offre un'API completa per la creazione e il clipping di XPS.  
- **Prerequisiti?** Visual Studio, runtime .NET e la libreria Aspose.Page per .NET.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per uno scenario di clipping di base.  
- **Posso usarlo in produzione?** Sì, con una licenza valida di Aspose (disponibile versione di prova).

## Che cosa significa “come ritagliare XPS”?
Il clipping in XPS funziona definendo una **clip geometry** (ad esempio un cerchio o un rettangolo) e assegnandola a una canvas. Qualsiasi elemento disegnato al di fuori di quella geometria non viene renderizzato, consentendo di creare layout di pagina sofisticati come immagini mascherate, forme personalizzate o aree di contenuto focalizzate.

## Perché usare Aspose.Page per .NET per ritagliare XPS?
- **Controllo completo** su trasformazioni della canvas, geometrie di percorso e pennelli.  
- **Nessuna dipendenza esterna** – tutto funziona all'interno della tua applicazione .NET.  
- **Supporto cross‑platform** per .NET Framework, .NET Core e .NET 5/6+.  
- **Alte prestazioni** con un'API leggera che genera file XPS validi.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio installato sul tuo computer.  
- Libreria Aspose.Page per .NET aggiunta al tuo progetto. Puoi scaricarla [qui](https://releases.aspose.com/page/net/).  
- Conoscenza di base del linguaggio di programmazione C#.

## Importare gli spazi dei nomi

Per utilizzare le funzionalità di Aspose.Page per .NET, è necessario importare gli spazi dei nomi richiesti nel tuo progetto. Segui questi passaggi:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ora, suddividiamo il codice di esempio fornito in più passaggi.

## Passo 1: Impostare il percorso della directory del documento.

```csharp
string dataDir = "Your Document Directory";
```

Assicurati di sostituire "Your Document Directory" con il percorso effettivo della tua directory dei documenti.

## Passo 2: Creare un nuovo documento XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Questo crea un nuovo documento XPS con cui lavorerai.

## Passo 3: Creare la canvas principale.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Questo passo crea la canvas principale, comune a tutti gli elementi della pagina.

## Passo 4: Impostare gli offset sinistro e superiore nella canvas principale.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Regola gli offset sinistro e superiore secondo le tue esigenze.

## Passo 5: Creare una geometria di percorso rettangolare.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Questo crea una geometria di percorso per un rettangolo.

## Passo 6: Creare un riempimento per i rettangoli.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Definisci il colore di riempimento per i rettangoli.

## Passo 7: Aggiungere un'altra canvas con clip alla canvas principale.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Questo passo aggiunge un'altra canvas alla canvas principale.

## Passo 8: Creare una geometria circolare per il clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Questo crea una geometria di clip circolare e la applica alla seconda canvas.

## Passo 9: Creare un rettangolo nella seconda canvas e riempirlo.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Questo passo crea un rettangolo nella seconda canvas e lo riempie.

## Passo 10: Aggiungere la seconda canvas con un rettangolo contornato alla canvas principale.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Questo aggiunge un'altra canvas alla canvas principale.

## Passo 11: Creare un rettangolo nella terza canvas e tracciarlo.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Questo crea un rettangolo nella terza canvas e gli applica un contorno.

## Passo 12: Salvare il documento XPS risultante.

```csharp
doc.Save(dataDir + "output2.xps");
```

Questo salva il documento XPS nella directory specificata.

## Problemi comuni e soluzioni
- **Percorso non valido** – Assicurati che `dataDir` termini con una barra rovesciata (`\\`) o usa `Path.Combine`.  
- **Clip non applicato** – Verifica che la stringa della clip geometry sia ben formata; uno spazio mancante può far sì che il clip venga ignorato.  
- **Eccezione di licenza** – In una build non di valutazione, aggiungi una licenza Aspose valida prima di creare il documento per evitare eccezioni a runtime.

## Domande frequenti

### D1: Posso usare Aspose.Page per .NET con altri formati di documento?

R1: Aspose.Page per .NET si concentra principalmente sui documenti XPS, ma Aspose fornisce altre librerie per vari formati di documento.

### D2: Aspose.Page per .NET è adatto ai principianti?

R2: Sì, Aspose.Page per .NET è progettato per essere user‑friendly, e i principianti possono rapidamente comprendere le sue funzionalità con una documentazione adeguata.

### D3: Dove posso trovare più esempi e risorse?

R3: Visita la [documentazione](https://reference.aspose.com/page/net/) e il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per risorse ed esempi estesi.

### D4: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

R4: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### D5: È disponibile una versione di prova gratuita per Aspose.Page per .NET?

R5: Sì, puoi provare la versione gratuita [qui](https://releases.aspose.com/).

## Altre domande frequenti

**D: Posso combinare più geometrie di clip su una singola canvas?**  
R: Sì, puoi assegnare un `PathGeometry` complesso che contiene diversi sotto‑percorsi alla proprietà `Clip`, consentendo mascherature a strati.

**D: Il clipping influisce sulla conversione PDF?**  
R: Quando converti successivamente l'XPS in PDF usando Aspose.PDF, la geometria di clip viene preservata, quindi il risultato visivo rimane identico.

**D: È possibile animare il clipping in XPS?**  
R: XPS di per sé non supporta l'animazione; tuttavia, puoi generare una serie di pagine XPS con diverse forme di clip per simulare il movimento.

---

**Ultimo aggiornamento:** 2026-01-05  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}