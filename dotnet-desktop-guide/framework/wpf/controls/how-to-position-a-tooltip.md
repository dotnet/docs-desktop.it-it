---
title: 'Procedura: posizionare un oggetto ToolTip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 851dc3c07e0abb4c7772f55f79900f1852b41232
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969772"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="c12d4-102">Procedura: posizionare un oggetto ToolTip</span><span class="sxs-lookup"><span data-stu-id="c12d4-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="c12d4-103">Questo esempio illustra come specificare la posizione di una descrizione comando sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="c12d4-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c12d4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c12d4-104">Example</span></span>  
 <span data-ttu-id="c12d4-105">È possibile posizionare una descrizione comando utilizzando un set di cinque proprietà definite in entrambe le <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> classi e.</span><span class="sxs-lookup"><span data-stu-id="c12d4-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="c12d4-106">Nella tabella seguente vengono illustrati questi due set di cinque proprietà e vengono forniti i collegamenti alla relativa documentazione di riferimento in base alla classe.</span><span class="sxs-lookup"><span data-stu-id="c12d4-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="c12d4-107">Proprietà della descrizione comando corrispondenti in base alla classe</span><span class="sxs-lookup"><span data-stu-id="c12d4-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="c12d4-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> Proprietà della classe</span><span class="sxs-lookup"><span data-stu-id="c12d4-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="c12d4-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> Proprietà della classe</span><span class="sxs-lookup"><span data-stu-id="c12d4-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="c12d4-110">Se si definisce il contenuto di una descrizione comando utilizzando un <xref:System.Windows.Controls.ToolTip> oggetto, è possibile utilizzare le proprietà di una delle due classi. Tuttavia, le <xref:System.Windows.Controls.ToolTipService> proprietà hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="c12d4-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="c12d4-111">Usare le <xref:System.Windows.Controls.ToolTipService> proprietà per le descrizioni comandi che non sono definite come <xref:System.Windows.Controls.ToolTip> oggetti.</span><span class="sxs-lookup"><span data-stu-id="c12d4-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="c12d4-112">Nelle illustrazioni seguenti viene illustrato come posizionare una descrizione comando utilizzando queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="c12d4-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="c12d4-113">Sebbene gli [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] esempi in queste illustrazioni mostrino come impostare le proprietà definite dalla <xref:System.Windows.Controls.ToolTip> classe, le proprietà corrispondenti della <xref:System.Windows.Controls.ToolTipService> classe seguono le stesse regole di layout.</span><span class="sxs-lookup"><span data-stu-id="c12d4-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="c12d4-114">Per ulteriori informazioni sui valori possibili per la proprietà di selezione host, vedere [comportamento di selezione host del popup](popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="c12d4-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="c12d4-115">Nell'immagine seguente viene illustrata la posizione della descrizione comando utilizzando la proprietà selezione host:</span><span class="sxs-lookup"><span data-stu-id="c12d4-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![Diagramma che mostra la posizione della descrizione comando utilizzando la proprietà Placement.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="c12d4-117">La figura seguente mostra la posizione della descrizione comando usando le proprietà Placement e PlacementRectangle:</span><span class="sxs-lookup"><span data-stu-id="c12d4-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![Diagramma che mostra la posizione della descrizione comando usando una proprietà PlacementRectangle.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="c12d4-119">Nell'immagine seguente viene illustrata la posizione della descrizione comando utilizzando le proprietà Placement, PlacementRectangle e offset:</span><span class="sxs-lookup"><span data-stu-id="c12d4-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![Diagramma che mostra la posizione della descrizione comando utilizzando la proprietà offset.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="c12d4-121">Nell'esempio seguente viene illustrato come utilizzare le <xref:System.Windows.Controls.ToolTip> proprietà per specificare la posizione di una descrizione comando il cui contenuto è un <xref:System.Windows.Controls.ToolTip> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c12d4-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="c12d4-122">Nell'esempio seguente viene illustrato come utilizzare le <xref:System.Windows.Controls.ToolTipService> proprietà per specificare la posizione di una descrizione comando il cui contenuto non è un <xref:System.Windows.Controls.ToolTip> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c12d4-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="c12d4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c12d4-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="c12d4-124">Procedure</span><span class="sxs-lookup"><span data-stu-id="c12d4-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="c12d4-125">Panoramica sul controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="c12d4-125">ToolTip Overview</span></span>](tooltip-overview.md)
