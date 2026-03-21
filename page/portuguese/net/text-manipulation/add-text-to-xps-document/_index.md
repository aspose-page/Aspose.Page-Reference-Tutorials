---
date: 2026-03-21
description: Aprenda como criar documentos XPS em .NET e adicionar texto usando Aspose.Page
  para .NET. Guia passo a passo para desenvolvedores .NET.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: Criar documento XPS .NET e adicionar texto com Aspose.Page
url: /pt/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar documento XPS .NET e adicionar texto com Aspose.Page

No desenvolvimento moderno em .NET, a capacidade de **criar documento XPS .NET** programaticamente é uma habilidade valiosa, especialmente quando você precisa gerar relatórios imprimíveis, faturas ou gráficos personalizados. Este tutorial orienta você a usar o Aspose.Page para **aspose.page add text** a um documento XPS, oferecendo controle total sobre layout e estilo — tudo a partir da sua aplicação .NET.

## Respostas rápidas
- **O que este tutorial cobre?** Adicionar texto a um documento XPS recém‑criado usando Aspose.Page para .NET.  
- **Quanto tempo leva?** Cerca de 5‑10 minutos para uma implementação básica.  
- **Quais são os pré‑requisitos?** Ambiente de desenvolvimento .NET e biblioteca Aspose.Page.  
- **É necessária licença?** Sim, uma licença válida do Aspose.Page é necessária para uso em produção.  
- **Funciona em .NET Core / .NET 6+?** Absolutamente – Aspose.Page suporta todas as versões recentes do .NET.

## O que é criar documento xps .net?

Criar um documento XPS em .NET significa gerar um arquivo de layout fixo que preserva a aparência exata do seu conteúdo em diferentes dispositivos e impressoras. XPS (XML Paper Specification) é o padrão aberto da Microsoft para descrição de página, semelhante ao PDF, mas totalmente baseado em XML.

## Por que usar Aspose.Page para adicionar texto?

Aspose.Page oferece uma API de alto nível, orientada a objetos, que abstrai a marcação XPS de baixo nível. Você pode adicionar texto, gráficos e formas sem lidar com XML bruto, tornando o processo de desenvolvimento mais rápido e menos propenso a erros.

## Pré‑requisitos

- Aspose.Page para .NET: Certifique‑se de que a biblioteca Aspose.Page está instalada. Você pode baixá‑la na [documentação do Aspose.Page para .NET](https://reference.aspose.com/page/net/).
- Ambiente de desenvolvimento: Configure seu ambiente de desenvolvimento .NET. Se ainda não fez isso, siga as instruções de instalação fornecidas na [documentação](https://reference.aspose.com/page/net/).
- Diretório de documentos: Crie um diretório onde você armazenará seus documentos. Substitua "Your Document Directory" no trecho de código fornecido pelo caminho real.

Agora que cobrimos o básico, vamos ao código.

## Importar namespaces

Primeiro, importe os namespaces necessários para iniciar o projeto:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: Criar documento XPS .NET

Crie um novo documento XPS que servirá como tela para o nosso texto.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Etapa 2: Criar um brush para o texto

Defina um brush de cor sólida que determina a cor do texto. Aqui usamos preto.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Etapa 3: Adicionar glifos (aspose.page add text)

Glifos são a representação de baixo nível dos caracteres em um documento XPS. Esta chamada adiciona o texto “Hello World!” nas coordenadas especificadas.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Etapa 4: Salvar o documento XPS resultante

Persista o documento no disco para que você possa visualizá‑lo ou imprimi‑lo posteriormente.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Seguindo estas etapas, você criou com sucesso **create XPS document .NET** e adicionou texto personalizado usando Aspose.Page.

## Problemas comuns e soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| **Arquivo não encontrado** ao salvar | `dataDir` aponta para uma pasta inexistente | Certifique‑se de que o diretório exista ou use `Directory.CreateDirectory(dataDir)` antes de salvar. |
| **Texto não visível** | Cor do brush coincide com o fundo | Altere `Color.Black` para outra cor contrastante. |
| **Fonte não suportada** | Fonte não está instalada na máquina | Use uma fonte garantida como presente, ou incorpore a fonte usando os recursos de incorporação de fontes do Aspose.Page. |

## Perguntas frequentes

### Q1: Posso personalizar a fonte e o tamanho do texto adicionado?

R1: Sim, você tem controle total sobre a fonte e o tamanho. Ajuste os parâmetros no método `AddGlyphs` conforme necessário.

### Q2: O Aspose.Page é compatível com .NET Core?

R2: Absolutamente! Aspose.Page suporta .NET Core, garantindo compatibilidade com as tecnologias .NET mais recentes.

### Q3: Existem requisitos de licenciamento para usar o Aspose.Page?

R3: Sim, é necessária uma licença válida. Explore as opções de licenciamento [aqui](https://purchase.aspose.com/buy).

### Q4: Como posso obter suporte ou ajuda?

R4: Visite o [fórum do Aspose.Page](https://forum.aspose.com/c/page/39) para conectar‑se com a comunidade e obter assistência.

### Q5: Há uma versão de avaliação gratuita disponível?

R5: Certamente! Você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

**Perguntas e respostas adicionais**

**P: Posso adicionar vários blocos de texto na mesma página?**  
R: Sim, basta chamar `doc.AddGlyphs` várias vezes com coordenadas diferentes.

**P: O Aspose.Page permite rotação de texto?**  
R: Você pode aplicar uma matriz de transformação ao objeto `XpsGlyphs` para girar ou inclinar o texto.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Última atualização:** 2026-03-21  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

---