---
title: Adicione propriedades simples em XMP usando Java
linktitle: Adicione propriedades simples em XMP usando Java
second_title: API Java Aspose.Page
description: Desbloqueie o potencial do Aspose.Page para Java com nosso guia sobre como adicionar propriedades a metadados XMP em arquivos EPS. Eleve o processamento de documentos sem esforço!
weight: 14
url: /pt/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicione propriedades simples em XMP usando Java

## Introdução
No cenário em constante evolução do processamento de documentos, o gerenciamento eficiente de metadados é crucial. Aspose.Page for Java capacita os desenvolvedores a manipular dados da Extensible Metadata Platform (XMP) perfeitamente. Neste tutorial, exploraremos o processo de adição de propriedades simples ao XMP usando Java, fornecendo um guia passo a passo abrangente.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento básico de programação Java.
-  Biblioteca Aspose.Page para Java instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/page/java/).
- Um arquivo EPS de amostra contendo metadados. Se você não tiver um, sinta-se à vontade para usar o arquivo “xmp3.eps” fornecido.
## Importar pacotes
Certifique-se de importar os pacotes necessários para iniciar seu projeto:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Etapa 1: Obtenha metadados XMP
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Inicializar fluxo de arquivo EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, obteremos um novo preenchido com valores de comentários de metadados PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Etapa 2: adicionar propriedade de data
```java
// Adicionar valor da propriedade de data "xmp:Date1"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Etapa 3: adicionar propriedade inteira
```java
// Adicione o valor da propriedade inteira "xmp:Intg1"
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Etapa 4: adicionar propriedade dupla
```java
// Adicione o valor da propriedade dupla "xmp:Double1"
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Etapa 5: adicionar propriedade de string
```java
// Adicionar valor da propriedade de string "xmp:String1"
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Etapa 6: Salvar documento
```java
// Inicializar fluxo de arquivo EPS de saída
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Salvar documento com metadados XMP alterados
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Etapa 7: fechar fluxos
```java
// Fechar fluxo EPS de entrada
psStream.close();
```
## Conclusão
Aspose.Page for Java simplifica o processo de manipulação de metadados XMP em arquivos EPS. Seguindo este guia passo a passo, você pode adicionar propriedades simples sem esforço para aprimorar os metadados do seu documento.
## perguntas frequentes
### Posso usar Aspose.Page for Java com outras linguagens de programação?
Aspose.Page oferece suporte principalmente a Java, mas existem versões disponíveis para outras linguagens como .NET.
### Há uma avaliação gratuita disponível para Aspose.Page for Java?
 Sim, você pode explorar os recursos do Aspose.Page obtendo uma avaliação gratuita[aqui](https://releases.aspose.com/).
### Onde posso encontrar documentação detalhada para Aspose.Page for Java?
 A documentação está disponível[aqui](https://reference.aspose.com/page/java/).
### Como posso obter uma licença temporária para Aspose.Page for Java?
 Uma licença temporária pode ser adquirida[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar Aspose.Page para Java?
 Você pode adquirir o produto[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
