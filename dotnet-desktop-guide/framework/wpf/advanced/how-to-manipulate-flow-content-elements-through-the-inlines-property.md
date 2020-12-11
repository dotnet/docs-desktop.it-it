---
title: 'Procedura: modificare elementi di contenuto del flusso tramite la proprietà Inlines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: 92f23fbf44464eb7658f3382f873f3db63f7cb26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966277"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="311e8-102">Procedura: modificare elementi di contenuto del flusso tramite la proprietà Inlines</span><span class="sxs-lookup"><span data-stu-id="311e8-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="311e8-103">Questi esempi illustrano alcune delle operazioni più comuni che possono essere eseguite sugli elementi di contenuto del flusso in linea (e contenitori di tali elementi, ad esempio <xref:System.Windows.Controls.TextBlock> ) tramite la proprietà **Inlines** .</span><span class="sxs-lookup"><span data-stu-id="311e8-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="311e8-104">Questa proprietà viene utilizzata per aggiungere e rimuovere elementi da <xref:System.Windows.Documents.InlineCollection> .</span><span class="sxs-lookup"><span data-stu-id="311e8-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="311e8-105">Gli elementi di contenuto del flusso che includono una proprietà **Inlines** includono:</span><span class="sxs-lookup"><span data-stu-id="311e8-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
- <xref:System.Windows.Documents.Bold>  
  
- <xref:System.Windows.Documents.Hyperlink>  
  
- <xref:System.Windows.Documents.Italic>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Span>  
  
- <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="311e8-106">Questi esempi si verificano <xref:System.Windows.Documents.Span> come elementi di contenuto del flusso, ma queste tecniche sono applicabili a tutti gli elementi o controlli che ospitano una <xref:System.Windows.Documents.InlineCollection> raccolta.</span><span class="sxs-lookup"><span data-stu-id="311e8-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="311e8-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="311e8-107">Example</span></span>  
 <span data-ttu-id="311e8-108">Nell'esempio seguente viene creato un nuovo <xref:System.Windows.Documents.Span> oggetto, quindi viene utilizzato il metodo **Add** per aggiungere due esecuzioni di testo come elementi figlio del contenuto di <xref:System.Windows.Documents.Span> .</span><span class="sxs-lookup"><span data-stu-id="311e8-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="311e8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="311e8-109">Example</span></span>  
 <span data-ttu-id="311e8-110">Nell'esempio seguente viene creato un nuovo elemento che viene <xref:System.Windows.Documents.Run> inserito all'inizio dell'oggetto <xref:System.Windows.Documents.Span> .</span><span class="sxs-lookup"><span data-stu-id="311e8-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="311e8-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="311e8-111">Example</span></span>  
 <span data-ttu-id="311e8-112">Nell'esempio seguente viene ottenuto il numero di elementi di primo livello <xref:System.Windows.Documents.Inline> contenuti in <xref:System.Windows.Documents.Span> .</span><span class="sxs-lookup"><span data-stu-id="311e8-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="311e8-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="311e8-113">Example</span></span>  
 <span data-ttu-id="311e8-114">Nell'esempio seguente viene eliminato l'ultimo <xref:System.Windows.Documents.Inline> elemento in <xref:System.Windows.Documents.Span> .</span><span class="sxs-lookup"><span data-stu-id="311e8-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="311e8-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="311e8-115">Example</span></span>  
 <span data-ttu-id="311e8-116">Nell'esempio seguente vengono cancellati tutti i contenuti ( <xref:System.Windows.Documents.Inline> elementi) da <xref:System.Windows.Documents.Span> .</span><span class="sxs-lookup"><span data-stu-id="311e8-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="311e8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="311e8-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="311e8-118">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="311e8-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="311e8-119">Modificare un oggetto FlowDocument tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="311e8-119">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="311e8-120">Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="311e8-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="311e8-121">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="311e8-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
