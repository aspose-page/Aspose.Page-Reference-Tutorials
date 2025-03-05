---
title: Aggiungi Circle Ellipse a PostScript (PS) con Aspose.Page
linktitle: Aggiungi ellisse circolare a PostScript (PS)
second_title: API Aspose.Page .NET
description: Scopri come aggiungere facilmente ellissi circolari ai documenti PostScript (PS) utilizzando Aspose.Page per .NET. Segui la nostra guida passo passo per un'integrazione perfetta.
type: docs
weight: 10
url: /it/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## introduzione

Benvenuti in questo tutorial completo sull'aggiunta di ellissi circolari ai documenti PostScript (PS) utilizzando Aspose.Page per .NET. Aspose.Page è una potente libreria che consente agli sviluppatori di lavorare senza problemi con PostScript e altri formati di documenti. In questa guida ti guideremo attraverso il processo per incorporare facilmente le ellissi circolari nei tuoi documenti PS.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:

1.  Aspose.Page per .NET Library: scarica e installa la libreria Aspose.Page per .NET da[Qui](https://releases.aspose.com/page/net/).

2. Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo .NET funzionante configurato sul tuo computer.

Ora iniziamo con la guida passo passo.

## Importa spazi dei nomi

Nel primo passaggio, è necessario importare gli spazi dei nomi necessari per rendere disponibile la funzionalità Aspose.Page nel codice.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ora suddividiamo l'esempio fornito in più passaggi per guidarti attraverso il processo di aggiunta di ellissi circolari a un documento PostScript.

## Passaggio 1: impostare la directory dei documenti

```csharp
// Inizio ex:1
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
```

Assicurati di sostituire "La tua directory dei documenti" con il percorso effettivo della directory dei tuoi documenti.

## Passaggio 2: crea il flusso di output per il documento PostScript

```csharp
//Crea flusso di output per il documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Qui viene creato un FileStream per scrivere il documento PostScript e la modalità file è impostata per creare un nuovo file.

## Passaggio 3: crea opzioni di salvataggio e documento PS

```csharp
//Crea opzioni di salvataggio con il formato A4
PsSaveOptions options = new PsSaveOptions();

// Crea un nuovo documento PS di 1 pagina
PsDocument document = new PsDocument(outPsStream, options, false);
```

Questo passaggio prevede la creazione di opzioni di salvataggio con formato A4 e l'inizializzazione di un nuovo documento PS di 1 pagina.

## Passaggio 4: crea il percorso grafico per la prima ellisse

```csharp
//Crea il percorso grafico dalla prima ellisse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Viene creato un percorso grafico per la prima ellisse, specificandone la posizione e le dimensioni.

## Passaggio 5: imposta Paint e riempi l'ellisse

```csharp
//Imposta la vernice
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Riempi l'ellisse
document.Fill(path);
```

Qui viene impostata la vernice e la prima ellisse viene riempita con il colore specificato.

## Passaggio 6: crea il percorso grafico per la seconda ellisse

```csharp
//Crea il percorso grafico dalla seconda ellisse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Allo stesso modo viene creato un percorso grafico per la seconda ellisse, definendone la posizione e le dimensioni.

## Passaggio 7: imposta il tratto e disegna l'ellisse

```csharp
//Imposta la corsa
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Traccia (delinea) l'ellisse
document.Draw(path);
```

In questo passaggio, il tratto viene impostato e la seconda ellisse viene delineata con il colore e lo spessore della linea specificati.

## Passaggio 8: chiudi la pagina corrente e salva il documento

```csharp
//Chiudi la pagina corrente
document.ClosePage();

//Salva il documento
document.Save();
```

Infine, la pagina corrente viene chiusa e l'intero documento viene salvato, completando il processo.

## Conclusione

Congratulazioni! Hai imparato con successo come aggiungere ellissi circolari ai documenti PostScript utilizzando Aspose.Page per .NET. Questo tutorial fornisce una guida dettagliata passo dopo passo per aiutarti a integrare perfettamente questa funzionalità nei tuoi progetti.

## Domande frequenti

### Q1: posso utilizzare Aspose.Page per .NET con altri formati di documenti?

 A1: Aspose.Page si concentra principalmente su PostScript, ma Aspose fornisce altre librerie per vari formati di documenti. Controlla il[Richiedere documentazione](https://reference.aspose.com/page/net/) per ulteriori dettagli.

### Q2: Dove posso trovare ulteriore supporto e discussioni nella community?

 A2: Visita il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per discussioni e supporto della comunità.

### Q3: È disponibile una prova gratuita per Aspose.Page per .NET?

 A3: Sì, puoi accedere a[prova gratuita](https://releases.aspose.com/)per esplorare le funzionalità di Aspose.Page per .NET.

### Q4: Come posso ottenere una licenza temporanea per Aspose.Page?

 A4: Ottieni una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) a scopo di test e valutazione.

### Q5: Dove posso acquistare Aspose.Page per .NET?

 A5: Acquista Aspose.Page per .NET da[pagina acquista](https://purchase.aspose.com/buy).