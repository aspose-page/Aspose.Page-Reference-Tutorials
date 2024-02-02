---
title: Transformações PS com Aspose.Page para .NET
linktitle: Transformações PS
second_title: API Aspose.Page .NET
description: Libere o potencial do Aspose.Page for .NET com este guia abrangente sobre transformações PostScript. Crie gráficos dinâmicos sem esforço.
type: docs
weight: 12
url: /pt/net/canvas-manipulation/transformationsps/
---
## Introdução

Bem-vindo ao mundo do Aspose.Page for .NET, onde você pode liberar o poder das transformações em documentos PostScript. Este tutorial irá guiá-lo através de várias transformações, como translação, dimensionamento, rotação, cisalhamento e transformações complexas, permitindo criar gráficos visualmente impressionantes e dinâmicos.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Biblioteca Aspose.Page for .NET: certifique-se de ter a biblioteca Aspose.Page for .NET integrada ao seu projeto. Você pode baixá-lo no[Link para Download](https://releases.aspose.com/page/net/).

- Diretório de documentos: configure um diretório para seus documentos e substitua o espaço reservado no código pelo caminho real.

## Importar namespaces

No seu projeto .NET, importe os namespaces necessários para trabalhar com Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora, vamos dividir cada exemplo em várias etapas em um formato de guia passo a passo.


## Sem transformações

### Etapa 1: criar fluxo de saída

```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";

// Crie fluxo de saída para documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Crie opções de salvamento com valores padrão
    PsSaveOptions options = new PsSaveOptions();

    // Crie um novo documento PS de 1 página
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Crie um caminho gráfico a partir do retângulo
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Defina a pintura no estado gráfico no nível superior
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Preencha o primeiro retângulo que está no estado gráfico de nível superior e sem nenhuma transformação
    document.Fill(path);

    // Fechar página atual
    document.ClosePage();

    // Salve o documento
    document.Save();
}
```

Este código cria um documento PostScript sem transformações, preenchendo um retângulo com a cor laranja.

## Tradução

### Etapa 1: salvar o estado dos gráficos

```csharp
// Salve o estado gráfico para retornar a este estado após a transformação
document.WriteGraphicsSave();
```

Esta etapa salva o estado atual do gráfico, permitindo retornar a ele após a transformação.

### Etapa 2: traduzir o estado dos gráficos

```csharp
// Deslocar o estado gráfico atual 250 para a direita
document.Translate(250, 0);
```

Traduza o estado gráfico atual adicionando um componente de tradução e, em seguida, defina a pintura no estado gráfico atual para uma cor azul.

### Etapa 3: preencher retângulo com transformação de tradução

```csharp
// Definir pintura no estado gráfico atual
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Preencha o segundo retângulo no estado gráfico atual (possui transformação de tradução)
document.Fill(path);
```

Esta etapa preenche o segundo retângulo no estado gráfico atual, que agora inclui a transformação de tradução.

### Etapa 4: restaurar o estado dos gráficos

```csharp
// Restaurar o estado gráfico para o nível anterior (superior)
document.WriteGraphicsRestore();
```

Após preencher o retângulo, restaure o estado gráfico ao nível anterior.

Continue este guia passo a passo para cada tipo de transformação, incluindo Dimensionamento, Rotação, Cisalhamento e Transformações Complexas.

## Conclusão

Parabéns! Você navegou com sucesso pelos recursos transformadores do Aspose.Page for .NET. Agora experimente diferentes combinações e dê asas à sua criatividade nas transformações de documentos PostScript.

## Perguntas frequentes

### Q1: Como posso aplicar múltiplas transformações a um único objeto?

A1: Para aplicar múltiplas transformações, use o`Transform` método com uma matriz de transformação personalizada.

### Q2: Posso visualizar as transformações antes de salvar o documento?

A2: Sim, você pode visualizar as transformações renderizando o documento e visualizando-o em um visualizador adequado.

### Q3: É possível aplicar transformações a elementos específicos de um documento?

R3: Sim, você pode isolar transformações em elementos gráficos específicos em um documento.

### P4: Há alguma consideração de desempenho ao lidar com transformações complexas?

A4: Transformações complexas podem afetar o desempenho, portanto, otimize seu código para obter eficiência.

### P5: Como posso obter suporte ou assistência para dúvidas relacionadas ao Aspose.Page?

 A5: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio e discussões da comunidade.