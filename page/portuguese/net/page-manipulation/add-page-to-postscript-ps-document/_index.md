---
date: 2026-03-03
description: Aprenda como definir tamanho de página personalizado e adicionar uma
  segunda página PS a um documento PostScript usando o Aspose.Page para .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Definir tamanho de página personalizado em documento PS com Aspose.Page
url: /pt/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Page to PostScript (PS) Document with Aspose.Page

## Introdução

No desenvolvimento .NET, poder **definir tamanho de página personalizado** e **adicionar uma segunda página PS** a um documento PostScript (PS) oferece controle detalhado sobre o layout de impressões, relatórios ou gráficos gerados. Aspose.Page para .NET torna essa tarefa simples com uma API limpa e orientada a objetos. Neste tutorial você aprenderá como criar um arquivo PS de múltiplas páginas, definir um tamanho personalizado para cada página e salvar o resultado — tudo com apenas algumas linhas de código C#.

## Respostas Rápidas
- **Posso definir um tamanho de página personalizado?** Sim – basta passar a largura e a altura ao abrir uma página.  
- **Como adiciono uma segunda página PS?** Chame `document.OpenPage(width, height)` uma segunda vez.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Preciso de uma licença?** Uma licença temporária funciona para testes; uma licença completa é necessária para produção.  
- **Onde posso baixar o Aspose.Page?** Na página oficial de download vinculada abaixo.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos configurados:

- Conhecimento prático de desenvolvimento .NET.  
- Visual Studio instalado em sua máquina.  
- Biblioteca Aspose.Page para .NET, que pode ser baixada [aqui](https://releases.aspose.com/page/net/).  
- Seu diretório de documentos preferido para testes.

## Importar Namespaces

Certifique‑se de incluir os namespaces necessários em seu projeto para acessar as funcionalidades fornecidas pelo Aspose.Page. No exemplo fornecido, os namespaces são incluídos implicitamente, mas é essencial verificar novamente e fazer ajustes conforme a estrutura do seu projeto.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Etapa 1: Configurar Seu Projeto

Crie um novo projeto .NET no Visual Studio e configure as definições necessárias. Certifique‑se de referenciar a biblioteca Aspose.Page em seu projeto.

## Definir Tamanho de Página Personalizado e Adicionar Segunda Página PS

Esta seção demonstra exatamente como **definir tamanho de página personalizado** para cada página e como **adicionar uma segunda página ps** ao mesmo documento.

### Etapa 2: Inicializar o Documento

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Etapa 3: Adicionar a Primeira Página (tamanho padrão)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Etapa 4: Adicionar a Segunda Página com um Tamanho Diferente (Personalizado)

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Etapa 5: Salvar o Documento

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Siga estas etapas meticulosamente, e você conseguirá **definir tamanho de página personalizado** e adicionar uma **segunda página PS** a um documento PostScript usando Aspose.Page para .NET.

## Por Que Isso Importa

- **Layout Preciso** – Dimensões de página personalizadas permitem corresponder às especificações da impressora ou criar formatos de brochura exclusivos.  
- **Múltiplas Páginas** – Adicionar uma segunda página (ou mais) possibilita relatórios de várias páginas sem ferramentas externas de mesclagem.  
- **Cross‑Platform** – O arquivo PS gerado pode ser renderizado em qualquer dispositivo compatível com PostScript ou convertido para PDF posteriormente.

## Problemas Comuns & Solução de Problemas

- **Caminho Incorreto** – Certifique‑se de que `dataDir` termina com um separador de caminho ou use `Path.Combine`.  
- **Problemas de Licença** – Sem uma licença válida, a biblioteca pode adicionar marca d'água ou limitar a contagem de páginas.  
- **Confusão de Unidades** – Largura e altura são medidas em pontos (1 ponto = 1/72 polegada). Ajuste conforme necessário.

## Perguntas Frequentes

**Q1: O Aspose.Page é compatível com diferentes formatos de documento?**  
A1: O Aspose.Page foca principalmente na manipulação de documentos PostScript. Para outros formatos, você pode explorar as bibliotecas Aspose específicas para cada necessidade.

**Q2: Posso personalizar o tamanho da página no Aspose.Page?**  
A2: Absolutamente! Conforme demonstrado no tutorial, você pode especificar tamanhos diferentes para cada página de acordo com seus requisitos.

**Q3: Onde posso encontrar mais exemplos e documentação?**  
A3: Visite a [documentação](https://reference.aspose.com/page/net/) para informações abrangentes e uma variedade de exemplos.

**Q4: Como obtenho uma licença temporária para o Aspose.Page?**  
A4: Acesse [este link](https://purchase.aspose.com/temporary-license/) para adquirir uma licença temporária para fins de teste.

**Q5: Onde posso buscar suporte da comunidade ou fazer perguntas?**  
A5: Participe do [fórum da comunidade Aspose.Page](https://forum.aspose.com/c/page/39) para conectar‑se com outros desenvolvedores, compartilhar experiências e buscar assistência.

---

**Última Atualização:** 2026-03-03  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}