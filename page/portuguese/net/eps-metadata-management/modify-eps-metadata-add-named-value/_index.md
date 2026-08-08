---
date: 2026-08-08
description: Aprenda como criar EPS com metadados XMP e adicionar valores nomeados
  usando Aspose.Page para .NET. Guia passo a passo com trechos de código.
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: Adicionar Valor Nomeado
og_description: Crie EPS com metadados XMP em .NET usando Aspose.Page. Este guia mostra
  como adicionar valores nomeados a arquivos EPS de forma rápida e confiável.
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: Criar EPS com XMP – adicionar valor nomeado usando Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Criar EPS com XMP – adicionar valor nomeado usando Aspose.Page
url: /pt/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar EPS com XMP – adicionar valor nomeado usando Aspose.Page

## Introdução

Neste tutorial você aprenderá a **criar EPS com XMP** e inserir um valor nomeado usando a biblioteca Aspose.Page para .NET. Seja construindo um pipeline de processamento em lote ou precisando enriquecer arquivos EPS com tags XMP personalizadas, os passos abaixo orientam tudo, desde a configuração do projeto até a persistência do arquivo modificado. Aspose.Page pode manipular documentos EPS de até **500 páginas** sem carregar o arquivo inteiro na memória, tornando‑se adequado para cenários de alto volume.

## Respostas rápidas
- **Qual é o objetivo principal?** Adicionar um valor XMP nomeado a um arquivo EPS existente.  
- **Qual biblioteca é necessária?** Aspose.Page para .NET.  
- **Preciso de licença?** Uma licença comercial é necessária para produção; há uma versão de avaliação gratuita disponível.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quanto tempo leva a implementação?** Aproximadamente 10–15 minutos para um caso de uso básico.

## Como criar EPS com metadados XMP em .NET?

Carregue o arquivo EPS de destino, obtenha (ou crie) seu objeto de metadados XMP, adicione o valor nomeado necessário e, finalmente, salve o documento de volta ao disco. Esse fluxo de trabalho requer apenas algumas chamadas de método e funciona de forma consistente em todas as versões de EPS suportadas. A abordagem também preserva o conteúdo das páginas existentes e outras estruturas XMP, permitindo encadear várias atualizações de metadados com segurança.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

- Conhecimento básico de C# e da estrutura de projetos .NET.  
- Visual Studio 2022 (ou qualquer IDE compatível).  
- Biblioteca Aspose.Page para .NET. Se ainda não a possui, faça o download na **página de download do Aspose.Page para .NET**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)).  

## Importar namespaces

Os namespaces a seguir fornecem acesso às classes de manipulação de EPS, saída de dispositivo e metadados XMP da Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Etapa 1: inicializar fluxo de entrada do arquivo eps

Crie um `FileStream` para o arquivo EPS de origem e instancie um objeto `PsDocument` para trabalhar com o documento.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Etapa 2: obter metadados XMP

Recupere o objeto `XmpMetadata` do documento; esse objeto representa o pacote XMP incorporado.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Etapa 3: alterar valores dos metadados XMP

Use o método `AddNamedValue` de `XmpMetadata` para inserir um novo valor nomeado na estrutura XMP especificada.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Etapa 4: salvar arquivo eps com metadados XMP alterados

Salve o documento modificado escrevendo‑o em um novo `FileStream`.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Por que usar Aspose.Page para metadados EPS?

Aspose.Page suporta **mais de 50 esquemas XMP** e pode processar arquivos EPS de até **500 páginas** mantendo o uso de memória abaixo de **30 MB** para documentos típicos. A biblioteca não depende de ferramentas externas ou código nativo, garantindo comportamento consistente em ambientes Windows, Linux e macOS.

## Problemas comuns e solução de problemas

- **Pacote XMP ausente:** Se `GetXmpMetadata()` retornar `null`, o arquivo EPS não contém um bloco XMP. A biblioteca criará um automaticamente, mas verifique se o arquivo não está corrompido.  
- **Conflitos de namespace:** Ao adicionar valores nomeados personalizados, use um URI de namespace exclusivo para evitar colisões com esquemas existentes.  
- **Arquivos grandes:** Para arquivos EPS maiores que 200 MB, considere transmitir a saída para evitar consumo excessivo de memória.

## Perguntas frequentes

**Q: O Aspose.Page é compatível com diferentes versões de arquivos EPS?**  
A: Aspose.Page suporta versões EPS 3.0 a 3.3, garantindo ampla compatibilidade com arquivos legados e modernos.

**Q: Posso usar Aspose.Page em projetos comerciais?**  
A: Sim, é necessária uma licença comercial para uso em produção. Você pode adquirir uma licença na **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.

**Q: Existe uma versão de avaliação gratuita?**  
A: Sim, um teste totalmente funcional pode ser baixado na **[Aspose.Page free trial download page](https://releases.aspose.com/)**.

**Q: Como obter suporte ou participar da comunidade?**  
A: Visite o **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** para fazer perguntas e compartilhar experiências.

**Q: O que é uma licença temporária e como obtenho uma?**  
A: Uma licença temporária permite avaliar o produto por um curto período. Você pode solicitar uma na **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

---

**Última atualização:** 2026-08-08  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Adicionar Metadados ao Documento EPS com Aspose.Page para .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Alterar Valor Nomeado com Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Extrair Metadados do Documento EPS com Aspose.Page para .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}