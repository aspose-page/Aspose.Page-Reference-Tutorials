---
title: Cortar imagens EPS com Aspose.Page para .NET
linktitle: Cortar imagens EPS
second_title: API Aspose.Page .NET
description: Explore o mundo contínuo da manipulação de imagens EPS em .NET com Aspose.Page. Corte e redimensione imagens sem esforço para obter resultados impressionantes.
type: docs
weight: 10
url: /pt/net/image-manipulation/crop-eps-images/
---
## Introdução

Você está tendo dificuldades para manipular imagens EPS em seus aplicativos .NET? Não procure mais! Neste tutorial, iremos guiá-lo através do processo de corte de imagens EPS usando a poderosa biblioteca Aspose.Page for .NET. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este guia passo a passo o ajudará a obter um corte preciso de imagens sem esforço.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Conhecimento prático de desenvolvimento .NET.
-  Biblioteca Aspose.Page para .NET instalada. Se não, você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).
- Uma imagem EPS de amostra (substitua "input.eps" no código pelo seu arquivo real).

## Importar namespaces

Vamos começar importando os namespaces necessários para que nosso código funcione sem problemas. 

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

Agora, vamos dividir o tutorial em várias etapas.

## Etapa 1: inicializar PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Inicialize um`PsDocument` objeto com o fluxo EPS de entrada.

## Etapa 2: extrair a caixa delimitadora

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Recupere a caixa delimitadora inicial da imagem EPS.

## Etapa 3: criar fluxo de saída

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Crie um fluxo de saída para a imagem EPS recortada.

## Etapa 4: definir a nova caixa delimitadora

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Defina uma nova caixa delimitadora para corte. Certifique-se de que os novos valores estejam dentro da caixa delimitadora inicial.

## Etapa 5: cortar e salvar

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Corte a imagem EPS usando a nova caixa delimitadora e salve-a no fluxo de saída.

Repita essas etapas para diferentes cenários de redimensionamento.

## Redimensionar imagens EPS

### Redimensionar em polegadas

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Redimensione a imagem EPS e salve-a com as dimensões especificadas em polegadas.

### Redimensionar em milímetros

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Redimensione a imagem EPS e salve-a com as dimensões especificadas em milímetros.

### Redimensionar em porcentagem

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Redimensione a imagem EPS e salve-a com as dimensões especificadas em porcentagens.

## Conclusão

Parabéns! Você aprendeu com sucesso como cortar e redimensionar imagens EPS usando Aspose.Page for .NET. Agora, aprimore seus recursos de manipulação de imagens e leve seus aplicativos .NET para o próximo nível.

## Perguntas frequentes

### Q1: Posso usar Aspose.Page for .NET com outros formatos de imagem?

A1: Aspose.Page concentra-se principalmente em imagens EPS, mas Aspose fornece várias bibliotecas para diferentes formatos. Verifique a documentação para formatos específicos.

### Q2: Como posso obter uma licença temporária para Aspose.Page for .NET?

 A2: Visita[esse link](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária para testes.

### Q3: Há alguma limitação no tamanho da imagem que posso processar com Aspose.Page for .NET?

A3: Aspose.Page foi projetado para lidar com imagens de vários tamanhos. No entanto, o desempenho pode variar com base na complexidade da imagem.

### Q4: Existe um fórum da comunidade para discussões do Aspose.Page?

 A4: Sim, você pode interagir com a comunidade Aspose.Page[aqui](https://forum.aspose.com/c/page/39).

### Q5: Onde posso encontrar documentação detalhada para Aspose.Page for .NET?

 A5: Consulte a documentação[aqui](https://reference.aspose.com/page/net/).