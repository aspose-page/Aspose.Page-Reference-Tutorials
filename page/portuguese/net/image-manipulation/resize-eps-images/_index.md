---
date: 2026-03-03
description: Aprenda a redimensionar imagens EPS no .NET com Aspose.Page – um guia
  passo a passo sobre como redimensionar EPS usando pontos, polegadas, milímetros
  ou porcentagens.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Como redimensionar imagens EPS com Aspose.Page para .NET
url: /pt/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Redimensionar Imagens EPS com Aspose.Page para .NET

## Introdução

Você está procurando **como redimensionar EPS** de forma fluida usando Aspose.Page para .NET? Este tutorial é seu guia completo para manipular facilmente o tamanho de imagens EPS em várias unidades, como pontos, polegadas, milímetros e percentuais. Aspose.Page para .NET oferece um conjunto poderoso de ferramentas e, neste tutorial, vamos guiá‑lo passo a passo.

## Respostas Rápidas
- **Qual biblioteca lida com o redimensionamento de EPS?** Aspose.Page for .NET  
- **Quais unidades são suportadas?** Points, Inches, Millimeters, and Percents  
- **Preciso de uma licença para produção?** Sim – é necessária uma licença comercial  
- **Posso redimensionar vários arquivos de uma vez?** Absolutamente – basta percorrer os arquivos  
- **O .NET Core é suportado?** Sim, a API funciona com .NET Framework e .NET Core  

## O que é Redimensionamento de EPS?
Encapsulated PostScript (EPS) é um formato gráfico vetorial amplamente usado em fluxos de trabalho de impressão e design. Redimensionar um arquivo EPS altera sua caixa delimitadora sem rasterizar a arte, preservando a nitidez em qualquer escala.

## Por que Redimensionar Imagens EPS?
- **Manter a Qualidade de Impressão:** O dimensionamento vetorial mantém as bordas nítidas.  
- **Atender aos Requisitos de Layout:** Ajuste as dimensões para corresponder ao tamanho da página ou da tela.  
- **Automatizar Tarefas em Lote:** Redimensione programaticamente dezenas de arquivos em segundos.  

## Pré-requisitos

Antes de mergulhar na magia do redimensionamento, certifique‑se de que você tem os seguintes pré‑requisitos configurados:

- Biblioteca Aspose.Page para .NET: Certifique‑se de que a biblioteca Aspose.Page para .NET está instalada. Você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).

- Diretório de Documentos: Crie um diretório onde você armazenará seu arquivo EPS de entrada e os arquivos redimensionados de saída.

Agora que tudo está configurado, vamos prosseguir importando os namespaces necessários e aprofundar o guia passo a passo.

## Importar Namespaces

Em seu projeto .NET, comece importando os namespaces necessários para trabalhar com Aspose.Page. Adicione o código a seguir no início do seu arquivo:

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

## Como Redimensionar EPS em Pontos

Pontos são uma unidade padrão de medida na indústria de impressão. O exemplo abaixo duplica a largura e altura originais.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## Como Redimensionar EPS em Polegadas

Polegadas são frequentemente usadas por designers gráficos ao preparar ativos para impressão.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## Como Redimensionar EPS em Milímetros

Milímetros são comuns em regiões que utilizam o sistema métrico.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## Como Redimensionar EPS Usando Percentuais

O redimensionamento baseado em percentuais permite escalar a imagem em relação ao seu tamanho original.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

Sinta‑se à vontade para integrar esses métodos ao seu projeto e você redimensionará imagens EPS sem esforço. Experimente diferentes unidades para alcançar as dimensões desejadas.

## Problemas Comuns e Soluções
- **Arquivo não encontrado:** Verifique se `dataDir` aponta para a pasta correta e se `input.eps` existe.  
- **Tamanho inesperado:** Lembre‑se de que `Units.Percents` espera valores como 150 para 150 % do tamanho original.  
- **Exceção de licença:** Se aparecer um erro de licenciamento, certifique‑se de que um arquivo de licença válido do Aspose.Page foi carregado antes de criar `PsDocument`.

## Conclusão

Parabéns! Você dominou **como redimensionar EPS** com Aspose.Page para .NET. Esta biblioteca poderosa abre um mundo de possibilidades para manipular gráficos vetoriais. Seja projetando para impressão ou mídia digital, Aspose.Page permite que você alcance resultados precisos e personalizados.

## Perguntas Frequentes

### Q1: Posso redimensionar várias imagens EPS simultaneamente?

A1: Sim, você pode percorrer uma coleção de arquivos EPS, aplicando os métodos de redimensionamento conforme necessário.

### Q2: O Aspose.Page é compatível com outros formatos de imagem?

A2: Aspose.Page foca principalmente nos formatos PostScript e EPS. Para outros formatos de imagem, considere usar Aspose.Imaging.

### Q3: Existem considerações de licenciamento para projetos comerciais?

A3: Sim, assegure‑se de possuir uma licença válida. Visite [aqui](https://purchase.aspose.com/buy) para detalhes sobre licenciamento.

### Q4: Posso testar o Aspose.Page antes de comprar?

A4: Absolutamente! Você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Q5: Onde posso buscar ajuda adicional ou discutir problemas?

A5: Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para conectar‑se com a comunidade e obter assistência.

## Perguntas Frequentes

**Q: Este código funciona com .NET Core 6?**  
A: Sim. A API é compatível com .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ e .NET 6+.

**Q: Como posso preservar o perfil de cor original?**  
A: O método `ResizeEps` não altera os dados de cor; ele apenas modifica a caixa delimitadora.

**Q: É possível redimensionar um EPS sem carregar todo o arquivo na memória?**  
A: Usar um stream como demonstrado mantém o uso de memória baixo; o documento é processado em tempo real.

**Q: Posso encadear múltiplas operações de redimensionamento?**  
A: Absolutamente. Chame `ResizeEps` sequencialmente na mesma instância de `PsDocument`.

**Q: O que acontece com imagens incorporadas dentro do EPS?**  
A: Elas são escaladas proporcionalmente ao conteúdo vetorial, preservando a qualidade.

**Última Atualização:** 2026-03-03  
**Testado Com:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}