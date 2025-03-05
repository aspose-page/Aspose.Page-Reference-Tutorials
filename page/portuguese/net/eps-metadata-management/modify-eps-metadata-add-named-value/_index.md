---
title: Adicionar valor nomeado com Aspose.Page
linktitle: Adicionar valor nomeado
second_title: API Aspose.Page .NET
description: Aprenda como adicionar valores nomeados a arquivos EPS em .NET usando Aspose.Page. Este tutorial abrangente orienta você pelo processo passo a passo.
type: docs
weight: 12
url: /pt/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## Introdução

No domínio do processamento de documentos com .NET, Aspose.Page se destaca como uma ferramenta poderosa para lidar com arquivos EPS. Aspose.Page permite que os desenvolvedores manipulem metadados XMP, facilitando tarefas como adicionar valores nomeados. Este tutorial irá guiá-lo passo a passo pelo processo de adição de valores nomeados a um arquivo EPS usando Aspose.Page.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Conhecimento básico da linguagem de programação C#.
- Um ambiente de desenvolvimento integrado (IDE), como o Visual Studio instalado.
-  Biblioteca Aspose.Page para .NET. Se não estiver instalado, você pode baixá-lo em[aqui](https://releases.aspose.com/page/net/).

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários para o seu código C#. Esses namespaces são vitais para acessar as funcionalidades fornecidas pelo Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Etapa 1: inicializar o fluxo de entrada do arquivo EPS

 A etapa inicial envolve a inicialização do fluxo de entrada do arquivo EPS. Substituir`"Your Document Directory"` com o caminho para o diretório do seu documento:

```csharp
// ExInício:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Etapa 2: Obtenha metadados XMP

Recuperar metadados XMP do arquivo EPS. Se o arquivo EPS não tiver metadados XMP, um novo será criado, preenchido com valores dos comentários dos metadados PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Etapa 3: alterar os valores de metadados XMP

Agora, vamos fazer alterações nos metadados XMP. Neste exemplo, adicionaremos um valor nomeado à estrutura "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Etapa 4: Salvar arquivo EPS com metadados XMP alterados

Salve o arquivo EPS com os metadados XMP atualizados. Crie um fluxo de saída e salve o arquivo EPS modificado:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Conclusão

Parabéns! Você adicionou com êxito um valor nomeado a um arquivo EPS usando Aspose.Page no .NET. Este tutorial orientou você pelas etapas essenciais, mostrando a simplicidade e eficácia do Aspose.Page na manipulação de documentos.

## Perguntas frequentes

### Q1: O Aspose.Page é compatível com diferentes versões de arquivos EPS?

A1: Aspose.Page suporta várias versões de arquivos EPS, garantindo compatibilidade com uma ampla variedade de documentos.

### Q2: Posso usar Aspose.Page para projetos comerciais?

 A2: Sim, Aspose.Page vem com uma licença comercial e você pode comprá-la[aqui](https://purchase.aspose.com/buy).

### Q3: Existe uma avaliação gratuita disponível para Aspose.Page?

 A3: Sim, você pode explorar Aspose.Page com uma avaliação gratuita disponível[aqui](https://releases.aspose.com/).

### P4: Como posso obter suporte ou me conectar com a comunidade Aspose?

 A4: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para obter suporte e se conectar com a comunidade.

### P5: O que é uma licença temporária e como posso obtê-la?

 R5: Se precisar de uma licença temporária para fins de teste ou avaliação, você pode adquirir uma[aqui](https://purchase.aspose.com/temporary-license/).