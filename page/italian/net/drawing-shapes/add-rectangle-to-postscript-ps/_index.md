---
title: Aggiungi rettangolo a PostScript (PS) con Aspose.Page per .NET
linktitle: Aggiungi rettangolo a PostScript (PS)
second_title: API Aspose.Page .NET
description: Migliora la creazione di documenti in .NET con Aspose.Page. Impara passo dopo passo come aggiungere rettangoli ai file PostScript (PS).
weight: 12
url: /it/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi rettangolo a PostScript (PS) con Aspose.Page per .NET

## introduzione

Se stai cercando di migliorare le tue capacità di creazione di documenti in .NET, Aspose.Page fornisce una potente soluzione per la gestione dei documenti PostScript. In questo tutorial, ti guideremo attraverso il processo di aggiunta di rettangoli a un documento PostScript utilizzando Aspose.Page per .NET.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:

-  Aspose.Page per .NET Library: scarica e installa la libreria Aspose.Page per .NET da[Qui](https://releases.aspose.com/page/net/).

- Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo .NET configurato sul tuo computer.

## Importa spazi dei nomi

Prima di iniziare a scrivere codice, assicurati di importare gli spazi dei nomi necessari per accedere alle classi e ai metodi richiesti:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ora suddividiamo l'esempio in più passaggi:

## Passaggio 1: configura la directory dei documenti

```csharp
// Inizio ex:1
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
```

In questo passaggio, sostituisci "La tua directory dei documenti" con il percorso in cui desideri salvare il tuo documento PostScript.

## Passaggio 2: crea il flusso di output per il documento PostScript

```csharp
//Crea flusso di output per il documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Qui creiamo un flusso di output per il documento PostScript e specifichiamo il nome del file ("AddRectangle_outPS.ps"). Modifica il nome e la posizione del file in base alle tue preferenze.

## Passaggio 3: imposta le opzioni di salvataggio e crea il documento PS

```csharp
//Crea opzioni di salvataggio con il formato A4
PsSaveOptions options = new PsSaveOptions();

// Crea un nuovo documento PS di 1 pagina
PsDocument document = new PsDocument(outPsStream, options, false);
```

Imposta le opzioni di salvataggio, specificando la dimensione della pagina desiderata (A4 in questo caso). Quindi, crea un nuovo documento PostScript a pagina singola.

## Passaggio 4: aggiungi rettangolo e riempimento

```csharp
//Crea il percorso grafico dal primo rettangolo
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Imposta la vernice
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Riempi il rettangolo
document.Fill(path);
```

Qui creiamo un percorso grafico che rappresenta il primo rettangolo, impostiamo il colore della vernice (in questo caso arancione) e riempiamo il rettangolo.

## Passaggio 5: aggiungi un altro rettangolo e un tratto

```csharp
//Crea il percorso grafico dal secondo rettangolo
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Imposta la corsa
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Traccia (contorna) il rettangolo
document.Draw(path);
```

Analogamente al passaggio precedente, creiamo un percorso grafico per il secondo rettangolo, impostiamo il colore del tratto (rosso con spessore 3) e contorniamo il rettangolo.

## Passaggio 6: chiudi la pagina e salva il documento

```csharp
//Chiudi la pagina corrente
document.ClosePage();

//Salva il documento
document.Save();
```

Infine, chiudi la pagina corrente e salva l'intero documento.

## Conclusione

Congratulazioni! Hai aggiunto con successo rettangoli a un documento PostScript utilizzando Aspose.Page per .NET. Questo tutorial ha coperto i passaggi essenziali, dalla configurazione dell'ambiente di sviluppo al salvataggio del documento finale.

## Domande frequenti

### Q1: posso personalizzare i colori dei rettangoli?

R1: Sì, puoi personalizzare i colori regolando i parametri in`SolidBrush` E`Pen` classi.

### Q2: Aspose.Page è compatibile con altri formati di documenti?

A2: Sì, Aspose.Page supporta vari formati di documenti, inclusi XPS e PostScript.

### Q3: Come posso aggiungere testo al documento?

 A3: Puoi usare il file`TextFragment` classe in Aspose.Page per aggiungere testo al tuo documento.

### Q4: Dove posso trovare ulteriori esempi e documentazione?

 A4: Esplora la documentazione[Qui](https://reference.aspose.com/page/net/) e visitare il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il sostegno della comunità.

### Q5: Posso provare Aspose.Page prima dell'acquisto?

 R5: Sì, puoi ottenere una versione di prova gratuita[Qui](https://releases.aspose.com/) , e per un uso prolungato, considerare a[licenza temporanea](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
