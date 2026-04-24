---
date: 2026-01-05
description: Aprenda a transformar documentos XPS sem esforço com o Aspose.Page para
  .NET. Siga nosso guia passo a passo para transformações perfeitas.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Como transformar XPS com Aspose.Page para .NET
url: /pt/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como transformar XPS com Aspose.Page para .NET

## Introdução

Bem‑vindo ao mundo do Aspose.Page para .NET, uma biblioteca poderosa que permite realizar várias transformações em documentos XPS de forma simples. **Neste tutorial, você descobrirá como transformar documentos XPS usando Aspose.Page para .NET**, seja você um desenvolvedor experiente ou esteja começando agora. Percorreremos cada passo, explicaremos o motivo de cada transformação e daremos dicas práticas que você pode aplicar em projetos reais.

## Respostas rápidas
- **O que é possível fazer?** Criar, transladar, dimensionar e girar elementos de canvas XPS programaticamente.  
- **Qual biblioteca é necessária?** Aspose.Page para .NET (versão mais recente).  
- **Preciso de licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Plataformas suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para as transformações básicas mostradas aqui.

## O que significa “como transformar xps”?
A expressão *como transformar xps* refere‑se à modificação programática do layout, tamanho e orientação dos elementos dentro de um documento XPS (XML Paper Specification). Usando Aspose.Page, você pode aplicar transformações baseadas em matrizes aos canvases, obtendo controle fino sobre posicionamento, dimensionamento e rotação sem editar manualmente o XML do XPS.

## Por que usar Aspose.Page para transformações XPS?
- **Integração total com .NET** – funciona perfeitamente com Visual Studio, Rider e outras IDEs.  
- **Sem dependências externas** – a API cuida de todos os detalhes de baixo nível do XPS para você.  
- **Suporte rico a transformações** – transladar, dimensionar, girar e combinar múltiplas transformações em uma única chamada.  
- **Desempenho otimizado** – adequado para gerar relatórios, faturas ou quaisquer gráficos imprimíveis sob demanda.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- **Biblioteca Aspose.Page para .NET** – faça o download e instale a partir da documentação oficial: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Ambiente de desenvolvimento** – Visual Studio, Visual Studio Code ou qualquer outra IDE compatível com .NET.  
- **Diretório de documentos** – uma pasta na sua máquina onde você lerá/escreverá arquivos XPS. Substitua o placeholder no código pelo caminho real.

Agora que tudo está configurado, vamos ao código.

## Importar namespaces

Primeiro, importe os namespaces que expõem as classes do Aspose.Page necessárias:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Como transformar XPS – Guia passo a passo

### Passo 1: Criar um novo documento XPS

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Explicação*: Definimos a pasta que contém nossos arquivos de origem e saída e, em seguida, instanciamos um `XpsDocument` vazio. Esse objeto será o canvas para todas as transformações subsequentes.

### Passo 2: Criar um canvas principal

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Por que isso importa*: O canvas principal atua como contêiner para todos os demais canvases. Ao aplicar um pequeno deslocamento garantimos que o conteúdo não seja cortado na borda da página.

### Passo 3: Criar uma geometria de caminho retangular

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Dica*: A string de caminho segue a sintaxe padrão do XPS (`M` para mover, `L` para linha, `Z` para fechar). Ajuste as coordenadas para mudar o tamanho do retângulo.

### Passo 4: Adicionar um preenchimento para retângulos

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: Use `CreateColor` com valores RGB para combinar com a paleta da sua marca.

### Passo 5: Adicionar um novo canvas sem transformações

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Aqui simplesmente posicionamos um retângulo na página sem nenhuma transformação extra — útil como elemento de referência.

### Passo 6: Adicionar um novo canvas com transformação de translação

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*O que está acontecendo?* A primeira matriz move o retângulo 200 unidades para baixo. A chamada subsequente `Translate` o desloca 500 unidades para a direita, demonstrando como múltiplas translações podem ser encadeadas.

### Passo 7: Adicionar um novo canvas com dupla transformação de escala

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Por que escalar?* Escalar por 2 dobra a largura e a altura do retângulo, permitindo criar gráficos maiores sem redefinir a geometria.

### Passo 8: Adicionar um novo canvas com rotação em torno de um ponto

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Insight chave*: `RotateAround` gira o canvas em torno de um ponto personalizado (aqui (100, 50)), oferecendo controle fino sobre o ponto de ancoragem da rotação.

### Passo 9: Salvar o documento XPS resultante

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Depois que todas as transformações são aplicadas, o documento é salvo em `output1.xps`. Abra o arquivo em qualquer visualizador XPS para ver os retângulos empilhados com suas respectivas translações, escalas e rotações.

## Problemas comuns e solução de erros

| Sintoma | Causa provável | Correção |
|---------|----------------|----------|
| Arquivo de saída vazio | `dataDir` aponta para uma pasta inexistente | Garanta que o diretório exista ou use um caminho absoluto |
| Retângulos não posicionados como esperado | Valores de matriz incorretos | Verifique a ordem das chamadas `Translate`, `Scale` e `RotateAround` |
| Cores aparecem erradas | Valores RGB fora do intervalo 0‑255 | Use valores de byte válidos para cada canal |

## Perguntas frequentes

**P: O Aspose.Page para .NET é compatível com todos os ambientes de desenvolvimento .NET?**  
R: Sim, funciona perfeitamente com Visual Studio, Visual Studio Code, Rider e qualquer IDE que suporte .NET.

**P: Onde posso encontrar exemplos adicionais e documentação detalhada da API?**  
R: Visite a documentação oficial em [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**P: Posso experimentar o Aspose.Page antes de comprar a licença?**  
R: Absolutamente. Um teste gratuito está disponível aqui: [Aspose.Page Free Trial](https://releases.aspose.com/).

**P: Como obtenho uma licença temporária para testes?**  
R: Você pode solicitar uma através da página de licença temporária: [Temporary License](https://purchase.aspose.com/temporary-license/).

**P: Onde compro uma licença completa?**  
R: Compre diretamente na loja da Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Última atualização:** 2026-01-05  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}