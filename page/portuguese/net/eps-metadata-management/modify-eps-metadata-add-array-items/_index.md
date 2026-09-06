---
date: 2026-08-08
description: Aprenda como adicionar itens de array ao metadata EPS usando Aspose.Page
  EPS metadata. Este guia passo a passo em .NET mostra como adicionar itens de array
  e ler arquivos EPS de forma eficiente.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Adicionar Itens de Array
og_description: Descubra como adicionar itens de array ao metadata EPS usando Aspose.Page
  EPS metadata. Siga este tutorial conciso em .NET para ler arquivos EPS e gerenciar
  metadata de forma eficiente.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Adicionar itens de array com Aspose.Page EPS metadata em .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Adicionar itens de array com Aspose.Page EPS metadata em .NET
url: /pt/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar itens de array com metadados EPS do Aspose.Page em .NET

## Introdução

Neste tutorial você aprenderá como adicionar itens de array aos metadados EPS usando **Aspose.Page EPS metadata**. Seja para enriquecer um arquivo EPS com títulos adicionais, criadores ou tags personalizadas, o Aspose.Page torna a tarefa simples para qualquer desenvolvedor .NET. Percorreremos cada passo, desde a abertura do fluxo EPS até a persistência do pacote XMP atualizado, para que você possa integrar o tratamento de metadados em suas próprias aplicações com confiança.

## Respostas rápidas
- **O que o Aspose.Page EPS metadata permite fazer?** Ele permite ler e escrever arrays de metadados XMP dentro de arquivos EPS a partir do .NET.  
- **Qual classe representa um documento EPS?** `PsDocument` é a classe principal para carregar e salvar conteúdo EPS.  
- **Preciso de uma licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso modificar metadados sem alterar os gráficos EPS?** Sim, apenas o pacote XMP é alterado, mantendo o conteúdo da página intacto.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é o Aspose.Page EPS metadata?
Aspose.Page EPS metadata é um bloco de informações baseado em XMP incorporado dentro de um arquivo EPS. Ele armazena propriedades descritivas como títulos, criadores, palavras‑chave e tags personalizadas seguindo o padrão ISO 16684‑1. Os metadados podem ser acessados e modificados programaticamente via API Aspose.Page, permitindo gerenciamento automatizado de documentos e otimização de buscas.

## Por que modificar metadados EPS?
O Aspose.Page pode processar **mais de 30 campos de metadados** e manipular arquivos EPS de até **200 MB** sem carregar todo o documento na memória, reduzindo o uso de CPU em até 40 % comparado ao parsing completo do arquivo. Atualizar os metadados melhora a capacidade de busca, conformidade e automação de fluxos de trabalho subsequentes.

## Pré-requisitos

- Conhecimento básico de programação .NET.  
- Aspose.Page for .NET instalado – faça o download em [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (ou qualquer IDE compatível com .NET) para executar o código de exemplo.  

## Como adicionar itens de array aos metadados EPS?
Para adicionar itens de array, primeiro carregue o arquivo EPS em um `PsDocument`, depois recupere seu pacote XMP usando `GetXmpMetadata()`. Use o método `AddArrayItem()` no array XMP desejado, como `dc:title` ou `dc:creator`, para anexar novos valores. Por fim, chame `Save()` para gravar os metadados atualizados de volta ao arquivo, mantendo o conteúdo gráfico inalterado.

### Etapa 1: inicializar o fluxo de entrada do arquivo eps
`PsDocument` representa um documento EPS e fornece métodos para acessar seu conteúdo. O código a seguir abre o arquivo EPS como um fluxo e cria uma instância de `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Etapa 2: obter metadados xmp
`GetXmpMetadata()` recupera o pacote XMP incorporado no arquivo EPS. Se nenhum pacote existir, a API gera um novo com base nos comentários PostScript existentes.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Etapa 3: alterar valores dos metadados xmp
`AddArrayItem()` adiciona um novo valor a um array XMP existente sem sobrescrever outras entradas. Use‑o para acrescentar títulos, criadores ou tags personalizadas aos metadados.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Etapa 4: salvar o arquivo eps com metadados xmp alterados
`Save()` grava o pacote XMP modificado de volta no arquivo EPS enquanto preserva o conteúdo PostScript original. Forneça o caminho de saída para criar um novo arquivo ou sobrescrever o original.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Problemas comuns e solução de problemas

- **Null XMP packet** – Se `GetXmpMetadata()` retornar `null`, verifique se o arquivo EPS contém ao menos um bloco de comentário; caso contrário, crie manualmente uma nova instância `XmpMetadata`.  
- **Encoding issues** – Use UTF‑8 ao adicionar valores de string para evitar corrupção de caracteres em idiomas não‑ASCII.  
- **Large files** – Para arquivos EPS maiores que 150 MB, considere fazer streaming da entrada via `FileStream` com um buffer para manter o uso de memória baixo.

## Perguntas frequentes

**Q: O Aspose.Page é compatível com todos os ambientes .NET?**  
A: Sim, o Aspose.Page funciona em .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6/7, oferecendo comportamento de API consistente no Windows, Linux e macOS.

**Q: Posso usar o Aspose.Page gratuitamente?**  
A: Você pode avaliar a biblioteca com um download de avaliação gratuita a partir da [página de compra da Aspose](https://purchase.aspose.com/buy). Uma licença comercial é necessária para implantações em produção.

**Q: Licenças temporárias estão disponíveis para o Aspose.Page?**  
A: Licenças temporárias podem ser obtidas na [página de licença temporária](https://purchase.aspose.com/temporary-license/) para projetos de curto prazo ou períodos de avaliação.

**Q: Onde posso encontrar suporte da comunidade para o Aspose.Page?**  
A: Participe da discussão no [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para fazer perguntas e compartilhar soluções com outros desenvolvedores.

**Q: Qual é a versão mais recente do Aspose.Page para .NET?**  
A: Consulte a [documentação](https://reference.aspose.com/page/net/) oficial para as notas de versão mais recentes e links de download.

---

**Última atualização:** 2026-08-08  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Tutoriais relacionados

- [Alterar itens de array com Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Adicionar propriedades simples com Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Adicionar namespace com Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}