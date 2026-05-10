---
date: 2026-03-03
description: Aprenda a usar o Aspose.Page para .NET para criar mosaicos de imagens
  em documentos XPS. Este guia passo a passo mostra como criar mosaicos de imagens
  de forma eficiente e melhorar o apelo visual.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Como usar o Aspose.Page para adicionar imagem em mosaico a um documento XPS
url: /pt/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Usar Aspose.Page para Adicionar Imagem em Mosaico a um Documento XPS

## Introdução

Se você está se perguntando **como usar Aspose** para dar aos seus arquivos XPS um estilo visual mais rico, você chegou ao lugar certo. Neste tutorial vamos percorrer os passos exatos necessários para **colocar uma imagem em mosaico** dentro de um documento XPS usando Aspose.Page para .NET. Ao final, você terá um trecho reutilizável que pode inserir em qualquer projeto .NET para criar gráficos de imagem em mosaico em tempo real.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Page for .NET  
- **Qual método cria o pincel em mosaico?** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **Posso controlar a opacidade?** Sim – defina `path.Fill.Opacity` (por exemplo, 0.5f)  
- **Preciso de uma licença para testes?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## O que é Aspose.Page e Por Que Usar Imagens em Mosaico?

Aspose.Page é uma API poderosa que permite a desenvolvedores gerar, editar e renderizar XPS, PDF e outros formatos baseados em página sem depender do Microsoft Office. Colocar uma imagem em mosaico — repetir um bitmap por toda uma forma — ajuda a preencher áreas grandes com padrões, marcas d'água ou texturas de fundo, mantendo o tamanho do arquivo baixo.

## Como Usar Aspose.Page para Imagens em Mosaico em Documentos XPS

A seguir você encontrará um exemplo completo, pronto‑para‑executar. Cada etapa é explicada em linguagem simples antes do bloco de código correspondente, para que você veja **por que** cada linha é importante.

### Pré-requisitos

- **Aspose.Page for .NET** – faça o download e referencie a biblioteca a partir do site oficial [here](https://reference.aspose.com/page/net/).  
- **Ambiente de desenvolvimento** – Visual Studio (qualquer edição) ou outro IDE .NET de sua preferência.

### Importar Namespaces

Primeiro, traga os namespaces necessários para o escopo para que o compilador saiba onde encontrar as classes XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Etapa 1: Definir o Diretório do Documento

Especifique onde o arquivo XPS gerado e a imagem de origem serão armazenados. Substitua o placeholder por uma pasta real em sua máquina.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Etapa 2: Criar um Novo Documento XPS

Instancie um documento XPS vazio que conterá o gráfico em mosaico.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Etapa 3: Adicionar uma Imagem em Mosaico

Aqui criamos um caminho retangular, preenchemos com um `ImageBrush` e definimos o pincel para o modo mosaico. A propriedade `TileMode` indica ao motor para repetir a imagem tanto horizontalmente quanto verticalmente. Ajuste as coordenadas do retângulo ou a imagem de origem conforme necessário para seu cenário.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Etapa 4: Salvar o Documento XPS Resultante

Finalmente, grave o documento no disco. O arquivo de saída pode ser aberto com qualquer visualizador XPS ou processado posteriormente com Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Problemas Comuns & Dicas

- **Erros de caminho** – Certifique‑se de que `dataDir` termina com uma barra final ou use `Path.Combine` para evitar problemas de separador ausente.  
- **Descompasso de tamanho da imagem** – A imagem de origem deve ser grande o suficiente para a área de mosaico; caso contrário, o padrão pode parecer esticado.  
- **Opacidade não visível** – Alguns visualizadores ignoram a opacidade em XPS; teste com um visualizador que suporte totalmente a renderização XPS (por exemplo, XPS Viewer no Windows).

## Perguntas Frequentes

### Q1: O Aspose.Page é compatível com todos os ambientes de desenvolvimento .NET?
A: Sim, Aspose.Page funciona com Visual Studio, Rider, VS Code e qualquer IDE que suporte .NET.

### Q2: Posso ajustar a opacidade da imagem em mosaico?
A: Absolutamente. O exemplo define `path.Fill.Opacity = 0.5f;` — você pode alterar o valor float entre 0 (transparente) e 1 (opaco).

### Q3: Existem outros modos de mosaico disponíveis no Aspose.Page para .NET?
A: Sim. Além de `XpsTileMode.Tile`, você pode usar `FlipX`, `FlipY` e `FlipXY` para criar padrões espelhados.

### Q4: Como lidar com licenças temporárias para Aspose.Page?
A: Consulte a página de [temporary license](https://purchase.aspose.com/temporary-license/) no site da Aspose para detalhes sobre como obter e aplicar uma licença de avaliação.

### Q5: Onde posso buscar ajuda ou conectar-me com a comunidade Aspose.Page?
A: Visite o [Aspose.Page forum](https://forum.aspose.com/c/page/39) para fazer perguntas, compartilhar trechos de código e aprender com outros desenvolvedores.

### Q6: Posso usar esta abordagem para criar um efeito de marca d'água?
A: Sim. Ao reduzir a opacidade e escolher uma imagem semitransparente, o pincel em mosaico funciona perfeitamente como uma marca d'água repetida.

## Conclusão

Agora você sabe **como usar Aspose** para adicionar uma imagem em mosaico a um documento XPS, controlar sua opacidade e salvar o resultado para uso posterior. Essa técnica é ideal para padrões de fundo, marcas d'água ou qualquer situação em que um gráfico repetido adiciona interesse visual sem inflar o tamanho do arquivo. Sinta‑se à vontade para experimentar diferentes formas, imagens e modos de mosaico para atender às necessidades do seu projeto.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}