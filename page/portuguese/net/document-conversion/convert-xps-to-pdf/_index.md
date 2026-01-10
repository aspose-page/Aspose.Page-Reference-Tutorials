---
date: 2026-01-10
description: Converta XPS para PDF sem esforço no .NET com Aspose.Page. Baixe a biblioteca,
  explore a documentação e obtenha uma avaliação gratuita.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Converter XPS para PDF com Aspose.Page para .NET
url: /pt/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter XPS para PDF com Aspose.Page para .NET

## Introdução

Neste tutorial você aprenderá **como converter XPS para PDF** usando a biblioteca Aspose.Page para .NET. Converter XPS para PDF é uma necessidade comum quando você precisa compartilhar documentos XPS com usuários que possuem apenas leitores de PDF, ou quando deseja incorporar conteúdo XPS em fluxos de trabalho maiores de PDF. Vamos percorrer cada passo, explicar por que cada configuração é importante e mostrar como ajustar a saída — como definir a qualidade JPEG e aplicar compressão de imagem PDF.

## Respostas Rápidas
- **Qual biblioteca é a melhor para conversão de XPS para PDF?** Aspose.Page para .NET
- **Preciso de licença para produção?** Sim, é necessária uma licença comercial; há uma versão de avaliação disponível.
- **Posso controlar a qualidade da imagem?** Absolutamente — use `JpegQualityLevel` e `PdfImageCompression`.
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **É possível converter vários arquivos XPS em um único PDF?** Sim, percorrendo os arquivos e mesclando os resultados.

## Pré‑requisitos

Antes de embarcarmos nesta jornada de conversão, certifique‑se de que você tem os seguintes pré‑requisitos:

- **Aspose.Page para .NET Library** – Garanta que a biblioteca Aspose.Page para .NET esteja instalada em seu ambiente de desenvolvimento. Você pode baixá‑la na [documentação do Aspose.Page](https://reference.aspose.com/page/net/).
- **Ambiente de Desenvolvimento** – Configure um ambiente de desenvolvimento .NET com Visual Studio ou qualquer outra IDE compatível.
- **Documento XPS** – Prepare o documento XPS que você deseja converter para PDF. Pode ser seu arquivo XPS de exemplo armazenado em um diretório designado.

## Importar Namespaces

Antes de mergulhar no código, vamos importar o namespace necessário para tornar as funcionalidades do Aspose.Page para .NET acessíveis em nosso projeto:

```csharp
using Aspose.Page.XPS;
```

## Guia Passo a Passo

### Passo 1: Inicializar Diretório do Documento

Defina a pasta que contém seu arquivo XPS de origem e onde o PDF resultante será salvo.

```csharp
string dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho absoluto ou relativo da pasta que contém seu documento XPS.

### Passo 2: Abrir Streams para Saída PDF e Entrada XPS

Usamos dois streams de arquivo — um para ler o arquivo XPS e outro para escrever o PDF gerado.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Dica profissional:** Certifique‑se de que os caminhos estejam corretos e de que a aplicação tenha permissões de leitura/escrita na pasta de destino.

### Passo 3: Carregar o Documento XPS

Crie uma instância `XpsDocument` a partir do stream XPS. O objeto `XpsLoadOptions` permite especificar preferências de carregamento, mas o padrão funciona na maioria dos cenários.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Passo 4: Configurar Opções de Salvamento PDF

Aqui definimos as preferências de saída do PDF. Observe o uso de **compressão de imagem PDF** (`PdfImageCompression.Jpeg`) e **qualidade JPEG** (`JpegQualityLevel = 100`). Essas configurações afetam diretamente o tamanho do arquivo e a fidelidade visual.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Controla a qualidade das imagens JPEG incorporadas no PDF (maior = melhor qualidade, arquivo maior).
- **`ImageCompression`** – Escolhe o algoritmo de compressão; JPEG é ideal para imagens fotográficas.
- **`TextCompression`** – A compressão Flate reduz o tamanho do PDF sem perder qualidade do texto.
- **`PageNumbers`** – Permite **salvar XPS como PDF** apenas para páginas selecionadas.

### Passo 5: Criar um Dispositivo de Renderização PDF

O `PdfDevice` atua como o alvo de renderização que grava os dados PDF no stream que abrimos anteriormente.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Passo 6: Salvar o Documento em PDF

Finalmente, invoque o método `Save`, passando o dispositivo de renderização e as opções configuradas.

```csharp
document.Save(device, options);
```

Quando o código terminar de executar, `XPStoPDF_out.pdf` aparecerá no diretório especificado, contendo as páginas convertidas com as configurações de compressão e qualidade que você definiu.

## Por que Converter XPS para PDF?

- **Acessibilidade universal** – Visualizadores de PDF estão instalados em praticamente todos os dispositivos, enquanto leitores de XPS são raros.
- **Preservar layout** – O PDF mantém o layout visual exato, fontes e gráficos do XPS original.
- **Processamento adicional** – Uma vez em PDF, você pode mesclar, anotar ou assinar digitalmente o documento usando outras bibliotecas Aspose.

## Casos de Uso Comuns

- **Relatórios corporativos** – Gere relatórios XPS a partir de sistemas legados e converta‑os para PDF para distribuição.
- **Arquivamento** – Armazene documentos como PDF para preservação a longo prazo, ainda podendo criá‑los a partir de fontes XPS.
- **Serviços web** – Ofereça um endpoint de API que aceita uploads de XPS e devolve arquivos PDF on‑the‑fly.

## Solução de Problemas & Dicas

- **Arquivo não encontrado** – Verifique novamente o caminho `dataDir` e assegure‑se de que o nome do arquivo XPS corresponde exatamente.
- **Erros de permissão** – Execute o Visual Studio como Administrador ou conceda permissões de gravação à pasta de saída.
- **PDFs grandes** – Se o PDF resultante for muito grande, diminua o `JpegQualityLevel` ou altere `ImageCompression` para `PdfImageCompression.Zip`.

## Perguntas Frequentes

### Q1: Posso converter vários arquivos XPS em um único PDF usando Aspose.Page para .NET?

A1: Sim, você pode percorrer vários arquivos XPS e seguir os mesmos passos para mesclá‑los em um único PDF.

### Q2: Existem outros formatos de saída suportados pelo Aspose.Page para .NET?

A2: Sim, o Aspose.Page para .NET suporta vários formatos de saída, incluindo TIFF, JPEG, PNG e mais.

### Q3: Como posso personalizar a aparência do documento PDF convertido?

A3: Você pode ajustar os parâmetros do objeto de opções, como compressão de imagem e compressão de texto, para obter a aparência desejada.

### Q4: Há uma versão de avaliação disponível para o Aspose.Page para .NET?

A4: Sim, você pode explorar as capacidades do Aspose.Page para .NET obtendo uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Q5: Onde posso obter suporte da comunidade para o Aspose.Page para .NET?

A5: Visite o [fórum do Aspose.Page](https://forum.aspose.com/c/page/39) para discussões e suporte da comunidade.

## Perguntas Frequentes (AI‑Friendly)

**Q: Como definir a qualidade JPEG ao converter XPS para PDF?**  
A: Use a propriedade `JpegQualityLevel` dentro de `PdfSaveOptions`. Definir 100 fornece qualidade máxima.

**Q: O que significa “compressão de imagem PDF” neste contexto?**  
A: Refere‑se à opção `ImageCompression`, que determina como as imagens são comprimidas dentro do PDF (ex.: JPEG, Zip).

**Q: Posso gerar programaticamente um PDF sem uma fonte XPS?**  
A: Sim, o Aspose.Page também suporta **c# generate pdf** diretamente a partir de comandos de desenho, mas isso está fora do escopo deste tutorial.

**Q: Existe uma forma de converter XPS para PDF sem perder gráficos vetoriais?**  
A: A conversão mantém os dados vetoriais; basta evitar rasterizar imagens mantendo `ImageCompression` definido como JPEG ou Zip conforme necessário.

**Q: A biblioteca suporta .NET Core?**  
A: Absolutamente – Aspose.Page para .NET funciona com .NET Core, .NET 5, .NET 6 e versões posteriores.

---

**Última atualização:** 2026-01-10  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}