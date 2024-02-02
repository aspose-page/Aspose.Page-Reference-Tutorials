---
title: Personalize Java PostScript - Adicionando retângulos com Aspose.Page
linktitle: Adicionar retângulo em Java PostScript
second_title: API Java Aspose.Page
description: Explore o guia passo a passo sobre como adicionar retângulos vibrantes a documentos Java PostScript usando Aspose.Page for Java. Melhore a personalização do seu documento sem esforço!
type: docs
weight: 11
url: /pt/java/postscript-shapes/add-rectangle/
---
## Introdução
Você deseja aprimorar seus documentos Java PostScript com retângulos vibrantes? Não procure mais! Neste guia passo a passo, exploraremos como usar Aspose.Page for Java para adicionar retângulos aos seus documentos PostScript. Aspose.Page é uma biblioteca poderosa que oferece recursos robustos para trabalhar com arquivos PostScript, tornando-a a escolha ideal para desenvolvedores que buscam manipular e personalizar seus documentos.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Compreensão básica de programação Java.
-  Biblioteca Aspose.Page para Java instalada. Caso contrário, baixe-o do[Documentação Aspose.Page para Java](https://reference.aspose.com/page/java/).
- Um ambiente de desenvolvimento Java configurado em sua máquina.
## Importar pacotes
No seu projeto Java, comece importando os pacotes necessários:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Tutorial: Adicionando retângulos em Java PostScript
## Etapa 1: definir tinta para preenchimento do retângulo
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie fluxo de saída para documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Crie opções de salvamento com tamanho A4
PsSaveOptions options = new PsSaveOptions();
// Crie um novo documento PS com a página aberta
PsDocument document = new PsDocument(outPsStream, options, false);
// Definir tinta para preencher o retângulo
document.setPaint(Color.ORANGE);        
// Preencha o primeiro retângulo
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Etapa 2: definir pintura para traçar retângulo
```java
// Definir tinta para traçar retângulo
document.setPaint(Color.RED);
// Definir curso
document.setStroke(new BasicStroke(3));
// Trace (contorne) o segundo retângulo
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Etapa 3: feche a página atual e salve o documento
```java
// Fechar página atual
document.closePage();
// Salve o documento
document.save();
```
Parabéns! Você adicionou retângulos vibrantes ao seu documento Java PostScript usando Aspose.Page.
## Conclusão
Neste tutorial, exploramos o processo de aprimoramento de seus documentos Java PostScript com retângulos usando Aspose.Page para Java. Esta poderosa biblioteca abre um mundo de possibilidades para desenvolvedores que buscam personalizar e manipular seus documentos sem esforço.
Divirta-se experimentando diferentes formas e cores para tornar seus documentos visualmente atraentes!
## perguntas frequentes

### Posso usar Aspose.Page for Java com outras linguagens de programação?
Aspose.Page oferece suporte principalmente a Java, mas bibliotecas semelhantes estão disponíveis para outras linguagens.
### Existe uma versão de teste do Aspose.Page para Java disponível?
 Sim, você pode explorar os recursos do Aspose.Page for Java com o[versão de teste gratuita](https://releases.aspose.com/).
### Onde posso encontrar ajuda e discussões adicionais?
 Visite a[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para se envolver com a comunidade e obter assistência.
### Como posso obter uma licença temporária para Aspose.Page for Java?
 Obtenha uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar uma versão licenciada do Aspose.Page for Java?
 Compre uma versão licenciada[aqui](https://purchase.aspose.com/buy).