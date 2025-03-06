---
title: Redimensione imagens EPS com Aspose.Page para .NET
linktitle: Redimensionar imagens EPS
second_title: API Aspose.Page .NET
description: Explore o processo contínuo de redimensionamento de imagens EPS em .NET usando Aspose.Page. Obtenha precisão em pontos, polegadas, milímetros e porcentagens sem esforço.
weight: 11
url: /pt/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Redimensione imagens EPS com Aspose.Page para .NET

## Introdução

Você deseja redimensionar imagens EPS perfeitamente usando Aspose.Page for .NET? Este tutorial é o seu guia completo para manipular facilmente o tamanho de imagens EPS em várias unidades, como pontos, polegadas, milímetros e porcentagens. Aspose.Page for .NET fornece um conjunto poderoso de ferramentas e, neste tutorial, orientaremos você no processo passo a passo.

## Pré-requisitos

Antes de mergulhar na magia do redimensionamento, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Biblioteca Aspose.Page for .NET: Certifique-se de ter a biblioteca Aspose.Page for .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/page/net/).

- Diretório de documentos: crie um diretório onde você armazenará seu arquivo EPS de entrada e os arquivos redimensionados de saída.

Agora que você configurou tudo, vamos importar os namespaces necessários e nos aprofundar no guia passo a passo.

## Importar namespaces

Em seu projeto .NET, comece importando os namespaces necessários para trabalhar com Aspose.Page. Adicione o seguinte código no início do seu arquivo:

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

## Etapa 1: redimensionar em pontos

Vamos começar redimensionando uma imagem EPS em pontos. Os pontos são uma unidade de medida padrão na indústria gráfica.

```csharp
public static void ResizeInPoints()
{
    // Seu diretório de documentos
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Etapa 2: redimensionar em polegadas

Agora, vamos redimensionar uma imagem EPS em polegadas, uma unidade comum usada em design gráfico.

```csharp
public static void ResizeInInches()
{
    // Seu diretório de documentos
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Etapa 3: redimensionar em milímetros

Agora, vamos redimensionar uma imagem EPS em milímetros, outra unidade amplamente utilizada em design e impressão.

```csharp
public static void ResizeInMillimeters()
{
    // Seu diretório de documentos
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Etapa 4: redimensionar em porcentagens

Finalmente, vamos redimensionar uma imagem EPS usando porcentagens, proporcionando uma abordagem flexível para ajustar o tamanho da imagem.

```csharp
public static void ResizeInPercents()
{
    // Seu diretório de documentos
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Sinta-se à vontade para integrar esses métodos ao seu projeto e você redimensionará imagens EPS sem esforço. Experimente unidades diferentes para atingir as dimensões desejadas.

## Conclusão

Parabéns! Você dominou a arte de redimensionar imagens EPS com Aspose.Page for .NET. Esta poderosa biblioteca abre um mundo de possibilidades para a manipulação de gráficos vetoriais. Esteja você projetando para mídia impressa ou digital, Aspose.Page permite que você obtenha resultados precisos e personalizados.

## Perguntas frequentes

### Q1: Posso redimensionar várias imagens EPS simultaneamente?

A1: Sim, você pode percorrer uma coleção de arquivos EPS, aplicando os métodos de redimensionamento de acordo.

### Q2: O Aspose.Page é compatível com outros formatos de imagem?

A2: Aspose.Page concentra-se principalmente nos formatos PostScript e EPS. Para outros formatos de imagem, considere usar Aspose.Imaging.

### P3: Há alguma consideração de licenciamento para projetos comerciais?

 A3: Sim, certifique-se de ter uma licença válida. Visita[aqui](https://purchase.aspose.com/buy) para detalhes de licenciamento.

### Q4: Posso experimentar o Aspose.Page antes de comprar?

 A4: Com certeza! Você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### P5: Onde posso procurar ajuda adicional ou discutir problemas?

 A5: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para se conectar com a comunidade e obter assistência.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
