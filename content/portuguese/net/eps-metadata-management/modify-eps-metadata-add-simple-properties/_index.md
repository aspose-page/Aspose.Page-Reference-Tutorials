---
title: Adicione propriedades simples com Aspose.Page para .NET
linktitle: Adicionar propriedades simples
second_title: API Aspose.Page .NET
description: Aprimore arquivos EPS com Aspose.Page for .NET. Adicione propriedades simples sem esforço para metadados de documentos personalizados.
type: docs
weight: 14
url: /pt/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## Introdução

No domínio da manipulação e aprimoramento de documentos, o Aspose.Page for .NET surge como uma ferramenta poderosa, fornecendo aos desenvolvedores a capacidade de adicionar e modificar metadados XMP em arquivos EPS perfeitamente. Este tutorial irá guiá-lo através do processo de adição de propriedades simples a um arquivo EPS usando Aspose.Page for .NET.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Aspose.Page for .NET: Certifique-se de ter o Aspose.Page for .NET instalado em seu ambiente de desenvolvimento. Se não, você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).

2.  Diretório de documentos: Configure um diretório para armazenar seus arquivos EPS. Atualize o`dataDir` variável no trecho de código fornecido com o caminho para o diretório do documento.

## Importar namespaces

Para começar, importe os namespaces necessários para permitir a comunicação com Aspose.Page for .NET. Adicione as seguintes linhas no início do seu arquivo de código:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Etapa 1: inicializar o fluxo de entrada do arquivo EPS

```csharp
// ExInício:1
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
// Inicializar fluxo de entrada de arquivo EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Crie uma instância PsDocument do stream
PsDocument document = new PsDocument(psStream);
```

## Etapa 2: Obtenha metadados XMP

```csharp
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, obteremos um novo preenchido com valores de comentários de metadados PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Etapa 3: alterar os valores de metadados XMP

```csharp
// Alterar valores de metadados XMP
DateTime now = DateTime.UtcNow;

// Adicionar propriedade Inteira
xmp.Add("xmp:Intg1", new XmpValue(111));

// Adicionar propriedade DateTime
xmp.Add("xmp:Date1", new XmpValue(now));

// Adicionar propriedade dupla
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Adicionar propriedade String
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Etapa 4: Salvar arquivo EPS com metadados XMP alterados

```csharp
// Salvar arquivo EPS com metadados XMP alterados

// Criar fluxo de saída
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Salvar arquivo EPS
    document.Save(outPsStream);
}
```

## Etapa 5: feche o FileStream

```csharp
finally
{
    psStream.Close();
}
```

Seguindo essas etapas, você pode incorporar facilmente propriedades simples em seus arquivos EPS usando Aspose.Page for .NET.

## Conclusão

Concluindo, Aspose.Page for .NET prova ser um recurso inestimável para desenvolvedores que buscam aprimorar arquivos EPS com metadados XMP personalizados. Ao adicionar propriedades simples, você pode personalizar e enriquecer seus documentos para atender a requisitos específicos, abrindo um mundo de possibilidades para manipulação de documentos.

## Perguntas frequentes

### Q1: O Aspose.Page for .NET é compatível com todos os arquivos EPS?

A1: Aspose.Page for .NET oferece suporte a uma ampla variedade de arquivos EPS. No entanto, a compatibilidade pode variar com base na complexidade e estrutura de arquivos individuais.

### Q2: Posso modificar metadados XMP existentes com Aspose.Page for .NET?

A2: Com certeza! Conforme demonstrado neste tutorial, você pode alterar facilmente os valores de metadados XMP existentes ou adicionar novos para atender às suas necessidades.

### P3: Há alguma limitação nos tipos de propriedades que posso adicionar?

A3: Aspose.Page for .NET oferece suporte a vários tipos de dados para propriedades, incluindo números inteiros, datas, duplos e strings. Você tem flexibilidade na escolha do tipo apropriado para seus metadados.

### Q4: Como posso obter suporte técnico para Aspose.Page for .NET?

 A4: Para assistência técnica, visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) ou explorar o[documentação](https://reference.aspose.com/page/net/) para orientação abrangente.

### Q5: Existe uma avaliação gratuita disponível para Aspose.Page for .NET?

 A5: Sim, você pode acessar uma avaliação gratuita[aqui](https://releases.aspose.com/).