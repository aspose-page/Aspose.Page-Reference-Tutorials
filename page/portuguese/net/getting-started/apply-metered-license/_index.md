---
date: 2026-01-28
description: Aprenda como converter EPS para PNG usando Aspose.Page para .NET e aplicar
  uma licença por consumo para um processamento de documentos sem interrupções.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Converter EPS para PNG e Aplicar Licença Medida com Aspose.Page para .NET
url: /pt/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter EPS para PNG e Aplicar Licença Metered com Aspose.Page para .NET

## Introdução

Desbloqueie todo o potencial do Aspose.Page para .NET **convertendo EPS para PNG** e aplicando uma licença metered. Este tutorial orienta você passo a passo — desde o carregamento de um arquivo EPS até a gravação como imagem PNG — para que possa processar documentos de forma eficiente e sem marcas d'água de avaliação.

## Respostas Rápidas
- **O que este tutorial cobre?** Conversão de arquivos EPS para imagens PNG e aplicação de uma licença metered com Aspose.Page para .NET.  
- **Preciso de uma licença?** Sim, uma licença metered é necessária para uso em produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo leva a implementação?** Aproximadamente 10–15 minutos para uma conversão básica.  
- **Posso executar isso no Linux/macOS?** Absolutamente — o Aspose.Page é multiplataforma.

## O que significa “converter EPS para PNG”?
Converter EPS para PNG significa rasterizar um arquivo Encapsulated PostScript (EPS) baseado em vetor em uma imagem bitmap PNG. Isso é útil quando você precisa exibir ou incorporar gráficos em páginas web, relatórios ou componentes de UI que não suportam EPS.

## Por que usar uma licença metered para a conversão de EPS para imagem?
Uma licença metered permite que você pague apenas pelas páginas que processa, o que é ideal para cargas de trabalho com volume variável. Ela também remove a faixa vermelha de avaliação que aparece ao usar a versão de teste, garantindo uma saída limpa para seus usuários finais.

## Pré‑requisitos

Antes de iniciar, certifique‑se de que os seguintes pré‑requisitos estejam atendidos:

- Uma licença válida do Aspose.Page para .NET: você pode obtê‑la em [purchase.aspose.com](https://purchase.aspose.com/buy).  
- Biblioteca Aspose.Page instalada: consulte a [documentação](https://reference.aspose.com/page/net/) para instruções de instalação.  
- Ambiente de desenvolvimento .NET: garanta que você tenha um ambiente .NET configurado e funcional em sua máquina.

## Importar Namespaces

No seu projeto .NET, importe os namespaces necessários para acessar as funcionalidades do Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Como converter EPS para PNG com uma licença metered?

A seguir, um guia passo a passo que cobre tudo o que você precisa saber.

### Etapa 1: Definir as Chaves Públicas e Privadas Metered

Inicialize a classe `Aspose.Page.Metered` e defina as chaves públicas e privadas metered. Substitua `<type public key here>` e `<type private key here>` pelas suas chaves reais.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Etapa 2: Carregar o Arquivo EPS e Criar o Documento

Especifique o caminho para o seu arquivo EPS e crie um stream para ler seu conteúdo. Em seguida, crie uma instância da classe `PsDocument` a partir do stream.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Etapa 3: Converter EPS para Imagem PNG

Crie um `ImageDevice` para converter o arquivo EPS em uma imagem PNG. Salve o arquivo EPS como imagem usando o `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Etapa 4: Recuperar os Bytes da Imagem

Obtenha os bytes da imagem, onde cada array de bytes representa uma página. Neste caso, temos apenas uma página.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Etapa 5: Salvar os Bytes da Imagem em Arquivo

Salve os bytes da imagem em um arquivo, garantindo a conversão bem‑sucedida de EPS para PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Etapa 6: Verificar a Licença Metered

Verifique visualmente se a licença metered foi aplicada com sucesso. Se a imagem resultante não contiver a mensagem vermelha de avaliação, isso indica que a licença metered está aplicada sem problemas.

Agora você está pronto para aproveitar todo o potencial do Aspose.Page para .NET com uma licença metered!

## Problemas Comuns e Soluções

| Problema | Causa | Solução |
|----------|-------|---------|
| A faixa vermelha de avaliação ainda aparece | Licença não definida ou chaves incorretas | Verifique novamente as chaves públicas/privadas e assegure que `SetMeteredKey` seja chamado antes de qualquer processamento de documento |
| Arquivo de saída não foi criado | Caminho `dataDir` incorreto ou permissões de arquivo | Confirme que o diretório existe e que a aplicação tem permissão de gravação |
| Páginas múltiplas não foram salvas | Apenas a primeira página foi escrita | Percorra `imagesBytes` e grave cada array em um arquivo PNG separado |

## Perguntas Frequentes

**P: Posso usar a licença metered em um pipeline CI/CD?**  
R: Sim, você pode armazenar as chaves de forma segura (por exemplo, em variáveis de ambiente) e chamar `SetMeteredKey` durante o processo de build.

**P: O Aspose.Page preserva o perfil de cores ao converter para PNG?**  
R: A saída PNG mantém as informações de cor originais, mas você pode personalizá‑las ainda mais via `ImageSaveOptions`.

**P: É possível converter EPS para outros formatos raster (JPEG, BMP)?**  
R: Absolutamente — basta alterar o `ImageSaveOptions` para o formato desejado.

**P: Qual é o tamanho máximo de arquivo EPS suportado?**  
R: O Aspose.Page lida com arquivos grandes, porém o consumo de memória aumenta com a resolução da imagem. Considere processar páginas individualmente para documentos muito extensos.

**P: Como obter programaticamente o número de páginas no arquivo EPS?**  
R: Use `document.PagesCount` após carregar o `PsDocument`.

## FAQ's

### Q1: Como obtenho uma licença metered para o Aspose.Page para .NET?

A1: Acesse [purchase.aspose.com](https://purchase.aspose.com/buy) para adquirir uma licença válida.

### Q2: Onde encontro a documentação do Aspose.Page para .NET?

A2: Consulte [Aspose.Page .NET](https://reference.aspose.com/page/net/) para documentação completa.

### Q3: Existe um fórum para discussões e suporte do Aspose.Page?

A3: Sim, visite o [forum](https://forum.aspose.com/c/page/39) para interagir com a comunidade e buscar assistência.

### Q4: Posso experimentar o Aspose.Page para .NET antes de comprar?

A4: Absolutamente! Acesse o teste gratuito [aqui](https://releases.aspose.com/).

### Q5: Como obtenho uma licença temporária para o Aspose.Page para .NET?

A5: Visite [temporary license/](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Última Atualização:** 2026-01-28  
**Testado com:** Aspose.Page 24.12 para .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}