---
date: 2025-11-29
description: Aprenda como salvar XPS como PDF em Java com Aspose.Page Java. Siga nosso
  guia passo a passo para conversão eficiente de XPS para PDF e configurações de compressão
  de PDF.
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Converter XPS para PDF em Java usando Aspose.Page Java
url: /pt/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter XPS para PDF em Java usando Aspose.Page Java

## Introdução
Neste tutorial, você aprenderá **como converter XPS para PDF em Java usando Aspose.Page Java**, uma biblioteca robusta projetada para conversão de documentos Java. Seja para processar faturas em lote, gerar relatórios imprimíveis ou simplesmente migrar arquivos XPS legados, o Aspose.Page Java torna o trabalho rápido, confiável e totalmente configurável.

## Respostas rápidas
- **Qual biblioteca lida com a conversão de XPS para PDF?** Aspose.Page Java  
- **Quanto tempo leva uma conversão básica?** Normalmente menos de um segundo para um arquivo XPS de uma única página.  
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para avaliação; uma licença é necessária para produção.  
- **Posso controlar a compressão do PDF?** Sim – use `PdfSaveOptions` para definir compressão de imagens e texto.  
- **Qual versão do Java é necessária?** Java 8 ou posterior (JDK 11+ recomendado).

## O que é Aspose.Page Java?
Aspose.Page Java é uma **API de alto desempenho** que permite que desenvolvedores criem, editem e convertam documentos XPS programaticamente. Ela suporta a renderização de XPS para PDF, PNG, JPEG e outros formatos, oferecendo controle detalhado sobre as configurações de saída, como **definir compressão PDF**.

## Por que usar Aspose.Page Java para conversão de XPS‑para‑PDF?
- **Renderização sem dependências** – sem bibliotecas nativas ou ferramentas externas.  
- **Preservação precisa do layout** – a saída PDF reflete a aparência original do XPS.  
- **Controle total sobre a saída PDF** – você pode ajustar a qualidade da imagem, escolher algoritmos de compressão e selecionar páginas específicas para renderizar.  
- **Multiplataforma** – funciona no Windows, Linux e macOS com qualquer JDK padrão.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK) 8+** – o JDK mais recente é recomendado para desempenho e segurança.  
2. **Biblioteca Aspose.Page for Java** – faça o download do JAR na [documentação oficial do Aspose.Page Java](https://reference.aspose.com/page/java/).  
3. Uma **IDE** (IntelliJ IDEA, Eclipse, VS Code) ou um editor de texto simples mais ferramentas de compilação por linha de comando (Maven/Gradle).  

## Importar Pacotes
Adicione as importações necessárias à sua classe Java para trabalhar com documentos XPS e saída PDF.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Guia passo a passo

### Etapa 1: Definir o caminho do diretório do documento
Defina a pasta que contém seu arquivo XPS de origem e onde o PDF será salvo.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Etapa 2: Inicializar o fluxo de saída PDF
Crie um `FileOutputStream` que aponta para o arquivo PDF de destino.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Dica profissional:** Use `try‑with‑resources` para fechar automaticamente o fluxo e evitar vazamentos de recursos.

### Etapa 3: Carregar o documento XPS
Instancie um objeto `XpsDocument` carregando o arquivo XPS de origem.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Etapa 4: Inicializar as opções de salvamento PDF (Definir compressão PDF)
Configure como o PDF deve ser comprimido. Esta etapa permite que você **defina compressão PDF** para imagens e texto, reduzindo o tamanho do arquivo sem sacrificar a qualidade.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Por que isso importa:** Ajustar a qualidade JPEG e os tipos de compressão pode reduzir um PDF de 10 MB para menos de 2 MB, mantendo a fidelidade visual necessária.

### Etapa 5: Criar dispositivo de renderização para o formato PDF
O `PdfDevice` envia as páginas renderizadas para o fluxo de saída PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Etapa 6: Salvar o documento
Finalmente, renderize o conteúdo XPS para PDF usando as opções configuradas.

```java
document.save(device, options);
```

> **Resultado:** Após a execução, `XPStoPDF.pdf` aparecerá na pasta `dataDir`, contendo as páginas convertidas com as configurações de compressão especificadas.

## Problemas comuns e soluções

| Problema | Causa | Solução |
|----------|-------|----------|
| **`FileNotFoundException`** | Caminho `dataDir` incorreto | Verifique se o diretório existe e se a aplicação tem permissões de leitura/escrita. |
| **Páginas PDF em branco** | Inicialização `PdfDevice` ausente | Certifique-se de que `PdfDevice` seja criado com o mesmo `FileOutputStream` usado para a saída. |
| **Tamanho grande do PDF** | Compressão padrão está baixa | Aumente `setJpegQualityLevel` ou troque para `PdfImageCompression.Jpeg` com um nível de qualidade mais baixo. |
| **Apenas algumas páginas aparecem** | Filtro `setPageNumbers` exclui páginas | Ajuste o array para incluir todos os números de página necessários ou remova a chamada para exportar todas as páginas. |

## Perguntas Frequentes

**Q:** *O Aspose.Page Java é compatível com diferentes versões do Java?*  
**A:** Sim, o Aspose.Page Java suporta Java 8 até Java 21, incluindo distribuições Oracle e OpenJDK.

**Q:** *Posso personalizar as configurações de compressão para o PDF convertido?*  
**A:** Absolutamente. Use `PdfSaveOptions` para definir a qualidade JPEG, o tipo de compressão de imagem e a compressão de texto conforme mostrado na Etapa 4.

**Q:** *Onde posso encontrar suporte adicional ou discussões da comunidade?*  
**A:** Visite o [Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para ajuda da comunidade, exemplos de código e dicas de solução de problemas.

**Q:** *Existe uma versão de teste gratuita disponível para o Aspose.Page?*  
**A:** Sim, você pode baixar uma versão de teste totalmente funcional na [página de download da Aspose](https://releases.aspose.com/).

**Q:** *Como posso obter uma licença temporária para o Aspose.Page?*  
**A:** Uma licença temporária pode ser solicitada [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão
Ao aproveitar o **Aspose.Page Java**, você pode facilmente **salvar XPS como PDF** e controlar cada aspecto da saída, desde a seleção de páginas até a compressão. Este tutorial cobriu tudo o que você precisa para integrar a conversão de XPS‑para‑PDF em suas aplicações Java, seja construindo uma ferramenta pontual ou um pipeline de processamento de documentos em larga escala.

---

**Última atualização:** 2025-11-29  
**Testado com:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}