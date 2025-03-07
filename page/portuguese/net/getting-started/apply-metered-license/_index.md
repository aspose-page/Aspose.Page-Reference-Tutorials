---
title: Aplicar licença medida com Aspose.Page para .NET
linktitle: Aplicar licença medida
second_title: API Aspose.Page .NET
description: Explore a integração perfeita do Aspose.Page for .NET com este guia passo a passo sobre como aplicar uma licença limitada. Otimize o processamento de documentos sem esforço.
weight: 10
url: /pt/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aplicar licença medida com Aspose.Page para .NET

## Introdução

Desbloqueie todo o potencial do Aspose.Page for .NET aplicando uma licença limitada. Este tutorial irá guiá-lo através do processo de configuração e aplicação da licença limitada, garantindo o uso tranquilo e otimizado desta poderosa biblioteca .NET.

## Pré-requisitos

Antes de mergulhar nas etapas, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Uma licença válida do Aspose.Page for .NET: você pode obtê-la em[comprar.aspose.com](https://purchase.aspose.com/buy).
-  Biblioteca Aspose.Page instalada: Consulte o[documentação](https://reference.aspose.com/page/net/) para obter instruções de instalação.
- Ambiente de desenvolvimento .NET: certifique-se de ter um ambiente .NET funcional configurado em sua máquina.

## Importar namespaces

Em seu projeto .NET, importe os namespaces necessários para acessar as funcionalidades do Aspose.Page:

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

## Etapa 1: definir chaves públicas e privadas medidas

 Inicialize o`Aspose.Page.Metered` class e definir as chaves públicas e privadas medidas. Substituir`<type public key here>` e`<type private key here>` com suas chaves reais.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Etapa 2: carregar o arquivo EPS e criar o documento

 Especifique o caminho para o seu arquivo EPS e crie um fluxo para ler seu conteúdo. Em seguida, crie uma instância do`PsDocument` classe do fluxo.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Etapa 3: converter EPS em imagem PNG

 Criar um`ImageDevice` para converter o arquivo EPS em uma imagem PNG. Salve o arquivo EPS como uma imagem usando o`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Etapa 4: recuperar bytes de imagem

Obtenha os bytes da imagem, onde cada matriz de bytes representa uma página. Neste caso, temos uma página.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Etapa 5: salvar bytes de imagem em arquivo

Salve os bytes da imagem em um arquivo, garantindo uma conversão bem-sucedida de EPS para PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Etapa 6: verificar a licença medida

Verifique visualmente se a licença medida foi aplicada com sucesso. Se a imagem resultante não contiver a mensagem de avaliação vermelha, isso indica que a licença medida foi aplicada sem problemas.

Agora você está pronto para aproveitar todos os recursos do Aspose.Page for .NET com uma licença limitada!

## Conclusão

Este guia passo a passo equipou você com o conhecimento para aplicar perfeitamente uma licença medida usando Aspose.Page for .NET. Aprimore seus recursos de processamento de documentos e explore os vastos recursos oferecidos por esta poderosa biblioteca.

## Perguntas frequentes

### Q1: Como obtenho uma licença limitada para Aspose.Page for .NET?

 A1: Visita[comprar.aspose.com](https://purchase.aspose.com/buy) para adquirir uma licença válida.

### Q2: Onde posso encontrar a documentação do Aspose.Page for .NET?

 A2: Consulte[Aspose.Page .NET](https://reference.aspose.com/page/net/) para documentação abrangente.

### Q3: Existe um fórum para discussões e suporte do Aspose.Page?

 A3: Sim, visite[fórum](https://forum.aspose.com/c/page/39) para se envolver com a comunidade e procurar assistência.

### Q4: Posso experimentar o Aspose.Page for .NET antes de comprar?

 A4: Com certeza! Acesse o teste gratuito em[aqui](https://releases.aspose.com/).

### Q5: Como posso obter uma licença temporária para Aspose.Page for .NET?

 A5: Visita[licença temporária/](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
