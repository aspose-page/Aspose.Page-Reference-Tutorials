---
date: 2026-02-23
description: Aprenda a criar documentos XPS com gradiente diagonal usando Aspose.Page
  para .NET e eleve suas apresentações visuais sem esforço.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Criar gradiente diagonal XPS com Aspose.Page para .NET
url: /pt/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar XPS com Gradiente Diagonal usando Aspose.Page para .NET

## Introdução

Se você precisa **criar XPS com gradiente diagonal** que chamem a atenção, o Aspose.Page para .NET torna isso simples. Neste tutorial você aprenderá como adicionar um gradiente diagonal a um documento XPS, passo a passo, usando a API do Aspose.Page. Ao final, você terá um padrão reutilizável que pode adaptar a qualquer forma ou esquema de cores.

## Respostas Rápidas
- **O que o método da API faz?** Ele cria um pincel de gradiente linear que se estende diagonalmente ao longo de um caminho.  
- **Qual classe representa o documento XPS?** `XpsDocument`.  
- **Preciso de uma licença para executar o exemplo?** Uma versão de avaliação gratuita funciona para desenvolvimento; uma licença é necessária para produção.  
- **Posso mudar a direção do gradiente?** Sim—ajuste os valores de `PointF` de início e fim.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é **criar XPS com gradiente diagonal**?
Um gradiente diagonal é uma transição suave de cores que vai de um canto de uma forma ao canto oposto. No XPS, esse efeito é obtido aplicando um `LinearGradientBrush` à propriedade de preenchimento de um caminho. A biblioteca Aspose.Page abstrai a marcação XPS de baixo nível, permitindo que você se concentre nas cores e na geometria.

## Por que usar Aspose.Page para gradientes diagonais?
- **Renderização de alta fidelidade** – a saída corresponde exatamente à especificação XPS.  
- **Integração total com .NET** – funciona com C#, VB.NET e qualquer linguagem .NET.  
- **Sem dependências externas** – tudo é tratado no processo, sem necessidade de COM ou Office.  
- **Escalável para documentos complexos** – você pode combinar múltiplos gradientes, imagens e texto na mesma página.

## Pré-requisitos

1. **Biblioteca Aspose.Page para .NET** – faça o download [aqui](https://releases.aspose.com/page/net/).  
2. **Ambiente de Desenvolvimento** – Visual Studio, Rider ou qualquer editor que suporte projetos .NET.  

Agora, vamos mergulhar no código.

## Importar Namespaces

Em seu projeto .NET, inclua os namespaces necessários da biblioteca Aspose.Page para acessar as classes e métodos requeridos. Adicione os seguintes namespaces no início do seu código:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Etapa 1: Definir o Diretório do Documento

Comece especificando o caminho para o diretório do seu documento. É aqui que o documento XPS resultante com o gradiente diagonal será salvo.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar um Novo Documento XPS

Inicialize um novo `XpsDocument` usando a biblioteca Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Etapa 3: Definir Cores do Gradiente

Crie uma lista de objetos `XpsGradientStop`, cada um representando uma cor no gradiente diagonal.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Etapa 4: Adicionar um Gradiente Diagonal a um Caminho

Crie um novo caminho com uma geometria definida e aplique o gradiente diagonal a ele. Ajuste a transformação de renderização e as propriedades de preenchimento conforme necessário.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Etapa 5: Salvar o Documento XPS Resultante

Finalmente, salve o documento XPS modificado no diretório especificado.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Você acabou de **criar um XPS com gradiente diagonal** com sucesso. Sinta-se à vontade para experimentar diferentes pontos de cor, strings de geometria ou matrizes de transformação para produzir uma variedade de efeitos visuais.

## Problemas Comuns e Soluções
- **Gradiente não visível** – Verifique se a geometria do caminho está fechada e se os pontos de início/fim do pincel estão dentro dos limites do caminho.  
- **Cores incorretas** – Certifique-se de usar `CreateColor` com os valores ARGB corretos; o método espera valores na faixa 0‑255.  
- **Arquivo não salvo** – Verifique se `dataDir` aponta para uma pasta existente e se a aplicação tem permissões de gravação.

## Perguntas Frequentes

**Q: Posso aplicar múltiplos gradientes a diferentes partes do documento?**  
A: Sim, você pode criar múltiplos caminhos e aplicar gradientes distintos a cada um.

**Q: Existem estilos de gradiente predefinidos disponíveis?**  
A: Aspose.Page permite gradientes personalizados, dando controle total sobre as transições de cor.

**Q: Posso usar Aspose.Page para .NET com outros formatos de documento?**  
A: Aspose.Page foca principalmente na manipulação de documentos XPS.

**Q: Como posso lidar com erros relacionados ao processamento de documentos?**  
A: Consulte a [documentação](https://reference.aspose.com/page/net/) para as melhores práticas de tratamento de erros.

**Q: Existe uma versão de avaliação disponível antes da compra?**  
A: Sim, você pode explorar o [free trial](https://releases.aspose.com/) para experimentar o Aspose.Page para .NET.

**Q: Como altero a direção do gradiente para vertical ou horizontal?**  
A: Modifique os argumentos `PointF` em `CreateLinearGradientBrush` para definir novos pontos de início e fim.

**Q: A biblioteca suporta transparência em gradientes?**  
A: Sim—inclua um valor alfa ao criar cores com `CreateColor`.

## Conclusão

Aspose.Page para .NET simplifica o processo de aprimorar documentos XPS com gradientes diagonais. Este guia conduziu você desde a configuração dos pré-requisitos até a gravação do arquivo final. Continue experimentando diferentes formas e paletas de cores para que seus relatórios, brochuras ou faturas XPS realmente se destaquem.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-02-23  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose