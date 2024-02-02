---
title: Alterar valores em XMP usando Java
linktitle: Alterar valores em XMP usando Java
second_title: API Java Aspose.Page
description: Aprimore documentos EPS com Aspose.Page para Java. Modifique facilmente os metadados XMP para obter conteúdo personalizado e profissional. #JavaDesenvolvimento
type: docs
weight: 17
url: /pt/java/xmp-metadata-manipulation/change-values/
---
## Introdução
No domínio do processamento e manipulação de documentos, Aspose.Page for Java se destaca como uma ferramenta poderosa. Este tutorial se aprofunda no processo de alteração de valores XMP (Extensible Metadata Platform) em documentos EPS (Encapsulated PostScript) usando Java com a biblioteca Aspose.Page. Seguindo o guia passo a passo fornecido, você aprenderá como modificar metadados sem esforço, garantindo que seus documentos sejam adaptados às suas necessidades específicas.
## Pré-requisitos
Antes de embarcarmos neste tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Ambiente de desenvolvimento Java: certifique-se de ter um ambiente de desenvolvimento Java funcional em sua máquina.
2.  Biblioteca Aspose.Page para Java: Baixe e instale a biblioteca Aspose.Page para Java. Você pode encontrar o pacote necessário[aqui](https://releases.aspose.com/page/java/).
## Importar pacotes
Comece importando os pacotes necessários para o seu projeto Java. Esses pacotes são vitais para interagir e manipular documentos EPS.
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
Recuperar metadados XMP do documento EPS. Se o arquivo EPS não contiver metadados XMP, um novo será criado com valores de comentários de metadados PS, como %%Creator, %%CreateDate e %%Title.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Inicializar fluxo de arquivo EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, um novo será criado com valores dos comentários de metadados PS
XmpMetadata xmp = document.getXmpMetadata();
```
## Etapa 2: alterar o valor “ModifyDate”
Modifique o valor “ModifyDate” nos metadados XMP para refletir a data desejada.
```java
// Alterar o valor "ModifyDate"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Etapa 3: alterar o valor do "Criador"
Atualize o valor “Criador” nos metadados XMP para especificar o criador do documento.
```java
// Alterar o valor do "criador"
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Etapa 4: alterar o valor do “Título”
Modifique o valor “Título” nos metadados XMP para definir um título apropriado para o documento.
```java
//Alterar o valor do "título"
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Etapa 5: Salvar documento com metadados XMP alterados
Salve o documento com os metadados XMP atualizados em um novo arquivo EPS.
```java
// Inicializar fluxo de arquivo EPS de saída
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Salvar documento com metadados XMP alterados
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Conclusão
Parabéns! Você navegou com sucesso no processo de alteração de valores XMP em documentos EPS usando Aspose.Page para Java. Este tutorial equipou você com o conhecimento para modificar metadados, garantindo que seus documentos estejam perfeitamente alinhados com seus requisitos específicos.
## Perguntas frequentes
### P: Como posso lidar com considerações de fuso horário ao modificar valores XMP?
 Utilizar`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` para garantir consistência nas configurações de fuso horário.
### P: Posso alterar vários valores XMP em uma única operação?
 Sim, usando o`put` método para cada valor desejado, você pode modificar vários valores XMP simultaneamente.
### P: Onde posso encontrar documentação adicional para Aspose.Page for Java?
 Explore a documentação abrangente[aqui](https://reference.aspose.com/page/java/).
### P: Existe uma avaliação gratuita disponível para Aspose.Page for Java?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### P: Como posso obter uma licença temporária para Aspose.Page for Java?
 Obtenha uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).