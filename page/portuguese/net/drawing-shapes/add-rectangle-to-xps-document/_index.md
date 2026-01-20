---
date: 2026-01-20
description: Aprenda a criar um documento XPS, adicionar um retângulo e salvar o arquivo
  XPS usando o Aspose.Page para .NET neste guia passo a passo.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'Criar documento XPS: Adicionar retângulo com Aspose.Page para .NET'
url: /pt/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Documento XPS: Adicionar Retângulo com Aspose.Page para .NET

## Introdução

Neste tutorial você **criará arquivos de documento XPS** e desenhará um retângulo dentro deles usando a biblioteca Aspose.Page para .NET. Adicionar formas como retângulos é uma necessidade comum quando você precisa gerar faturas, relatórios ou gráficos personalizados programaticamente. Siga os passos abaixo e terá um arquivo XPS pronto‑para‑uso em minutos.

## Respostas Rápidas
- **O que posso gerar?** Documentos XPS com gráficos vetoriais e texto.  
- **Qual biblioteca?** Aspose.Page para .NET (versão de avaliação gratuita disponível).  
- **Quanto tempo leva?** Cerca de 5‑10 minutos para implementar e executar.  
- **Preciso de licença?** Uma licença temporária é necessária para uso em produção.  
- **Posso salvar o resultado como arquivo XPS?** Sim – o método `Save` grava um **arquivo XPS salvo** no disco.

## O que é “criar documento XPS”?

Criar um documento XPS significa construir programaticamente uma descrição de página no formato XML Paper Specification. O arquivo resultante é independente de resolução, ideal para impressão e exibição de alta qualidade em diferentes plataformas.

## Por que usar Aspose.Page para criar documento XPS?

- **Suporte total ao .NET** – funciona com .NET Framework, .NET Core e .NET 5/6+.  
- **API de desenho rica** – inclui geometria de caminho, pincéis, canetas e manipulação de texto.  
- **Sem dependências externas** – tudo roda no processo sem necessidade de Office ou Acrobat.  

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem o seguinte:

1. **Aspose.Page para .NET** – faça o download [aqui](https://releases.aspose.com/page/net/).  
2. **Uma pasta gravável** onde os arquivos XPS gerados serão armazenados.

## Importar Namespaces

No seu projeto .NET, importe os namespaces necessários:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: Definir o Diretório do Documento

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Dica profissional:** Use um caminho absoluto ou `Path.Combine` para evitar problemas de separador de caminho em diferentes SOs.

## Etapa 2: Criar um Novo Documento XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

Neste ponto você **criou um objeto de documento XPS** que armazenará todos os elementos de desenho.

## Etapa 3: Adicionar um Retângulo (usando create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

A chamada `CreatePathGeometry` **cria a geometria de caminho** que define o contorno do retângulo. Você pode modificar a string de comando semelhante a SVG para desenhar outras formas.

## Etapa 4: Salvar o Documento (salvar arquivo XPS)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Chamar `Save` grava o **arquivo XPS salvo** no local que você especificou.

Parabéns! Você criou com sucesso um **documento XPS**, adicionou um retângulo e salvou o arquivo.

## Problemas Comuns e Soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| `FileNotFoundException` em `doc.Save` | `dataDir` aponta para uma pasta inexistente | Garanta que o diretório exista ou crie‑o com `Directory.CreateDirectory(dataDir)`. |
| Retângulo não visível | Perfil de cor de traço ausente ou geometria de caminho malformada | Verifique o caminho do arquivo ICC e a string de geometria (`M … Z`). |
| Desempenho lento em documentos grandes | Muitas chamadas individuais a `AddPath` | Agrupe operações de desenho ou reutilize objetos de pincel/caneta. |

## Perguntas Frequentes

**P: O Aspose.Page é compatível com todas as aplicações .NET?**  
R: Sim, o Aspose.Page foi projetado para funcionar perfeitamente com todas as aplicações .NET.

**P: Onde posso encontrar a documentação do Aspose.Page para .NET?**  
R: A documentação está disponível [aqui](https://reference.aspose.com/page/net/).

**P: Posso experimentar o Aspose.Page para .NET gratuitamente antes de comprar?**  
R: Sim, você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

**P: Como posso obter uma licença temporária para o Aspose.Page para .NET?**  
R: Visite [este link](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária.

**P: Onde posso buscar suporte da comunidade ou fazer perguntas relacionadas ao Aspose.Page para .NET?**  
R: Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade.

---

**Última atualização:** 2026-01-20  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}