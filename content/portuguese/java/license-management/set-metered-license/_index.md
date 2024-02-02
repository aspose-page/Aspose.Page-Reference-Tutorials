---
title: Integração de licença medida sem esforço com Aspose.Page Java
linktitle: Definir licença limitada em Java
second_title: API Java Aspose.Page
description: Explore a integração perfeita do Aspose.Page com Java. Configure licenças limitadas sem esforço e aprimore seus recursos de processamento de documentos.
type: docs
weight: 10
url: /pt/java/license-management/set-metered-license/
---
## Introdução
Bem-vindo ao nosso guia completo sobre como configurar uma licença limitada em Java usando Aspose.Page. Se você deseja aprimorar seus recursos de processamento de documentos e garantir uma integração perfeita com o Aspose.Page, você está no lugar certo. Neste tutorial, orientaremos você no processo, dividindo cada etapa em partes de fácil digestão.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento básico de programação Java.
-  Biblioteca Aspose.Page instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/page/java/).
- Chaves públicas e privadas medidas, que você pode obter por meio de sua conta Aspose.
## Importar pacotes
Vamos começar importando os pacotes necessários para o nosso programa Java. Certifique-se de ter a biblioteca Aspose.Page integrada ao seu projeto.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Etapa 1: inicializar o documento e o formato da imagem
primeiro passo é configurar o documento e definir o formato de imagem desejado.
```java
// definir chaves públicas e privadas medidas
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Acesse a propriedade setMeteredKey e passe chaves públicas e privadas como parâmetros
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Etapa 2: inicializar o fluxo de entrada PostScript
Nesta etapa, inicializamos o fluxo de entrada PostScript para processamento.
```java
// Inicializar fluxo de entrada PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Etapa 3: verifique a licença do documento
Antes de prosseguir, é fundamental verificar se o documento está devidamente licenciado.
```java
// Verifique se o documento está licenciado
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Etapa 4: opções de inicialização e dispositivo de imagem
Agora, vamos inicializar as opções e o dispositivo de imagem com parâmetros padrão.
```java
// Inicialize o objeto de opções com parâmetros padrão.
ImageSaveOptions options = new ImageSaveOptions();
// Inicialize o objeto ImageDevice com parâmetros padrão.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Etapa 5: Salvar arquivo EPS como imagem
Salve o arquivo EPS como uma imagem usando as opções e o dispositivo definidos.
```java
// Salvar arquivo EPS como imagem
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Etapa 6: obter e salvar bytes de imagem
Recupera bytes de imagem e salva-os em um arquivo.
```java
// Obtenha bytes de imagens. Matriz de um byte para uma página. No nosso caso, temos uma página.
byte[][] imagesBytes = device.getImagesBytes();
// Salvar bytes de imagem em arquivo
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Conclusão
Parabéns! Você configurou com sucesso uma licença limitada em Java usando Aspose.Page. Este tutorial forneceu um guia passo a passo para garantir um processo de integração tranquilo.
## Perguntas frequentes
### P: Como obtenho chaves públicas e privadas medidas?
Você pode obter essas chaves através de sua conta Aspose.
### P: A biblioteca Aspose.Page é gratuita?
 Aspose.Page oferece versões de teste gratuitas e pagas. Visita[aqui](https://releases.aspose.com/) para um teste gratuito.
### P: Posso usar Aspose.Page para projetos comerciais?
 Sim, Aspose.Page oferece licenças comerciais. Você pode comprá-los[aqui](https://purchase.aspose.com/buy).
### P: Onde posso encontrar documentação adicional?
 Consulte a documentação[aqui](https://reference.aspose.com/page/java/).
### P: Como posso obter licenças temporárias?
 Licenças temporárias podem ser obtidas[aqui](https://purchase.aspose.com/temporary-license/).