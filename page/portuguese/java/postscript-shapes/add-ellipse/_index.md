---
title: Adicionar elipse em Java PostScript
linktitle: Adicionar elipse em Java PostScript
second_title: API Java Aspose.Page
description: Domine a criação de documentos PostScript impressionantes em Java com Aspose.Page. Aprenda a adicionar reticências passo a passo para obter conteúdo visualmente atraente.
weight: 10
url: /pt/java/postscript-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar elipse em Java PostScript

## Introdução
No mundo dinâmico do desenvolvimento Java, a criação de documentos visualmente atraentes é um requisito comum. Aspose.Page for Java é uma biblioteca poderosa que permite aos desenvolvedores manipular arquivos PostScript sem esforço. Neste tutorial, exploraremos como adicionar reticências a documentos PostScript usando Aspose.Page para Java. Acompanhe para aprimorar suas habilidades de criação de documentos!
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos configurados:
1. Ambiente de desenvolvimento Java: certifique-se de ter um ambiente de desenvolvimento Java funcional instalado em sua máquina.
2.  Biblioteca Aspose.Page para Java: Baixe e inclua a biblioteca Aspose.Page em seu projeto Java. Você pode encontrar a biblioteca[aqui](https://releases.aspose.com/page/java/).
## Importar pacotes
Em seu código Java, importe os pacotes necessários para utilizar a funcionalidade Aspose.Page. Aqui está um exemplo:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Etapa 1: configure seu documento
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie fluxo de saída para documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Crie opções de salvamento com tamanho A4
PsSaveOptions options = new PsSaveOptions();
// Crie um novo documento PS com a página aberta
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Etapa 2: preencher a elipse com cor
```java
// Definir tinta para preencher a elipse
document.setPaint(Color.ORANGE);
// Preencha a primeira elipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## Etapa 3: delinear a elipse com traço
```java
// Definir tinta para traçar a elipse
document.setPaint(Color.RED);
// Definir curso
document.setStroke(new BasicStroke(3));
// Trace (contorne) a segunda elipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## Etapa 4: fechar e salvar o documento
```java
// Fechar página atual
document.closePage();
// Salve o documento
document.save();
```
Agora você adicionou reticências ao seu documento PostScript com sucesso usando Aspose.Page para Java! Experimente diferentes coordenadas e dimensões para personalizar seu visual.
## Conclusão
 Aspose.Page para Java simplifica o processo de criação e manipulação de documentos PostScript. Este tutorial equipou você com o conhecimento necessário para adicionar elipses, fornecendo uma base sólida para visualizações mais complexas. Mergulhe no[documentação](https://reference.aspose.com/page/java/) para obter mais detalhes e recursos.
## Perguntas frequentes
### P: Posso usar Aspose.Page for Java com outras bibliotecas Java?
R: Sim, Aspose.Page for Java foi projetado para integração perfeita com outras bibliotecas Java.
### P: Como posso obter uma licença temporária do Aspose.Page for Java?
 R: Obtenha uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/) para fins de teste.
### P: O Aspose.Page é adequado para projetos comerciais?
 R: Absolutamente! Visita[aqui](https://purchase.aspose.com/buy) para explorar opções de licenciamento para uso comercial.
### P: Onde posso procurar ajuda ou discutir dúvidas relacionadas ao Aspose.Page?
 R: Junte-se à comunidade no[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para discussões e assistência.
### P: Existe algum recurso gratuito para aprender mais sobre Aspose.Page for Java?
 R: Utilize o[teste grátis](https://releases.aspose.com/) e explore exemplos na documentação.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
