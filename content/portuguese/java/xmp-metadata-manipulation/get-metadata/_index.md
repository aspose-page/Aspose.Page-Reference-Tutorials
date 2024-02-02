---
title: Obtenha metadados do XMP usando Java
linktitle: Obtenha metadados do XMP usando Java
second_title: API Java Aspose.Page
description: Desbloqueie o poder do Aspose.Page for Java para extrair metadados XMP sem esforço. Eleve a análise de documentos com nosso guia passo a passo!
type: docs
weight: 18
url: /pt/java/xmp-metadata-manipulation/get-metadata/
---
## Introdução
Bem-vindo ao nosso guia passo a passo sobre a utilização do Aspose.Page for Java para extrair metadados de arquivos XMP. XMP (Extensible Metadata Platform) fornece uma maneira padronizada de armazenar metadados em arquivos. Este tutorial se concentra na recuperação de informações essenciais do XMP usando Java, oferecendo insights sobre detalhes do documento.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
- Java Development Kit (JDK): Certifique-se de ter o Java instalado em sua máquina.
-  Aspose.Page para Java: Baixe e instale a biblioteca Aspose.Page, que você pode encontrar[aqui](https://releases.aspose.com/page/java/).
## Importar pacotes
No seu projeto Java, importe os pacotes necessários:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Etapa 1: inicializar o fluxo de arquivos EPS de entrada
Comece definindo o caminho para o diretório do documento e inicializando o fluxo de arquivos EPS de entrada.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Etapa 2: Obtenha metadados XMP
Recuperar metadados XMP do arquivo EPS. Se o arquivo não tiver metadados XMP, um novo será gerado com valores dos comentários dos metadados PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Etapa 3: extrair informações do CreatorTool
Verifique e imprima o valor "CreatorTool" dos metadados XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Etapa 4: extrair informações do CreateDate
Verifique e imprima o valor “CreateDate” dos metadados XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Etapa 5: recuperar a largura da miniatura
Se existirem miniaturas, extraia e imprima a largura da primeira miniatura.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Etapa 6: extrair informações de formato
Verifique e imprima o valor “formato” dos metadados XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Etapa 7: obter o DocumentID
Verifique e imprima o valor "DocumentID" dos metadados XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Conclusão
Parabéns! Você aprendeu com sucesso como extrair metadados XMP usando Aspose.Page para Java. Este guia fornece uma visão geral abrangente do processo, garantindo que você possa recuperar com eficácia informações essenciais de seus documentos.
## perguntas frequentes
### Posso usar Aspose.Page for Java com outras linguagens de programação?
 Sim, Aspose.Page oferece suporte a vários idiomas, incluindo Java, .NET e muito mais. Verifica a[documentação](https://reference.aspose.com/page/java/) para detalhes.
### Há uma avaliação gratuita disponível para Aspose.Page for Java?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte para Aspose.Page para Java?
 Visite a[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio comunitário.
### Como obtenho uma licença temporária para Aspose.Page for Java?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Existem recursos adicionais para Aspose.Page for Java?
 Explore o completo[documentação](https://reference.aspose.com/page/java/) e baixe a biblioteca[aqui](https://releases.aspose.com/page/java/).