---
title: Alterar valores com Aspose.Page para .NET
linktitle: Mudar valores
second_title: API Aspose.Page .NET
description: Domine a manipulação de arquivos EPS com Aspose.Page para .NET. Altere os valores dos metadados XMP sem esforço.
weight: 17
url: /pt/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alterar valores com Aspose.Page para .NET

## Introdução

No mundo dinâmico do processamento de documentos, Aspose.Page for .NET se destaca como uma ferramenta poderosa, oferecendo aos desenvolvedores a capacidade de manipular arquivos EPS sem esforço. Neste tutorial, nos aprofundaremos no processo de alteração de valores em arquivos EPS usando Aspose.Page for .NET. Quer você seja um desenvolvedor experiente ou um iniciante curioso, este guia passo a passo irá equipá-lo com as habilidades necessárias para modificar com eficiência os metadados XMP em seus arquivos EPS.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

### 1. Biblioteca Aspose.Page para .NET

Certifique-se de ter a biblioteca Aspose.Page for .NET instalada em seu ambiente de desenvolvimento. Se não, você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).

### 2. Diretório de Documentos

Configure um diretório para seus documentos. Este será o local onde seus arquivos EPS serão armazenados.

Agora que classificamos nossos pré-requisitos, vamos passar para as próximas etapas cruciais.

## Importar namespaces

Em qualquer projeto .NET, é essencial importar os namespaces necessários para utilizar as funcionalidades do Aspose.Page. Veja como você pode fazer isso:

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

```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
// Inicializar fluxo de entrada de arquivo EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Etapa 2: criar uma instância PsDocument do stream

```csharp
//Crie uma instância PsDocument do stream
PsDocument document = new PsDocument(psStream);
```

Agora que preparamos o cenário, vamos prosseguir para o núcleo do nosso tutorial - alterar os valores dos metadados XMP no arquivo EPS.

## Etapa 3: obtenha metadados XMP

```csharp
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, obteremos um novo preenchido com valores de comentários de metadados PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Etapa 4: modificar os valores de metadados XMP

Agora, vamos alterar alguns valores-chave nos metadados XMP:

### Etapa 4.1: Alterar o valor ModifyDate

```csharp
// Alterar valor ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Etapa 4.2: Alterar o valor do Criador

```csharp
// Alterar valor do Criador
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Etapa 4.3: Alterar o valor do título

```csharp
// Alterar valor do título
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Feitas essas alterações, vamos para a etapa final - salvar o arquivo EPS modificado.

## Etapa 5: salve o arquivo EPS com metadados XMP alterados

### Etapa 5.1: Criar fluxo de saída

```csharp
// Criar fluxo de saída
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Etapa 5.2: Salvar arquivo EPS

```csharp
// Salvar arquivo EPS
document.Save(outPsStream);
```

Finalmente, feche o fluxo de entrada:

```csharp
finally
{
    psStream.Close();
}
```

Parabéns! Você modificou com êxito os valores de metadados XMP em um arquivo EPS usando Aspose.Page for .NET.

## Conclusão

Neste tutorial, exploramos o processo contínuo de alteração de valores em arquivos EPS usando Aspose.Page for .NET. Como desenvolvedor, você agora tem uma ferramenta poderosa à sua disposição para uma manipulação eficiente de documentos.

## Perguntas frequentes

### Q1: Posso usar Aspose.Page for .NET com outros formatos de arquivo?

A1: Aspose.Page concentra-se principalmente na manipulação de arquivos EPS. Para outros formatos, explore a diversificada gama de produtos da Aspose.

### Q2: Existe uma versão de teste disponível?

 A2: Sim, você pode experimentar o Aspose.Page for .NET com a avaliação gratuita disponível[aqui](https://releases.aspose.com/).

### P3: Onde posso encontrar documentação detalhada?

 A3: A documentação abrangente pode ser encontrada[aqui](https://reference.aspose.com/page/net/).

### P4: Como obtenho uma licença temporária?

 A4: Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Posso comprar Aspose.Page para .NET?

 A5: Com certeza! Visite a página de compra[aqui](https://purchase.aspose.com/buy) para opções de licenciamento.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
