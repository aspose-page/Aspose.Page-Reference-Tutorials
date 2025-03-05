---
title: Applicare la licenza misurata con Aspose.Page per .NET
linktitle: Applicare la licenza a consumo
second_title: API Aspose.Page .NET
description: Esplora la perfetta integrazione di Aspose.Page per .NET con questa guida passo passo sull'applicazione di una licenza a consumo. Ottimizza l'elaborazione dei documenti senza sforzo.
type: docs
weight: 10
url: /it/net/getting-started/apply-metered-license/
---
## introduzione

Sblocca tutto il potenziale di Aspose.Page per .NET applicando una licenza a consumo. Questo tutorial ti guiderà attraverso il processo di configurazione e applicazione della licenza a consumo, garantendo un utilizzo fluido e ottimizzato di questa potente libreria .NET.

## Prerequisiti

Prima di approfondire i passaggi, assicurati di disporre dei seguenti prerequisiti:

-  Una licenza Aspose.Page per .NET valida: è possibile ottenerla da[buy.aspose.com](https://purchase.aspose.com/buy).
-  Libreria Aspose.Page installata: fare riferimento al[documentazione](https://reference.aspose.com/page/net/) per le istruzioni di installazione.
- Ambiente di sviluppo .NET: assicurati di avere un ambiente .NET funzionante configurato sul tuo computer.

## Importa spazi dei nomi

Nel tuo progetto .NET, importa gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Passaggio 1: impostare le chiavi pubbliche e private misurate

 Inizializza il`Aspose.Page.Metered` class e impostare le chiavi pubbliche e private misurate. Sostituire`<type public key here>` E`<type private key here>` con le tue vere chiavi.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Passaggio 2: carica il file EPS e crea il documento

 Specifica il percorso del tuo file EPS e crea uno stream per leggerne il contenuto. Quindi, crea un'istanza di`PsDocument` classe dallo stream.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Passaggio 3: Converti immagine EPS in PNG

 Creare un`ImageDevice` per convertire il file EPS in un'immagine PNG. Salva il file EPS come immagine utilizzando il file`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Passaggio 4: recupera i byte di immagine

Ottieni i byte dell'immagine, dove ogni array di byte rappresenta una pagina. In questo caso, abbiamo una pagina.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Passaggio 5: salva i byte di immagine nel file

Salva i byte dell'immagine in un file, garantendo la corretta conversione da EPS a PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Passaggio 6: verificare la licenza a consumo

Controllare visivamente se la licenza a consumo è stata applicata correttamente. Se l'immagine risultante non contiene il messaggio di valutazione rosso, indica che la licenza a consumo viene applicata senza problemi.

Ora sei pronto per sfruttare tutte le funzionalità di Aspose.Page per .NET con una licenza a consumo!

## Conclusione

Questa guida passo passo ti ha fornito le conoscenze per applicare senza problemi una licenza a consumo utilizzando Aspose.Page per .NET. Migliora le tue capacità di elaborazione dei documenti ed esplora le vaste funzionalità offerte da questa potente libreria.

## Domande frequenti

### Q1: Come posso ottenere una licenza a consumo per Aspose.Page per .NET?

 A1: Visita[buy.aspose.com](https://purchase.aspose.com/buy) per acquisire una licenza valida.

### Q2: Dove posso trovare la documentazione per Aspose.Page per .NET?

 A2: Fare riferimento a[Aspose.Page .NET](https://reference.aspose.com/page/net/) per una documentazione completa.

### Q3: esiste un forum per le discussioni e il supporto di Aspose.Page?

 A3: Sì, visita[Forum](https://forum.aspose.com/c/page/39) impegnarsi con la comunità e cercare assistenza.

### Q4: Posso provare Aspose.Page per .NET prima dell'acquisto?

 A4: Assolutamente! Accedi alla prova gratuita su[Qui](https://releases.aspose.com/).

### Q5: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

 A5: Visita[licenza temporanea/](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea.