---
title: 'Procedura: regolare la spaziatura tra paragrafi'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964612"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="74795-102">Procedura: regolare la spaziatura tra paragrafi</span><span class="sxs-lookup"><span data-stu-id="74795-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="74795-103">Questo esempio illustra come regolare o eliminare la spaziatura tra i paragrafi nel contenuto del flusso.</span><span class="sxs-lookup"><span data-stu-id="74795-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="74795-104">In contenuto dinamico, lo spazio aggiuntivo visualizzato tra i paragrafi è il risultato dei margini impostati su questi paragrafi; la spaziatura tra i paragrafi può quindi essere controllata regolando i margini dei paragrafi.</span><span class="sxs-lookup"><span data-stu-id="74795-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="74795-105">Per eliminare completamente la spaziatura aggiuntiva tra due paragrafi, impostare i margini per i paragrafi su **0**.</span><span class="sxs-lookup"><span data-stu-id="74795-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="74795-106">Per ottenere una spaziatura uniforme tra i paragrafi nell'intero oggetto <xref:System.Windows.Documents.FlowDocument> , utilizzare lo stile per impostare un valore di margine uniforme per tutti i paragrafi in <xref:System.Windows.Documents.FlowDocument> .</span><span class="sxs-lookup"><span data-stu-id="74795-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="74795-107">È importante notare che i margini per due paragrafi adiacenti comporteranno il "collasso" al più grande dei due margini, anziché raddoppiare.</span><span class="sxs-lookup"><span data-stu-id="74795-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="74795-108">Quindi, se due paragrafi adiacenti hanno rispettivamente margini di 20 pixel e 40 pixel, lo spazio risultante tra i paragrafi è 40 pixel, maggiore è il numero di valori dei due margini.</span><span class="sxs-lookup"><span data-stu-id="74795-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74795-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="74795-109">Example</span></span>  
 <span data-ttu-id="74795-110">Nell'esempio seguente viene utilizzato lo stile per impostare il margine di tutti <xref:System.Windows.Documents.Paragraph> gli elementi in un oggetto <xref:System.Windows.Documents.FlowDocument> su **0**, eliminando in tal modo la spaziatura aggiuntiva tra i paragrafi in <xref:System.Windows.Documents.FlowDocument> .</span><span class="sxs-lookup"><span data-stu-id="74795-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
