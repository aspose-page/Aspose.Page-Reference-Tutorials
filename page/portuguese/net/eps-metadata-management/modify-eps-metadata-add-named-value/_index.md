---
date: 2026-01-23
description: Aprenda a editar arquivos EPS adicionando valores nomeados usando o Aspose.Page
  para .NET. Este guia passo a passo ajuda os desenvolvedores a manipular os metadados
  EPS.
linktitle: Add Named Value
second_title: Aspose.Page .NET API
title: Como editar arquivos EPS – Adicionar valor nomeado com Aspose.Page
url: /pt/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Editar Arquivos EPS – Adicionar Valor Nomeado com Aspose.Page

## Introdução – Como Editar Arquivos EPS

Neste tutorial sobre **como editar EPS**, vamos guiá‑lo na adição de um valor nomeado a um documento EPS usando a biblioteca Aspose.Page para .NET. Seja construindo uma ferramenta de processamento em lote ou precisando enriquecer metadados EPS em tempo real, as etapas abaixo fornecem um guia claro e prático.

## Respostas Rápidas
- **O que o, modificar e gravar arquivos EPS, incluindo metadados XMP.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Preciso de uma licença?** Um teste gratuito está disponível, mas uma licença comercial é necessária para uso em produção.  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos para o cenário básico de valor nomeado.  
- **É seguro para arquivos EPS grandes?** Sim – o Aspose.Page transmite dados, mantendo o uso de memória baixo.

## Pré‑requisitos

Antes de mergulhar no tutorial, certifique‑se de que você possui os seguintes pré‑requisitos:

- Conhecimento básico da linguagem de programação C#.  
- Um ambiente de desenvolvimento integrado (IDE) como o Visual Studio instalado.  
- Biblioteca Aspose.Page para .NET. Se não estiver instalada, você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).

## Importar Namespaces

Primeiro, vamos importar os namespaces necessários para o seu código C#. Esses namespaces são essenciais para acessar as funcionalidades fornecidas pelo Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Etapa 1: Inicializar o Stream de Entrada do Arquivo EPS

A etapa inicial envolve inicializar o stream de entrada para o arquivo EPS. Substitua `"Your Document Directory"` pelo caminho do seu diretório de documentos:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Etapa 2: Obter Metadados XMP

Recupere os metadados XMP do arquivo EPS. Se o arquivo EPS não possuir metadados XMP, um novo será criado, preenchido com valores dos comentários de metadados PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Etapa 3: Alterar Valores dos Metadados XMP

Agora, vamos fazer alterações nos metadados XMP. Neste exemplo, adicionaremos um valor nomeado à estrutura `"xmpTPg:MaxPageSize"`:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Etapa 4: Salvar o Arquivo EPS com Metadados XMP Alterados

Salve o arquivo EPS com os metadados XMP atualizados. Crie um stream de saída e salve o arquivo EPS modificado:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Conclusão

Parabéns! Você adicionou com sucesso um valor nomeado a um arquivo EPS usando o Aspose.Page no .NET. Este tutorial demonstra como é simples **editar metadados EPS**, permitindo que você enriqueça documentos uma licença [aqui](https://purchase.aspose.com/buy).

### Q3: Existe um teste gratuito disponível para o Aspose.Page?

**R3:** Sim, você pode explorar o Aspose.Page com um teste gratuito disponível [aqui](https://releases.aspose.com/).

### Q4: Como posso obter suporte ou conectar‑me com a comunidade Aspose?

**R4:** Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para obter suporte e conectar‑se com a comunidade.

### Q5: O que é uma licença temporária e como posso obter uma?

**R5:** Se precisar de uma licença temporária para testes ou avaliação, você pode adquiri‑la [aqui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose