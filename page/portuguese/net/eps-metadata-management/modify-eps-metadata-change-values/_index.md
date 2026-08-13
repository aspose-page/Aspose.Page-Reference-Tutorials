---
date: 2026-08-13
description: Aprenda a usar o Aspose.Page para alterar valores EPS em aplicações .NET,
  incluindo atualizações passo a passo de metadados XMP.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Alterar Valores
og_description: O tutorial Aspose.Page altera valores EPS mostra como modificar metadados
  XMP dentro de arquivos EPS usando .NET. Siga o guia passo a passo para atualizar
  criador, título e data de modificação instantaneamente.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page altera valores EPS com .NET tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page altera valores EPS com .NET – tutorial
url: /pt/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page alterar valores EPS com .NET – tutorial

## Introdução

Neste tutorial você descobrirá como **aspose.page change eps values** editando os metadados XMP incorporados em um arquivo EPS. Seja para atualizar o nome do criador, ajustar o título ou corrigir a data de modificação, o Aspose.Page para .NET oferece uma API limpa, orientada a código, que funciona no Windows, Linux e macOS. Ao final do guia, você terá um trecho reutilizável que pode ser inserido em qualquer serviço ou aplicativo console .NET.

## Respostas rápidas
- **O que o tutorial cobre?** Alteração de metadados XMP (criador, título, data de modificação) em arquivos EPS usando Aspose.Page para .NET.  
- **Qual versão da biblioteca é necessária?** Qualquer versão do Aspose.Page para .NET que suporte XMP (v24.10+).  
- **Preciso de uma licença?** Uma licença temporária é necessária para produção; uma avaliação gratuita funciona para desenvolvimento.  
- **Posso executar isso no .NET Core?** Sim – a API é compatível com .NET 5, .NET 6 e .NET Core 3.1+.  
- **Quanto tempo leva a implementação?** Cerca de 5‑10 minutos para uma atualização básica de metadados.

## O que são metadados XMP?

Metadados XMP são um bloco XML padronizado que armazena informações descritivas (autor, título, datas) dentro de arquivos EPS e outros formatos gráficos. Eles são incorporados diretamente no cabeçalho do arquivo e podem ser lidos por muitas ferramentas de design e publicação, permitindo um tratamento consistente de metadados entre plataformas. Atualizar o XMP permite que aplicativos subsequentes exibam as propriedades corretas do documento sem alterar o conteúdo visual.

## Por que usar Aspose.Page para metadados EPS?

O Aspose.Page pode processar **30+** formatos gráficos e lida com arquivos EPS de até **1 GB** sem carregar todo o arquivo na memória, proporcionando uma redução de **70 %** no uso de RAM em comparação com a análise de fluxo ingênua. A biblioteca também garante que a renderização visual do EPS permaneça inalterada após as edições de metadados.

## Pré-requisitos

Antes de começar, certifique‑se de que o seguinte esteja pronto:

1. **Biblioteca Aspose.Page para .NET** – faça o download na página oficial de lançamentos do Aspose.Page para .NET [here](https://releases.aspose.com/page/net/). Você também pode explorar outros lançamentos de produtos Aspose [here](https://releases.aspose.com/).  
2. **Diretório de documentos** – crie uma pasta na sua máquina onde os arquivos EPS de origem e os arquivos de saída serão armazenados.

Agora que o ambiente está configurado, vamos importar os namespaces necessários.

## Importar namespaces

O namespace `Aspose.Page` fornece as classes principais, enquanto `System.IO` oferece recursos de manipulação de streams.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Como alterar valores de metadados EPS?

Carregue o arquivo EPS, recupere seu pacote XMP, modifique os campos necessários e grave o EPS atualizado no disco. O processo não requer renderização do conteúdo da página, sendo rápido e eficiente em memória. Siga as etapas detalhadas para ver exemplos de código para cada operação. Este fluxo de ponta a ponta está coberto nas etapas abaixo.

### Etapa 1: inicializar fluxo de entrada do arquivo EPS

Crie um `FileStream` somente‑leitura que aponta para o arquivo EPS de origem.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Etapa 2: criar instância PsDocument a partir do fluxo

`PsDocument` é o objeto de nível superior que representa um documento EPS na memória. Ele fornece acesso tanto ao conteúdo da página quanto aos metadados XMP incorporados.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Etapa 3: obter metadados XMP

A propriedade `XmpMetadata` retorna um objeto `XmpPacket` que pode ser consultado e editado.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Etapa 4: modificar valores de metadados XMP

Agora você alterará três campos comuns: **ModifyDate**, **Creator** e **Title**.

#### Etapa 4.1: alterar valor ModifyDate

Defina o `ModifyDate` para o timestamp UTC atual.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Etapa 4.2: alterar valor Creator

Substitua o criador existente pelo nome da sua aplicação.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Etapa 4.3: alterar valor Title

Atualize o título para refletir o novo propósito do conteúdo.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Etapa 5: salvar arquivo EPS com metadados XMP alterados

Após a edição, grave o documento novamente.

#### Etapa 5.1: criar fluxo de saída

Abra um `FileStream` para o arquivo EPS de destino.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Etapa 5.2: salvar arquivo EPS

Chame `Save` na instância `PsDocument`, passando o fluxo de saída.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Por fim, feche o fluxo de entrada para liberar o manipulador do arquivo.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Parabéns! Você alterou com sucesso **aspose.page change eps values** atualizando os metadados XMP dentro de um arquivo EPS.

## Armadilhas comuns e solução de problemas

- **Pacote XMP vazio** – Alguns arquivos EPS são gerados sem XMP. Nesse caso, crie um novo `XmpPacket` via `new XmpPacket()` antes de atribuir valores.  
- **Arquivos grandes** – Para EPS maiores que 500 MB, habilite o buffer de stream definindo `PsDocumentOptions.UseMemoryMappedFiles = true` para evitar `OutOfMemoryException`.  
- **Formato de data incorreto** – O XMP espera ISO 8601. Use `DateTime.UtcNow.ToString("o")` para gerar uma string compatível.

## Perguntas frequentes

**Q: Posso usar Aspose.Page para .NET com outros formatos gráficos?**  
A: Sim, a biblioteca suporta mais de 30 formatos, incluindo PDF, SVG e AI, mas as APIs de edição XMP são específicas para EPS e PDF.

**Q: Uma versão de avaliação está disponível?**  
A: Sim, você pode experimentar o Aspose.Page para .NET com a avaliação gratuita disponível na página de lançamentos da Aspose [here](https://releases.aspose.com/).

**Q: Onde encontro documentação detalhada?**  
A: A referência completa da API Aspose.Page .NET pode ser encontrada [here](https://reference.aspose.com/page/net/).

**Q: Como obtenho uma licença temporária?**  
A: Você pode obter uma licença temporária [here](https://purchase.aspose.com/temporary-license/).

**Q: Posso comprar Aspose.Page para .NET?**  
A: Absolutamente! Visite a página de compra do Aspose.Page [here](https://purchase.aspose.com/buy) para opções de licenciamento.

---

**Última atualização:** 2026-08-13  
**Testado com:** Aspose.Page 24.10 para .NET  
**Autor:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Tutoriais relacionados

- [Adicionar Metadados ao Documento EPS com Aspose.Page para .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Extrair Metadados do Documento EPS com Aspose.Page para .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Alterar Valor Nomeado com Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}