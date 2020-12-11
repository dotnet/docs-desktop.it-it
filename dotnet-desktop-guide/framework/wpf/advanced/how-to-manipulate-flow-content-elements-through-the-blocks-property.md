---
title: 'Procedura: modificare elementi di contenuto del flusso tramite la proprietà Blocks'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: 3ca05590bd1adf7f9c486382a08cb334b4731ac9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952356"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="aa8d9-102">Procedura: modificare elementi di contenuto del flusso tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="aa8d9-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="aa8d9-103">Questi esempi illustrano alcune delle operazioni più comuni che possono essere eseguite sugli elementi di contenuto del flusso tramite la proprietà **Blocks** .</span><span class="sxs-lookup"><span data-stu-id="aa8d9-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="aa8d9-104">Questa proprietà viene utilizzata per aggiungere e rimuovere elementi da <xref:System.Windows.Documents.BlockCollection> .</span><span class="sxs-lookup"><span data-stu-id="aa8d9-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="aa8d9-105">Gli elementi di contenuto del flusso che includono una proprietà **Blocks** includono:</span><span class="sxs-lookup"><span data-stu-id="aa8d9-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
- <xref:System.Windows.Documents.Figure>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.ListItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="aa8d9-106">Questi esempi <xref:System.Windows.Documents.Section> vengono usati come elemento del contenuto di flusso, ma queste tecniche sono applicabili a tutti gli elementi che ospitano una raccolta di elementi di contenuto del flusso.</span><span class="sxs-lookup"><span data-stu-id="aa8d9-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa8d9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa8d9-107">Example</span></span>  
 <span data-ttu-id="aa8d9-108">Nell'esempio seguente viene creato un nuovo oggetto <xref:System.Windows.Documents.Section> , quindi viene utilizzato il metodo **Add** per aggiungere un nuovo paragrafo al contenuto della **sezione** .</span><span class="sxs-lookup"><span data-stu-id="aa8d9-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="aa8d9-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa8d9-109">Example</span></span>  
 <span data-ttu-id="aa8d9-110">Nell'esempio seguente viene creato un nuovo elemento che viene <xref:System.Windows.Documents.Paragraph> inserito all'inizio dell'oggetto <xref:System.Windows.Documents.Section> .</span><span class="sxs-lookup"><span data-stu-id="aa8d9-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="aa8d9-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa8d9-111">Example</span></span>  
 <span data-ttu-id="aa8d9-112">Nell'esempio seguente viene ottenuto il numero di elementi di primo livello <xref:System.Windows.Documents.Block> contenuti in <xref:System.Windows.Documents.Section> .</span><span class="sxs-lookup"><span data-stu-id="aa8d9-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="aa8d9-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa8d9-113">Example</span></span>  
 <span data-ttu-id="aa8d9-114">Nell'esempio seguente viene eliminato l'ultimo <xref:System.Windows.Documents.Block> elemento in <xref:System.Windows.Documents.Section> .</span><span class="sxs-lookup"><span data-stu-id="aa8d9-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="aa8d9-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa8d9-115">Example</span></span>  
 <span data-ttu-id="aa8d9-116">Nell'esempio seguente vengono cancellati tutti i contenuti ( <xref:System.Windows.Documents.Block> elementi) da <xref:System.Windows.Documents.Section> .</span><span class="sxs-lookup"><span data-stu-id="aa8d9-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="aa8d9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa8d9-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="aa8d9-118">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="aa8d9-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="aa8d9-119">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="aa8d9-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="aa8d9-120">Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="aa8d9-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="aa8d9-121">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="aa8d9-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
