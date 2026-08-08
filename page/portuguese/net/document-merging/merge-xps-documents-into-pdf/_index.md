---
date: 2026-06-20
description: Converta XPS para PDF sem esforço e comprima imagens PDF usando Aspose.Page
  para .NET. Siga nosso guia passo a passo para criar PDFs de alta qualidade.
keywords:
- convert xps to pdf
- compress pdf images
- create pdf from xps
linktitle: Mesclar documentos XPS em PDF
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Effortlessly convert XPS to PDF and compress PDF images using Aspose.Page
    for .NET. Follow our step-by-step guide for high-quality PDF creation.
  headline: Convert XPS to PDF with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can load each XPS document sequentially and render them into
      the same `PdfDevice` instance, adjusting the `PageNumbers` option as needed.
    question: Can I merge multiple XPS files into a single PDF?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: Is a temporary license available for Aspose.Page for .NET?
  - answer: Aspose.Page for .NET does not impose strict limitations on file size,
      but optimal performance is achieved with files under 500 MB; larger files may
      require more memory.
    question: Are there any limitations on file size when using Aspose.Page for document
      conversion?
  - answer: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation.
      Check the documentation for advanced customization options.
    question: Can I customize the output PDF further, such as adding watermarks or
      annotations?
  - answer: Yes, Aspose.Page for .NET is designed to work seamlessly across Windows,
      Linux, and macOS environments.
    question: Does Aspose.Page for .NET support cross‑platform development?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Converter XPS para PDF com Aspose.Page para .NET
url: /pt/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter XPS para PDF com Aspose.Page para .NET

## Introdução

Se você precisa **converter XPS para PDF** rapidamente, mantendo gráficos vetoriais e texto nítidos, o Aspose.Page para .NET fornece uma API pronta‑para‑uso que cuida do trabalho pesado. Neste tutorial, percorreremos todo o fluxo de trabalho — desde o carregamento de um arquivo XPS até a gravação de um PDF de alta qualidade — para que você possa integrar a conversão em qualquer aplicação .NET com confiança.

## Respostas Rápidas
- **Qual biblioteca lida com XPS → PDF?** Aspose.Page for .NET.
- **Quantas linhas de código são necessárias?** Cerca de cinco etapas lógicas (≈ 30 linhas no total).
- **As imagens PDF podem ser comprimidas?** Sim, use `PdfSaveOptions.ImageCompression`.
- **É necessária uma licença para produção?** É necessária uma licença comercial; um teste temporário está disponível.
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Como converter XPS para PDF usando Aspose.Page?

Carregue o arquivo XPS com `new XpsDocument(inputStream)` e chame `PdfDevice.Render` passando uma instância configurada de `PdfSaveOptions` — este único pipeline converte o documento e grava o PDF em um fluxo de saída. Toda a operação é executada na memória, portanto nenhum arquivo temporário é criado, e você pode opcionalmente habilitar a compressão de imagens para reduzir o tamanho final do arquivo.

## O que é Aspose.Page para .NET?

Aspose.Page para .NET é uma biblioteca de processamento de documentos que permite a criação, conversão e renderização de XPS, PDF e outros formatos baseados em página sem exigir o Microsoft Office. Ela fornece APIs para criar, editar e converter documentos baseados em página, suportando tanto gráficos vetoriais quanto raster, e funciona em múltiplas plataformas. Ela expõe uma API de baixo nível que oferece aos desenvolvedores controle granular sobre as opções de renderização.

## Por que usar Aspose.Page para converter XPS para PDF?

Aspose.Page suporta **mais de 30 formatos de saída** e pode processar **arquivos XPS de 500 páginas** em menos de **2 segundos** em um servidor típico, tudo isso preservando os dados vetoriais. A biblioteca também oferece **compressão de imagens** integrada (até 80 % de redução) e **compressão de texto**, ajudando você a criar PDFs leves sem sacrificar a qualidade.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos configurados:

- Aspose.Page para .NET: Certifique‑se de que a biblioteca Aspose.Page está instalada. Você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).
- Arquivos de Documento: Tenha o documento XPS (`input.xps`) pronto no diretório especificado.

## Importar Namespaces

Os namespaces `Aspose.Page.Xps` e `Aspose.Page.Pdf` contêm as classes necessárias para carregar arquivos XPS e salvar PDFs.

```csharp
using Aspose.Page.XPS;
```

Esta etapa garante que você tenha acesso às classes e métodos necessários para a conversão do documento.

## Etapa 1: Inicializar Streams

Crie um `FileStream` para o arquivo XPS de origem e outro `FileStream` para o PDF de destino. Usar declarações `using` garante que os streams sejam descartados corretamente.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Esta etapa envolve a configuração dos streams de entrada e saída para os arquivos XPS e PDF. Certifique‑se de que os caminhos e nomes de arquivos corretos sejam usados.

## Etapa 2: Carregar Documento XPS

`XpsDocument` é uma classe que carrega e representa um arquivo XPS na memória.  
Aqui, carregamos o documento XPS no objeto `XpsDocument`, preparando‑o para processamento adicional.

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

## Etapa 3: Inicializar Opções de Salvamento

`PdfSaveOptions` configura como o PDF é salvo, incluindo compressão e configurações de página.  
Personalize o objeto `PdfSaveOptions` de acordo com suas preferências, especificando parâmetros como compressão de imagem, compressão de texto e números de página.

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

## Etapa 4: Criar Dispositivo de Renderização

`PdfDevice` é o motor de renderização que converte páginas XPS em conteúdo PDF.  
O `PdfDevice` é a ferramenta responsável por renderizar o documento XPS no formato PDF.

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

## Etapa 5: Salvar o Documento

Chame `PdfDevice.Render` com o documento XPS carregado e o stream de saída. O método grava um arquivo PDF totalmente compatível no disco.

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Finalmente, salve o documento usando o dispositivo de renderização e as opções especificadas.

## Armadilhas Comuns e Dicas

- **Propriedade do stream:** Sempre envolva streams em blocos `using` para evitar bloqueios de arquivos.
- **Arquivos grandes:** Para arquivos XPS maiores que 200 MB, considere aumentar o `BufferSize` no `FileStream` para melhorar o desempenho.
- **Qualidade da imagem:** Se precisar de imagens sem perdas, defina `ImageCompression` como `PdfImageCompression.None` em vez de JPEG.

## Perguntas Frequentes

**Q: Posso mesclar vários arquivos XPS em um único PDF?**  
**A:** Sim, você pode carregar cada documento XPS sequencialmente e renderiz‑los na mesma instância de `PdfDevice`, ajustando a opção `PageNumbers` conforme necessário.

**Q: Uma licença temporária está disponível para Aspose.Page para .NET?**  
**A:** Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para fins de teste.

**Q: Existem limitações de tamanho de arquivo ao usar Aspose.Page para conversão de documentos?**  
**A:** Aspose.Page para .NET não impõe limitações rígidas de tamanho de arquivo, mas o desempenho ideal é alcançado com arquivos abaixo de 500 MB; arquivos maiores podem exigir mais memória.

**Q: Posso personalizar ainda mais o PDF de saída, como adicionar marcas d'água ou anotações?**  
**A:** Sim, Aspose.Page para .NET oferece recursos extensivos para manipulação de PDFs. Consulte a documentação para opções avançadas de personalização.

**Q: Aspose.Page para .NET suporta desenvolvimento multiplataforma?**  
**A:** Sim, Aspose.Page para .NET foi projetado para funcionar perfeitamente em ambientes Windows, Linux e macOS.

## FAQ Adicional

**Q: Como comprimir imagens PDF durante a conversão?**  
**A:** Defina `PdfSaveOptions.ImageCompression = PdfImageCompression.Jpeg` e, opcionalmente, ajuste `JpegQuality` para equilibrar tamanho e qualidade.

**Q: Qual a melhor maneira de criar PDFs a partir de XPS em um processo em lote?**  
**A:** Percorra um diretório de arquivos XPS, reutilize uma única instância de `PdfDevice` e chame `Render` para cada documento, a fim de minimizar a sobrecarga.

**Q: A biblioteca suporta PDFs protegidos por senha?**  
**A:** Sim, você pode atribuir uma senha via `PdfSaveOptions.Password` antes de salvar.

**Q: Quais runtimes .NET são oficialmente suportados?**  
**A:** .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6/7 são totalmente suportados.

**Q: Como posso verificar se a conversão preservou os gráficos vetoriais?**  
**A:** Abra o PDF resultante em um visualizador que possa inspecionar tipos de objetos (por exemplo, Adobe Acrobat) e confirme que o texto e as formas permanecem selecionáveis e escaláveis.

## Conclusão

Agora você tem um fluxo de trabalho completo e pronto para produção para **converter XPS para PDF** usando Aspose.Page para .NET. Ao aproveitar o motor de renderização da biblioteca e as opções de salvamento, você também pode **comprimir imagens PDF** e ajustar finamente a saída para atender aos seus requisitos de tamanho e qualidade. Sinta‑se à vontade para explorar recursos adicionais, como marca d'água, criptografia e processamento em lote, para expandir ainda mais esta solução.

---

**Last Updated:** 2026-06-20  
**Tested With:** Aspose.Page 23.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar Documento XPS com Aspose.Page para .NET](/page/net/document-creation/create-xps-document/)
- [Modificar Documento XPS com Aspose.Page para .NET](/page/net/document-creation/modify-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}