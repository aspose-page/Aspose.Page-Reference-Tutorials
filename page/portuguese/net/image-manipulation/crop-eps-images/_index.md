---
date: 2026-03-16
description: Aprenda a recortar imagens EPS e redimensionar arquivos de imagem EPS
  no .NET usando o Aspose.Page. Siga este guia passo a passo para recortar EPS e redimensionar
  imagens EPS sem esforço.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Como recortar imagens EPS com Aspose.Page para .NET
url: /pt/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Recortar Imagens EPS com Aspose.Page para .NET

## Introdução

Se você precisa saber **como recortar EPS** imagens em uma aplicação .NET, você está no lugar certo. Neste tutorial, vamos guiá‑lo através do recorte e redimensionamento de arquivos EPS usando a poderosa biblioteca Aspose.Page para .NET. Seja aprimorando uma ferramenta de relatórios ou preparando gráficos para um serviço web, dominar esta técnica economizará tempo e fornecerá resultados perfeitos em pixels.

## Respostas Rápidas
- **Qual biblioteca lida com recorte de EPS?** Aspose.Page for .NET  
- **Método principal?** `doc.CropEps(outputStream, newBoundingBox)`  
- **Posso também redimensionar o EPS?** Sim – use `ResizeEps` com polegadas, milímetros ou porcentagens.  
- **Pré‑requisitos?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page instalado, um arquivo EPS.  
- **Tempo típico de implementação?** Cerca de 10 minutos para um fluxo básico de recorte‑e‑redimensionamento.

## Pré‑requisitos

Antes de mergulhar no código, certifique‑se de que você tem:

- Um conhecimento prático de desenvolvimento .NET.  
- Biblioteca Aspose.Page para .NET instalada. Caso não tenha, você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).  
- Uma imagem EPS de exemplo (substitua `"input.eps"` no código pelo seu arquivo real).

## Importar Namespaces

Vamos começar importando os namespaces que nos dão acesso às classes de manipulação de EPS.

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Como Recortar Imagens EPS – Guia Passo a Passo

### Etapa 1: Inicializar `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Criamos uma instância de `PsDocument` a partir do fluxo de entrada EPS. Este objeto representa o arquivo EPS na memória e nos dá acesso aos métodos de recorte e redimensionamento.

### Etapa 2: Extrair a Caixa Delimitadora Original

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

A caixa delimitadora indica as dimensões atuais da tela EPS. Conhecer esses valores ajuda a definir um retângulo de recorte seguro.

### Etapa 3: Criar um Fluxo de Saída

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Abrimos um fluxo gravável onde o EPS recortado será salvo. Usar um bloco `using` garante que o fluxo seja fechado corretamente.

### Etapa 4: Definir uma Nova Caixa Delimitadora

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Substitua os números pelas coordenadas que deseja manter. Certifique‑se de que os novos valores permaneçam dentro da caixa delimitadora original; caso contrário, a operação falhará.

### Etapa 5: Recortar e Salvar o EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Esta única linha realiza o recorte e grava o resultado em `output_crop.eps`. O método modifica o documento na memória, permitindo encadear outras operações se necessário.

## Redimensionar Imagem EPS

Após o recorte, frequentemente você deseja alterar o tamanho do EPS para exibição ou impressão. Aspose.Page suporta três unidades de medida.

### Redimensionar em Polegadas

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Redimensionar em Milímetros

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Redimensionar em Porcentagens

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Cada chamada sobrescreve a saída anterior, portanto, certifique‑se de criar um novo fluxo se precisar de arquivos separados para cada tamanho.

## Problemas Comuns & Solução de Problemas

| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| **Valores da caixa delimitadora fora do intervalo** | Nova caixa excede as dimensões originais | Verifique os valores de `initialBoundingBox` e escolha coordenadas dentro desse intervalo. |
| **Arquivo de saída está vazio** | Fluxo de saída não foi descarregado ou fechado | Garanta que o bloco `using` seja concluído antes de acessar o arquivo, ou chame `outputEpsStream.Flush()`. |
| **Escala inesperada** | Mistura de unidades (ex.: polegadas vs. milímetros) | Sempre especifique o enum `Units` correto que corresponde aos seus valores de tamanho. |

## Perguntas Frequentes

### Q1: Posso usar Aspose.Page para .NET com outros formatos de imagem?

A1: Aspose.Page foca principalmente em imagens EPS, mas a Aspose fornece várias bibliotecas para diferentes formatos. Consulte a documentação deles para formatos específicos.

### Q2: Como posso obter uma licença temporária para Aspose.Page para .NET?

A2: Visite [este link](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária para testes.

### Q3: Existem limitações ao tamanho da imagem que posso processar com Aspose.Page para .NET?

A3: Aspose.Page foi projetado para lidar com imagens de vários tamanhos. Contudo, o desempenho pode variar conforme a complexidade da imagem.

### Q4: Existe um fórum da comunidade para discussões sobre Aspose.Page?

A5: Sim, você pode interagir com a comunidade Aspose.Page [aqui](https://forum.aspose.com/c/page/39).

### Q5: Onde posso encontrar documentação detalhada para Aspose.Page para .NET?

A5: Consulte a documentação [aqui](https://reference.aspose.com/page/net/).

---

**Última atualização:** 2026-03-16  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}