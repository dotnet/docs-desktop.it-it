---
title: "Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati"
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: ad671b81bdfc1c168294123d035ccf7287b3b2fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964549"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati
## <a name="example"></a>Esempio
 In questo esempio viene illustrato come gestire gli spazi dei nomi specificati nell'origine del binding XML.

 Se i dati XML hanno la definizione dello spazio dei nomi XML seguente:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 È possibile usare l' <xref:System.Windows.Data.XmlNamespaceMapping> elemento per eseguire il mapping dello spazio dei nomi a un oggetto <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> , come nell'esempio seguente. È quindi possibile usare <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> per fare riferimento allo spazio dei nomi XML. <xref:System.Windows.Controls.ListBox>In questo esempio vengono visualizzati il *titolo* e il controller di dominio *: data* di ogni *elemento*.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Si noti che l'oggetto <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> specificato non deve corrispondere a quello utilizzato nell'origine XML. se il prefisso viene modificato nell'origine XML, il mapping continua a funzionare.

 In questo particolare esempio, i dati XML provengono da un servizio Web, ma l' <xref:System.Windows.Data.XmlNamespaceMapping> elemento funziona anche con dati XML o XML inline in un file incorporato.

## <a name="see-also"></a>Vedere anche

- [Eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
