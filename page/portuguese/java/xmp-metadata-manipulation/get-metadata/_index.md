---
date: 2026-05-25
description: Aprenda como ler XMP usando Aspose.Page com Java. Este guia passo a passo
  mostra como extrair metadados XMP, informações do criador, carimbos de data/hora,
  miniaturas e muito mais.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Como ler metadados XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Ler XMP usando Aspose.Page – Guia Java
url: /pt/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obter Metadados de XMP usando Java

## Como ler XMP usando Aspose.Page (Java)?

Carregue o arquivo EPS com `new Document("file.eps")` — a classe `Document` representa um arquivo carregado. Chame `getXmpMetadata()`, que extrai o pacote XMP, e então consulte o objeto `XmpMetadata` retornado — uma interface semelhante a um mapa para propriedades XMP — para obter as chaves que você precisa. Isso é tudo o que é necessário para ler XMP usando Aspose.Page. A API abstrai o parsing de baixo nível, então você obtém um mapa pronto para uso das propriedades em apenas duas linhas de código.

Bem‑vindo ao nosso tutorial passo a passo que mostra **como ler metadados XMP** com Java e a biblioteca Aspose.Page. XMP (Extensible Metadata Platform) é um padrão amplamente adotado para incorporar metadados ricos dentro de documentos. Ao final deste guia, você será capaz de ler XMP de formatos de documento, extrair informações do criador, timestamps, miniaturas e muito mais — capacitando você a criar soluções de análise de documentos mais inteligentes.

## Respostas Rápidas
- **O que significa “read XMP”?** Significa extrair programaticamente o pacote XMP que armazena metadados dentro de um arquivo.  
- **Qual biblioteca é necessária?** Aspose.Page for Java (download da página oficial [aqui](https://releases.aspose.com/page/java/)).  
- **Preciso de licença?** Uma licença temporária ou completa é necessária para produção; um teste gratuito funciona para avaliação.  
- **Qual versão do Java é suportada?** Java 8 ou superior.  
- **Posso ler XMP de outros formatos?** Sim — Aspose.Page extrai XMP de EPS, PDF, JPEG, PNG e mais de 20 outros formatos.

## Pré-requisitos
Antes de mergulhar no código, certifique‑se de que você tem:

- **Java Development Kit (JDK)** – Java 8+ instalado e configurado na sua máquina.  
- **Aspose.Page for Java** – Baixe a biblioteca do site oficial [aqui](https://releases.aspose.com/page/java/).  
- Um arquivo EPS que contenha metadados XMP (por exemplo, `xmp1.eps`).  

## Importar Pacotes
A classe `XmpMetadata` está no namespace `com.aspose.page.xmp`, enquanto a classe `Document` está em `com.aspose.page`. Importe ambas para que você possa trabalhar com o arquivo EPS e seus metadados.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Etapa 1: Inicializar Fluxo de Arquivo EPS de Entrada
Comece definindo o caminho para o diretório do seu documento e inicializando o fluxo de arquivo EPS de entrada.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Etapa 2: Obter Metadados XMP
`XmpMetadata` é o objeto da Aspose.Page que contém o pacote XMP extraído de um documento. Recupere‑lo com `document.getXmpMetadata()`. Se o arquivo não possuir XMP, a API sintetiza um pacote mínimo a partir dos comentários PostScript existentes.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Etapa 3: Extrair Informação CreatorTool
A chave `CreatorTool` está no namespace `xmp` e registra a aplicação que gerou o arquivo. Verifique sua presença e imprima o valor.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Etapa 4: Extrair Informação CreateDate
`CreateDate` armazena o timestamp de quando o documento foi originalmente criado. Use o mesmo padrão `containsKey`/`get` para lê‑lo.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Etapa 5: Recuperar Largura da Miniatura
Se miniaturas existirem, o array `xmp:Thumbnails` contém uma ou mais entradas. Cada entrada possui `width`, `height` e dados binários. O exemplo extrai a largura da primeira miniatura.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Etapa 6: Extrair Informação de Formato
A chave `format` indica o formato original do arquivo (por exemplo, “application/postscript”). Isso é útil quando você precisa registrar ou validar tipos de origem.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Etapa 7: Obter DocumentID
`DocumentID` é um identificador único atribuído pela aplicação criadora. Pode ser usado para desduplicação em grandes bibliotecas de ativos.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Por Que Isso Importa
Aspose.Page pode ler XMP de **mais de 20** formatos de arquivo e processa documentos de até **500 MB** sem carregar o arquivo inteiro na memória, proporcionando acesso rápido e de baixo custo a metadados essenciais. Essa capacidade é crítica para pipelines de processamento em lote, sistemas de gerenciamento de ativos digitais e qualquer solução que dependa de atributos de documentos pesquisáveis e legíveis por máquina.

## Armadilhas Comuns & Dicas
- **XMP ausente:** Alguns arquivos EPS podem não conter XMP. A chamada `getXmpMetadata()` sintetizará um conjunto mínimo baseado nos comentários PS existentes, mas você não obterá metadados completos a menos que estejam incorporados.  
- **Arrays de Miniaturas:** A chave `xmp:Thumbnails` pode conter várias entradas. O exemplo extrai apenas a primeira; itere o array se precisar de todas as miniaturas.  
- **Consciência de Namespace:** As chaves XMP usam namespaces (por exemplo, `xmp:`, `dc:`). Certifique‑se de referenciar o nome exato da chave; caso contrário `containsKey` retornará false.  

## Perguntas Frequentes
### Posso usar Aspose.Page para Java com outras linguagens de programação?
Sim, Aspose.Page suporta Java, .NET e várias outras linguagens. Veja a lista completa na [documentação](https://reference.aspose.com/page/java/).

### Existe um teste gratuito disponível para Aspose.Page para Java?
Sim, você pode acessar o teste gratuito [aqui](https://releases.aspose.com/).

### Onde posso encontrar suporte para Aspose.Page para Java?
Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para ajuda da comunidade e suporte oficial.

### Como obtenho uma licença temporária para Aspose.Page para Java?
Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Existem recursos adicionais para Aspose.Page para Java?
Explore a [documentação](https://reference.aspose.com/page/java/) completa e baixe a biblioteca [aqui](https://releases.aspose.com/page/java/).

## FAQ Adicional
**Q: Essa abordagem funciona com arquivos PDF que contêm XMP?**  
A: Sim, Aspose.Page pode ler XMP de PDF, EPS e vários formatos de imagem.

**Q: Posso modificar os metadados XMP após lê‑los?**  
A: Absolutamente. O objeto `XmpMetadata` é mutável; você pode adicionar, atualizar ou remover chaves e então salvar o documento.

**Q: Existe uma maneira de extrair todas as imagens de miniatura, não apenas as dimensões?**  
A: Você pode recuperar os dados binários da propriedade `xmpGImg:data` de cada entrada de miniatura e gravá‑los em um arquivo.

## Conclusão
Agora você dominou **como ler metadados XMP** usando Java e Aspose.Page. Seguindo estas etapas, você pode extrair ferramentas de criação, timestamps, miniaturas, informações de formato e IDs de documento — proporcionando total compreensão dos metadados incorporados em seus arquivos EPS. Sinta‑se à vontade para experimentar namespaces XMP adicionais para obter dados ainda mais ricos para suas aplicações.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Tutoriais Relacionados

- [Tutorial Aspose Page Java – Adicionar Metadados XMP a Arquivos EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Tutorial aspose.page xmp – Adicionar Namespace em XMP usando Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Tutorial aspose page xmp – Alterar Valor Nomeado em XMP usando Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}