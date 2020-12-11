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
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="b9026-102">Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati</span><span class="sxs-lookup"><span data-stu-id="b9026-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="b9026-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9026-103">Example</span></span>
 <span data-ttu-id="b9026-104">In questo esempio viene illustrato come gestire gli spazi dei nomi specificati nell'origine del binding XML.</span><span class="sxs-lookup"><span data-stu-id="b9026-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="b9026-105">Se i dati XML hanno la definizione dello spazio dei nomi XML seguente:</span><span class="sxs-lookup"><span data-stu-id="b9026-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="b9026-106">È possibile usare l' <xref:System.Windows.Data.XmlNamespaceMapping> elemento per eseguire il mapping dello spazio dei nomi a un oggetto <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> , come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b9026-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="b9026-107">È quindi possibile usare <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> per fare riferimento allo spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="b9026-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="b9026-108"><xref:System.Windows.Controls.ListBox>In questo esempio vengono visualizzati il *titolo* e il controller di dominio *: data* di ogni *elemento*.</span><span class="sxs-lookup"><span data-stu-id="b9026-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="b9026-109">Si noti che l'oggetto <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> specificato non deve corrispondere a quello utilizzato nell'origine XML. se il prefisso viene modificato nell'origine XML, il mapping continua a funzionare.</span><span class="sxs-lookup"><span data-stu-id="b9026-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="b9026-110">In questo particolare esempio, i dati XML provengono da un servizio Web, ma l' <xref:System.Windows.Data.XmlNamespaceMapping> elemento funziona anche con dati XML o XML inline in un file incorporato.</span><span class="sxs-lookup"><span data-stu-id="b9026-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9026-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9026-111">See also</span></span>

- [<span data-ttu-id="b9026-112">Eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath</span><span class="sxs-lookup"><span data-stu-id="b9026-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="b9026-113">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="b9026-113">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="b9026-114">Procedure</span><span class="sxs-lookup"><span data-stu-id="b9026-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
