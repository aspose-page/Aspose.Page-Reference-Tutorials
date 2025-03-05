---
title: Alterar valor nomeado com Aspose.Page para .NET
linktitle: Alterar valor nomeado
second_title: API Aspose.Page .NET
description: Aprenda como alterar valores nomeados em arquivos EPS usando Aspose.Page for .NET. Personalize metadados XMP sem esforço para processamento personalizado de documentos.
type: docs
weight: 16
url: /pt/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## Introdução

No mundo do processamento de documentos, Aspose.Page for .NET se destaca como uma ferramenta poderosa para manipulação de arquivos EPS. Uma das principais funcionalidades que oferece é a capacidade de alterar valores nomeados nos metadados XMP. Este tutorial irá guiá-lo através do processo de alteração de um valor nomeado usando Aspose.Page for .NET, permitindo que você personalize seus arquivos EPS de acordo com suas necessidades específicas.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Aspose.Page for .NET: Certifique-se de ter a biblioteca Aspose.Page for .NET instalada. Se não, você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).

- Diretório de documentos: tenha um diretório designado para seus arquivos EPS onde você pode realizar as alterações de valores nomeados.

## Importar namespaces

No seu projeto .NET, você precisa importar os namespaces necessários para acessar a funcionalidade fornecida pelo Aspose.Page. Adicione os seguintes namespaces ao seu código:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Agora, vamos dividir o código em várias etapas para uma compreensão abrangente:

## Etapa 1: inicializar o fluxo de entrada do arquivo EPS

```csharp
// ExInício:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// Fim:1
```

Nesta etapa, configuramos o fluxo de entrada para o arquivo EPS que você deseja modificar. Certifique-se de substituir "Seu diretório de documentos" pelo caminho real para o diretório de documentos.

## Etapa 2: Obtenha metadados XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Recupere os metadados XMP existentes do arquivo EPS. Se o arquivo EPS não contiver metadados XMP, um novo será gerado com valores dos comentários dos metadados PS.

## Etapa 3: alterar os valores de metadados XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Aqui, demonstramos a alteração de dois valores nomeados na estrutura "xmpTPg:MaxPageSize". Você pode personalizar isso de acordo com seus requisitos específicos.

## Etapa 4: Salvar arquivo EPS com metadados XMP alterados

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Salve o arquivo EPS modificado no fluxo de saída. O arquivo agora refletirá as alterações feitas nos metadados XMP.

## Conclusão

Com este tutorial, você aprendeu como aproveitar o Aspose.Page for .NET para alterar valores nomeados nos metadados XMP em arquivos EPS. Esta funcionalidade abre um mundo de possibilidades para personalizar e adaptar os seus documentos para atender a requisitos específicos.

## Perguntas frequentes

### Q1: Posso usar Aspose.Page for .NET com outros formatos de documento?

A1: Sim, Aspose.Page oferece suporte a vários formatos de documento, incluindo EPS, XPS e PDF.

### Q2: Existe uma versão de teste disponível para Aspose.Page for .NET?

 A2: Sim, você pode acessar uma avaliação gratuita[aqui](https://releases.aspose.com/).

### Q3: Onde posso encontrar mais documentação sobre Aspose.Page for .NET?

 A3: Consulte a documentação[aqui](https://reference.aspose.com/page/net/).

### Q4: Como posso obter uma licença temporária para Aspose.Page for .NET?

 A4: Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Quais opções de suporte estão disponíveis para usuários do Aspose.Page para .NET?

 A5: Visite o fórum da comunidade[aqui](https://forum.aspose.com/c/page/39) para apoio e discussões.