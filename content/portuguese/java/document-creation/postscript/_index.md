---
title: Crie documento em Java com PostScript
linktitle: Crie documento em Java com PostScript
second_title: API Java Aspose.Page
description: Crie facilmente documentos PostScript em Java usando Aspose.Page. Personalize o tamanho da página, margens e fontes. Experimente o teste gratuito agora!
type: docs
weight: 10
url: /pt/java/document-creation/postscript/
---
## Introdução
No domínio do desenvolvimento Java, criar e gerenciar documentos é um aspecto crucial. Com o advento do Aspose.Page for Java, o processo torna-se não apenas eficiente, mas também flexível. Este tutorial tem como objetivo guiá-lo nas etapas de criação de um documento em Java com PostScript usando Aspose.Page, garantindo que você aproveite todo o poder desta ferramenta.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
- Conhecimento prático de programação Java.
-  Aspose.Page para Java instalado. Você pode baixá-lo[aqui](https://releases.aspose.com/page/java/).
- Fontes necessárias armazenadas em uma pasta designada. Por exemplo, crie um diretório 'necessary_fonts' em seu diretório de documentos.
## Importar pacotes
Em seu projeto Java, importe os pacotes Aspose.Page necessários:
```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
Agora, vamos dividir o exemplo em várias etapas para uma compreensão perfeita.
## Etapa 1: definir diretório de documentos
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
```
Substitua “Seu diretório de documentos” pelo caminho real onde você deseja salvar seus documentos.
## Etapa 2: definir a pasta de fontes
```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```
Certifique-se de ter as fontes necessárias armazenadas nesta pasta.
## Etapa 3: Criar fluxo de saída para documento PostScript
```java
// Crie fluxo de saída para documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```
Esta etapa estabelece o fluxo de saída para o documento PostScript, definindo o nome do arquivo adequadamente.
## Etapa 4: crie opções de salvamento com tamanho A4
```java
// Crie opções de salvamento com tamanho A4
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```
Personalize as opções de salvamento com base nos requisitos do seu documento, especificando o tamanho e a orientação da página.
## Etapa 5: definir margens de página e pastas de fontes adicionais
```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```
Ajuste as margens da página e inclua pastas de fontes adicionais se as fontes estiverem armazenadas fora das pastas do sistema.
## Etapa 6: crie um documento PS de várias páginas ou de página única
```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```
Determine se o documento PostScript resultante terá várias páginas ou uma página e crie o documento de acordo.
## Etapa 7: feche a página atual e salve o documento
```java
document.closePage();
document.save();
```
Conclua o processo de criação do documento fechando a página atual e salvando o documento.
Este guia passo a passo garante que você possa criar facilmente um documento em Java com PostScript usando Aspose.Page, liberando o potencial desta ferramenta poderosa.
## Conclusão
Dominar a criação de documentos em Java torna-se fácil com Aspose.Page. Este tutorial fornece um guia abrangente para navegar pelo processo, permitindo que você aproveite todos os recursos desta biblioteca.
## Perguntas frequentes
### Posso usar fontes personalizadas em meu documento PostScript?
Sim você pode. Certifique-se de definir a pasta de fontes adicionais nas opções de salvamento.
### Existe uma versão de teste disponível para Aspose.Page for Java?
 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).
### Como posso acessar a documentação do Aspose.Page for Java?
 Consulte a documentação[aqui](https://reference.aspose.com/page/java/).
### Onde posso comprar uma licença para Aspose.Page for Java?
 Você pode comprar uma licença[aqui](https://purchase.aspose.com/buy).
### Existe um fórum para discussões do Aspose.Page?
 Sim, você pode participar da comunidade[fórum](https://forum.aspose.com/c/page/39) para discussões e apoio.