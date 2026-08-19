---
date: 2026-02-25
description: Scopri come utilizzare un pennello a gradiente lineare in C# per aggiungere
  un gradiente ai file PS e riempire un rettangolo con gradiente usando Aspose.Page
  per .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Pennello a gradiente lineare – Aggiungi gradiente verticale a PostScript
  (PS) con Aspose.Page
url: /it/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Aggiungi un gradiente verticale a PostScript (PS) con Aspose.Page

## Introduzione

Nel campo della manipolazione e creazione di documenti, **Aspose.Page for .NET** si distingue come uno strumento potente per gli sviluppatori. In questa guida scoprirai come **aggiungere un gradiente a file PS** utilizzando un **pennello a gradiente lineare C#** per **riempire un rettangolo con gradiente**. Alla fine di questo tutorial avrai una chiara comprensione passo‑passo del codice necessario e del motivo per cui questa tecnica produce un gradiente verticale uniforme nel tuo output PostScript.

## Risposte Rapide
- **Cosa fa un pennello a gradiente lineare C#?** Crea una transizione fluida tra più colori su una forma.
- **Posso usarlo con qualsiasi versione di .NET?** Sì, Aspose.Page supporta .NET Framework 4.5+ e .NET Core/5+.
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale per build non‑di valutazione.
- **Il gradiente è davvero verticale?** Il pennello è ruotato di 90°, garantendo un flusso verticale.
- **Dove viene salvato l'output?** Nel percorso specificato in `dataDir` (ad es., `VerticalGradient_outPS.ps`).

## Cos'è un Pennello a Gradiente Lineare C#?
Un **pennello a gradiente lineare C#** è un oggetto GDI+ (`LinearGradientBrush`) che dipinge una transizione di colore lineare tra punti definiti. Quando combinato con l'API di disegno di Aspose.Page, consente di renderizzare gradienti sofisticati direttamente in un documento PostScript (PS).

## Perché Usare un Pennello a Gradiente Lineare per PostScript?
- **Output di alta qualità:** I gradienti sono renderizzati a livello di stampante, preservando la fedeltà.
- **Controllo totale:** È possibile impostare stop di colore personalizzati, rotazione e scala.
- **Codice riutilizzabile:** La stessa logica del pennello funziona per PDF, SVG e altri formati supportati da Aspose.Page.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere quanto segue:

- Aspose.Page for .NET: Verifica di avere la libreria Aspose.Page installata. Puoi trovare le risorse necessarie e la documentazione [qui](https://reference.aspose.com/page/net/).
- Ambiente di sviluppo: Configura un ambiente di sviluppo adeguato, includendo un Integrated Development Environment (IDE) per lo sviluppo .NET.
- Conoscenze di base: Familiarizzati con le basi dello sviluppo .NET, inclusa la gestione di stream, percorsi grafici e manipolazione dei colori.

## Importa Namespace

Nel tuo progetto C#, includi i namespace richiesti all'inizio del file di codice:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Passo 1: Configura la Directory del Documento

Inizia specificando il percorso della tua directory dei documenti. Questo è il luogo in cui verrà salvato il documento PS.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Crea Stream di Output per il Documento PostScript

Genera uno stream di output per il documento PostScript utilizzando la classe `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Passo 3: Crea Opzioni di Salvataggio e Documento PS

Crea le opzioni di salvataggio con dimensione A4 e inizializza un nuovo documento PS a 1 pagina.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 4: Definisci le Dimensioni del Rettangolo

Specifica le dimensioni e la posizione del rettangolo dove verrà applicato il gradiente verticale.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Passo 5: Crea il Percorso Grafico

Costruisci un percorso grafico dal rettangolo definito.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Passo 6: Definisci i Colori di Interpolazione

Stabilisci un array di colori di interpolazione e le relative posizioni per il gradiente.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Passo 7: Crea il Pennello a Gradiente Lineare

Crea un pennello a gradiente lineare con il rettangolo come confine, colore iniziale e finale.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Passo 8: Imposta la Trasformazione del Pennello

Stabilisci una trasformazione per il pennello, assicurandoti che le componenti di scala X e Y corrispondano alla larghezza e all'altezza del rettangolo.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Passo 9: Imposta il Paint e Riempi il Rettangolo

Imposta il paint per il documento e **riempi il rettangolo con gradiente** usando il percorso precedentemente definito.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Passo 10: Chiudi la Pagina Corrente e Salva il Documento

Chiudi la pagina corrente e salva il documento PostScript.

```csharp
document.ClosePage();
document.Save();
```

Congratulazioni! Hai aggiunto con successo **un gradiente verticale a un documento PostScript** utilizzando un **pennello a gradiente lineare C#** con Aspose.Page for .NET. Sperimenta con parametri e colori diversi per ottenere vari effetti visivi nei tuoi documenti.

## Problemi Comuni e Soluzioni

| Problema | Perché accade | Come risolverlo |
|----------|---------------|-----------------|
| Il gradiente appare orizzontale | Rotazione del pennello non applicata | Assicurati che `brushTransform.Rotate(90);` sia chiamato prima di assegnare a `brush.Transform`. |
| I colori sembrano sbiaditi | Stream di output a bassa risoluzione | Usa un `PsSaveOptions` a risoluzione più alta o aumenta le dimensioni del documento. |
| Il file di output è vuoto | Stream non svuotato | Verifica che `document.Save();` sia chiamato al di fuori del blocco `using`. |

## Domande Frequenti

**D1: Posso applicare più gradienti a regioni diverse dello stesso documento?**  
R: Sì, puoi. Ripeti semplicemente i passaggi per ogni regione con le sue dimensioni e schema di colore specifici.

**D2: Come posso integrare questo codice nel mio progetto .NET esistente?**  
R: Copia e incolla il codice nel file del tuo progetto e assicurati di avere il riferimento alla libreria Aspose.Page.

**D3: Esistono altri tipi di gradiente disponibili in Aspose.Page per .NET?**  
R: Aspose.Page supporta vari tipi di gradiente, inclusi gradienti radiali e di percorso. Consulta la documentazione per maggiori dettagli.

**D4: Posso usare Aspose.Page per progetti commerciali?**  
R: Sì. Visita [qui](https://purchase.aspose.com/buy) per esplorare le opzioni di licenza.

**D5: Esiste un forum della community per Aspose.Page dove posso chiedere aiuto?**  
R: Certamente! Vai al [forum Aspose.Page](https://forum.aspose.com/c/page/39) per connetterti con altri sviluppatori e ricevere assistenza.

---

**Ultimo aggiornamento:** 2026-02-25  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}