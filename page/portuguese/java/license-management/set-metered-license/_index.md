---
date: 2026-09-24
description: Aprenda como usar Aspose.Page para converter EPS para PNG em Java, configurar
  uma metered license e escrever código Java para gerar arquivo PNG de forma eficiente.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Definir Metered License em Java
og_description: Aspose.Page converter EPS para PNG em Java com uma metered license.
  Este guia mostra passo a passo como configurar licenciamento, renderizar EPS e escrever
  código Java para gerar arquivo PNG.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page converter EPS para PNG em Java (metered license)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page converter EPS para PNG em Java (metered license)
url: /pt/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page converter EPS para PNG em Java (licença medida)

## Introdução
Se você precisa **salvar EPS como PNG** em uma aplicação Java mantendo a licença simples, está no lugar certo. Este tutorial orienta você a configurar uma **licença medida** para Aspose.Page, carregar um arquivo EPS (Encapsulated PostScript) e convertê‑lo para uma imagem PNG. Ao final, você entenderá como **renderizar EPS para PNG de forma eficiente** e como **escrever código Java para arquivo PNG** que funciona de maneira confiável em produção.

## Respostas rápidas
- **O que significa “save EPS as PNG”?** Converte um arquivo EPS vetorial em uma imagem PNG raster, preservando transparência e compressão sem perdas.  
- **Por que usar uma licença medida?** Você paga apenas pelas páginas que processa, o que é ideal para cargas de trabalho variáveis.  
- **Preciso de conexão à internet?** Não, as chaves medidas são validadas localmente na JVM.  
- **Qual versão do Java é necessária?** Java 8 ou superior é totalmente suportado.  
- **Quanto tempo leva a configuração?** Aproximadamente 10 minutos para uma implementação básica.

## O que é “save EPS to PNG”?
Salvar EPS como PNG converte um documento Encapsulated PostScript vetorial em uma imagem PNG raster, preservando transparência e oferecendo compressão sem perdas. Essa transformação é útil quando você precisa de gráficos prontos para a web, miniaturas ou pré‑visualizações imprimíveis que podem ser exibidas em qualquer navegador sem a necessidade de um interpretador PostScript.

## Por que renderizar EPS para PNG com Aspose.Page?
Aspose.Page fornece uma API pura Java que rasteriza arquivos EPS com alta fidelidade, suporta mais de 50 formatos de saída e oferece licenciamento medido, de modo que você paga apenas pelo que converte. A biblioteca pode processar documentos com centenas de páginas sem carregar o arquivo inteiro na memória, proporcionando renderização rápida e precisa em qualquer plataforma que suporte a JVM.

## Pré‑requisitos
- Experiência básica em desenvolvimento Java.  
- A biblioteca Aspose.Page baixada da [página de download Aspose.Page Java](https://releases.aspose.com/page/java/).  
- Um par de chaves públicas e privadas medidas da sua conta Aspose.  

## Importar pacotes
As instruções `import` trazem as classes necessárias para o escopo. Mantenha este bloco exatamente como mostrado para que o código compile sem alterações.

As classes `java.io` lidam com fluxos de arquivos, enquanto as classes Aspose.Page gerenciam licenciamento, carregamento de documentos e renderização de imagens.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Como salvar EPS como PNG usando Aspose.Page Java
A seguir está o guia passo a passo que combina licenciamento, carregamento, renderização e gravação do arquivo PNG final.

### Resposta direta
Carregue seu arquivo EPS, aplique uma licença medida, configure `ImageSaveOptions` para PNG, renderize o documento em um `ImageDevice` e, finalmente, grave o array de bytes resultante no disco. Essa sequência completa o fluxo **save EPS as PNG** em apenas algumas linhas de código Java.

### Etapa 1: inicializar documento e formato de imagem
Primeiro, defina as chaves medidas e especifique o formato de saída (PNG). Isso estabelece a base para a conversão.

A classe `MeteredLicense` armazena suas chaves públicas e privadas, enquanto `ImageSaveOptions` indica ao Aspose.Page que produza saída PNG.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Etapa 2: inicializar fluxo de entrada PostScript
Abra o arquivo EPS que deseja converter. O fluxo alimenta o documento ao Aspose.Page.

`FileInputStream` lê o arquivo EPS do disco, permitindo que o construtor `Document` analise os dados PostScript.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Etapa 3: verificar licença do documento
Sempre verifique se a licença medida foi aplicada corretamente antes do processamento.

O método `isLicensed()` retorna `true` somente quando as chaves fornecidas são válidas, evitando o uso acidental de uma biblioteca não licenciada.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Etapa 4: inicializar opções e dispositivo de imagem
Crie o objeto de opções que controla as configurações de conversão e o dispositivo que receberá a imagem renderizada.

`ImageDevice` captura a saída rasterizada na memória, enquanto `ImageSaveOptions` permite ajustar DPI, nível de compressão e profundidade de cor.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Etapa 5: salvar arquivo EPS como imagem
Esta é a chamada principal **save EPS as PNG**. O documento é renderizado no dispositivo de imagem usando as opções que configuramos.

O método `document.save(device, options)` realiza a rasterização em uma única etapa.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Etapa 6: obter e salvar bytes da imagem
Extraia os bytes PNG do dispositivo e grave‑os em um arquivo no disco. Esta etapa demonstra como **write PNG file Java** de forma segura.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` persiste a imagem sem bibliotecas adicionais.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Problemas comuns e soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **Licença não reconhecida** | As chaves estão incorretas ou `setMeteredKey` é chamado após o processamento do documento. | Verifique novamente as strings das chaves públicas/privadas e assegure que `setMeteredKey` seja executado antes de quaisquer chamadas ao Aspose.Page. |
| **Arquivo de saída vazio** | `device.getImagesBytes()` retornou `null` porque o arquivo EPS não pôde ser analisado. | Verifique se o arquivo EPS é válido e se `ImageSaveOptions` especifica um tamanho de canvas diferente de zero. |
| **OutOfMemoryError em EPS grande** | Renderizar arquivos vetoriais grandes consome muita memória heap. | Processar as páginas uma de cada vez ou aumentar o heap da JVM (`-Xmx2g`). |

## Perguntas frequentes

**Q: Como obtenho as chaves públicas e privadas medidas?**  
A: Faça login na sua conta Aspose, navegue até a seção **Metered License** e copie as chaves públicas e privadas geradas.

**Q: A biblioteca Aspose.Page é gratuita?**  
A: Aspose.Page oferece um teste gratuito com funcionalidade completa; o uso em produção requer uma licença paga. Baixe o teste na [página de download de teste Aspose](https://releases.aspose.com/).

**Q: Posso usar Aspose.Page em projetos comerciais?**  
A: Sim, uma licença comercial permite a implantação em ambientes de produção. Adquira uma licença na [página de compra Aspose](https://purchase.aspose.com/buy).

**Q: Onde posso encontrar documentação adicional?**  
A: A referência completa da API está disponível na [referência da API Aspose.Page Java](https://reference.aspose.com/page/java/).

**Q: Como obtenho uma licença temporária para avaliação?**  
A: Licenças temporárias são fornecidas através do portal Aspose na [página de licença temporária Aspose](https://purchase.aspose.com/temporary-license/).

**Q: E se eu precisar converter arquivos EPS multipágina?**  
A: Percorra cada página usando `device.getImagesBytes()` e grave cada array de bytes em um arquivo PNG separado.

**Q: Posso alterar a qualidade ou profundidade de cor do PNG?**  
A: Sim, configure `ImageSaveOptions` (por exemplo, `options.setCompressionLevel(9)`) antes de chamar `document.save(...)`.

---

**Última atualização:** 2026-09-24  
**Testado com:** Aspose.Page 24.12 para Java (mais recente)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como definir licença para Aspose.Page Java API – Gerenciamento de Licença](/page/java/license-management/)
- [Converter PS para PNG com Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Redimensionar EPS usando Aspose.Page – Manipulação de EPS em Java](/page/java/manipulation-eps/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}