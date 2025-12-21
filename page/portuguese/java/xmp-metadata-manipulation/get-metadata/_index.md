---
date: 2025-12-21
description: Aprenda a ler metadados XMP usando Java com Aspose.Page. Este guia passo
  a passo mostra como ler XMP de formato de documento e extrair propriedades principais.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Como ler metadados XMP usando Java – Guia Aspose.Page
url: /pt/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obter Metadados de XMP usando Java

## Como Ler Metadados XMP usando Java

Bem‑vindo ao nosso tutorial passo a passo que mostra **como ler XMP** metadados com Java e a biblioteca Aspose.Page. XMP (Extensible Metadata Platform) é um padrão amplamente adotado para incorporar metadados ricos em documentos. Ao final deste guia, você será capaz de ler XMP de formatos de documento, extrair informações do criador, timestamps, miniaturas e muito mais — capacitando você a criar soluções de análise de documentos mais inteligentes.

## Respostas Rápidas
- **O que significa “como ler xmp”?** Refere‑se à extração de metadados XMP de arquivos programaticamente.  
- **Qual biblioteca é necessária?** Aspose.Page for Java (disponível na página de download da Aspose).  
- **Preciso de licença?** É necessária uma licença temporária ou completa para uso em produção; um teste gratuito está disponível.  
- **Qual versão do Java é suportada?** Java 8 ou superior.  
- **Posso ler XMP de outros formatos?** Sim, Aspose.Page pode lidar com EPS, PDF e vários tipos de imagem que incorporam XMP.

## Pré‑requisitos
Antes de mergulhar no código, certifique‑se de que você tem:

- **Java Development Kit (JDK)** – Java 8+ instalado e configurado na sua máquina.  
- **Aspose.Page for Java** – Baixe a biblioteca no site oficial [here](https://releases.aspose.com/page/java/).  
- Um arquivo EPS que contém metadados XMP (por exemplo, `xmp1.eps`).  

## Importar Pacotes
Em seu projeto Java, importe os pacotes necessários:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Etapa 1: Inicializar Fluxo de Arquivo EPS de Entrada
Comece definindo o caminho para o diretório de documentos e inicializando o fluxo de arquivo EPS de entrada.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Etapa 2: Obter Metadados XMP
Recupere os metadados XMP do arquivo EPS. Se o arquivo não possuir metadados XMP, um novo será gerado com valores dos comentários de metadados PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Etapa 3: Extrair Informação CreatorTool
Verifique e imprima o valor “CreatorTool” dos metadados XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Etapa 4: Extrair Informação CreateDate
Verifique e imprima o valor “CreateDate” dos metadados XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Etapa 5: Recuperar Largura da Miniatura
Se miniaturas existirem, extraia e imprima a largura da primeira miniatura.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Etapa 6: Extrair Informação de Formato
Verifique e imprima o valor “format” dos metadados XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Etapa 7: Obter DocumentID
Verifique e imprima o valor “DocumentID” dos metadados XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Por Que Isso Importa
Ler metadados XMP permite descobrir programaticamente a origem, a data de criação e outros atributos essenciais de um documento sem abri‑lo em um visualizador. Isso é especialmente útil para processamento em lote, sistemas de gerenciamento de conteúdo e pipelines de ativos digitais onde os metadados dirigem a indexação e a pesquisa.

## Armadilhas Comuns & Dicas
- **XMP ausente:** Alguns arquivos EPS podem não conter XMP. A chamada `getXmpMetadata()` sintetizará um conjunto mínimo baseado nos comentários PS existentes, mas você não obterá metadados completos a menos que estejam incorporados.  
- **Arrays de Miniaturas:** A chave `xmp:Thumbnails` pode conter múltiplas entradas. O exemplo extrai apenas a primeira; itere o array se precisar de todas as miniaturas.  
- **Conscientização de Namespace:** As chaves XMP usam namespaces (ex.: `xmp:`, `dc:`). Certifique‑se de referenciar o nome exato da chave; caso contrário `containsKey` retornará false.

## Perguntas Frequentes
### Posso usar Aspose.Page for Java com outras linguagens de programação?
Sim, Aspose.Page suporta múltiplas linguagens, incluindo Java, .NET, e mais. Consulte a [documentation](https://reference.aspose.com/page/java/) para detalhes.

### Existe um teste gratuito disponível para Aspose.Page for Java?
Sim, você pode acessar o teste gratuito [here](https://releases.aspose.com/).

### Onde posso encontrar suporte para Aspose.Page for Java?
Visite o [Aspose.Page forum](https://forum.aspose.com/c/page/39) para suporte da comunidade.

### Como obtenho uma licença temporária para Aspose.Page for Java?
Você pode obter uma licença temporária [here](https://purchase.aspose.com/temporary-license/).

### Existem recursos adicionais para Aspose.Page for Java?
Explore a documentação completa [documentation](https://reference.aspose.com/page/java/) e baixe a biblioteca [here](https://releases.aspose.com/page/java/).

## FAQ Adicional
**Q: Esse método funciona com arquivos PDF que contêm XMP?**  
A: Sim, Aspose.Page pode ler XMP de PDF, EPS e vários formatos de imagem.

**Q: Posso modificar os metadados XMP após lê‑los?**  
A: Absolutamente. O objeto `XmpMetadata` é mutável; você pode adicionar, atualizar ou remover chaves e então salvar o documento.

**Q: Existe uma maneira de extrair todas as imagens de miniatura, não apenas as dimensões?**  
A: Você pode recuperar os dados binários da propriedade `xmpGImg:data` de cada entrada de miniatura e gravá‑los em um arquivo.

## Conclusão
Você agora domina **como ler XMP** metadados usando Java e Aspose.Page. Seguindo estas etapas, pode extrair ferramentas do criador, timestamps, miniaturas, informações de formato e IDs de documento — proporcionando total visibilidade dos metadados incorporados em seus arquivos EPS. Sinta‑se à vontade para experimentar namespaces XMP adicionais e obter dados ainda mais ricos para suas aplicações.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose