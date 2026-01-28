---
date: 2026-01-28
description: Scopri come convertire EPS in PNG usando Aspose.Page per .NET e applicare
  una licenza a consumo per una gestione fluida dei documenti.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Converti EPS in PNG e applica licenza a consumo con Aspose.Page per .NET
url: /it/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti EPS in PNG e Applica Licenza a Consumo con Aspose.Page per .NET

## Introduzione

Sblocca tutto il potenziale di Aspose.Page per .NET **convertendo EPS in PNG** e applicando una licenza a consumo. Questo tutorial ti guida attraverso ogni passaggio—dal caricamento di un file EPS al salvataggio come immagine PNG—per consentirti di elaborare documenti in modo efficiente e senza filigrane di valutazione.

## Risposte Rapide
- **Di cosa tratta questo tutorial?** Conversione di file EPS in immagini PNG e applicazione di una licenza a consumo con Aspose.Page per .NET.  
- **È necessaria una licenza?** Sì, è richiesta una licenza a consumo per l'uso in produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo richiede l'implementazione?** Circa 10–15 minuti per una conversione di base.  
- **Posso eseguirlo su Linux/macOS?** Assolutamente—Aspose.Page è multipiattaforma.

## Cos'è “convertire EPS in PNG”?

Convertire EPS in PNG significa rasterizzare un file Encapsulated PostScript (EPS) basato su vettori in un'immagine bitmap PNG. Questo è utile quando è necessario visualizzare o incorporare grafiche in pagine web, report o componenti UI che non supportano EPS.

## Perché utilizzare una licenza a consumo per la conversione di EPS in immagine?

Una licenza a consumo ti consente di pagare solo per le pagine che elabori, ideale per carichi di lavoro con volume variabile. Inoltre rimuove il banner rosso di valutazione che appare quando si utilizza la versione di prova gratuita, garantendo un output pulito per gli utenti finali.

## Prerequisiti

Prima di immergerti nei passaggi, assicurati di avere i seguenti prerequisiti:

- Una licenza valida di Aspose.Page per .NET: puoi ottenerla da [purchase.aspose.com](https://purchase.aspose.com/buy).
- Libreria Aspose.Page installata: consulta la [documentazione](https://reference.aspose.com/page/net/) per le istruzioni di installazione.
- Ambiente di sviluppo .NET: assicurati di avere un ambiente .NET funzionante configurato sulla tua macchina.

## Importa Namespace

Nel tuo progetto .NET, importa i namespace necessari per accedere alle funzionalità di Aspose.Page:

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

## Come convertire EPS in PNG con una licenza a consumo?

Di seguito trovi una guida passo‑passo che copre tutto ciò che devi sapere.

### Passo 1: Imposta le Chiavi Pubbliche e Private a Consumo

Inizializza la classe `Aspose.Page.Metered` e imposta le chiavi pubbliche e private a consumo. Sostituisci `<type public key here>` e `<type private key here>` con le tue chiavi effettive.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Passo 2: Carica il File EPS e Crea il Documento

Specifica il percorso del tuo file EPS e crea uno stream per leggere il suo contenuto. Quindi, crea un'istanza della classe `PsDocument` dallo stream.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Passo 3: Converti EPS in Immagine PNG

Crea un `ImageDevice` per convertire il file EPS in un'immagine PNG. Salva il file EPS come immagine usando `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Passo 4: Recupera i Byte dell'Immagine

Ottieni i byte dell'immagine, dove ogni array di byte rappresenta una pagina. In questo caso, abbiamo una pagina.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Passo 5: Salva i Byte dell'Immagine su File

Salva i byte dell'immagine su un file, garantendo una conversione riuscita da EPS a PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Passo 6: Verifica la Licenza a Consumo

Verifica visivamente se la licenza a consumo è stata applicata correttamente. Se l'immagine risultante non contiene il messaggio rosso di valutazione, indica che la licenza a consumo è stata applicata senza problemi.

Ora sei pronto a sfruttare tutte le capacità di Aspose.Page per .NET con una licenza a consumo!

## Problemi Comuni e Soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Il banner rosso di valutazione appare ancora | Licenza non impostata o chiavi errate | Verifica nuovamente le chiavi pubbliche/private e assicurati che `SetMeteredKey` sia chiamato prima di qualsiasi elaborazione del documento |
| Nessun file di output creato | Percorso `dataDir` errato o permessi del file | Verifica che la directory esista e che l'applicazione abbia i permessi di scrittura |
| Pagine multiple non salvate | Solo la prima pagina è stata scritta | Itera su `imagesBytes` e scrivi ogni array in un file PNG separato |

## Domande Frequenti

**Q: Posso usare la licenza a consumo in una pipeline CI/CD?**  
A: Sì, puoi memorizzare le chiavi in modo sicuro (ad esempio, in variabili d'ambiente) e chiamare `SetMeteredKey` durante il processo di build.

**Q: Aspose.Page supporta la conservazione del profilo colore quando si converte in PNG?**  
A: L'output PNG mantiene le informazioni di colore originali, ma è possibile personalizzarle ulteriormente tramite `ImageSaveOptions`.

**Q: È possibile convertire EPS in altri formati raster (JPEG, BMP)?**  
A: Assolutamente—basta cambiare `ImageSaveOptions` nel formato desiderato.

**Q: Qual è la dimensione massima del file EPS supportata?**  
A: Aspose.Page gestisce file di grandi dimensioni, ma il consumo di memoria aumenta con la risoluzione dell'immagine. Considera di elaborare le pagine singolarmente per documenti molto grandi.

**Q: Come posso recuperare programmaticamente il numero di pagine nel file EPS?**  
A: Usa `document.PagesCount` dopo aver caricato il `PsDocument`.

## FAQ

### Q1: Come posso ottenere una licenza a consumo per Aspose.Page per .NET?

A1: Visita [purchase.aspose.com](https://purchase.aspose.com/buy) per acquisire una licenza valida.

### Q2: Dove posso trovare la documentazione per Aspose.Page per .NET?

A2: Consulta [Aspose.Page .NET](https://reference.aspose.com/page/net/) per una documentazione completa.

### Q3: Esiste un forum per discussioni e supporto su Aspose.Page?

A3: Sì, visita il [forum](https://forum.aspose.com/c/page/39) per interagire con la community e chiedere assistenza.

### Q4: Posso provare Aspose.Page per .NET prima di acquistarlo?

A4: Assolutamente! Accedi alla prova gratuita [qui](https://releases.aspose.com/).

### Q5: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

A5: Visita [temporary license/](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

**Ultimo aggiornamento:** 2026-01-28  
**Testato con:** Aspose.Page 24.12 for .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}