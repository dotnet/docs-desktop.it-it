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
# <a name="how-to-position-a-tooltip"></a>Procedura: posizionare un oggetto ToolTip
Questo esempio illustra come specificare la posizione di una descrizione comando sullo schermo.  
  
## <a name="example"></a>Esempio  
 È possibile posizionare una descrizione comando utilizzando un set di cinque proprietà definite in entrambe le <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> classi e. Nella tabella seguente vengono illustrati questi due set di cinque proprietà e vengono forniti i collegamenti alla relativa documentazione di riferimento in base alla classe.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Proprietà della descrizione comando corrispondenti in base alla classe  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> Proprietà della classe|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> Proprietà della classe|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Se si definisce il contenuto di una descrizione comando utilizzando un <xref:System.Windows.Controls.ToolTip> oggetto, è possibile utilizzare le proprietà di una delle due classi. Tuttavia, le <xref:System.Windows.Controls.ToolTipService> proprietà hanno la precedenza. Usare le <xref:System.Windows.Controls.ToolTipService> proprietà per le descrizioni comandi che non sono definite come <xref:System.Windows.Controls.ToolTip> oggetti.  
  
 Nelle illustrazioni seguenti viene illustrato come posizionare una descrizione comando utilizzando queste proprietà. Sebbene gli [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] esempi in queste illustrazioni mostrino come impostare le proprietà definite dalla <xref:System.Windows.Controls.ToolTip> classe, le proprietà corrispondenti della <xref:System.Windows.Controls.ToolTipService> classe seguono le stesse regole di layout. Per ulteriori informazioni sui valori possibili per la proprietà di selezione host, vedere [comportamento di selezione host del popup](popup-placement-behavior.md).  

 Nell'immagine seguente viene illustrata la posizione della descrizione comando utilizzando la proprietà selezione host:  
  
 ![Diagramma che mostra la posizione della descrizione comando utilizzando la proprietà Placement.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 La figura seguente mostra la posizione della descrizione comando usando le proprietà Placement e PlacementRectangle:

 ![Diagramma che mostra la posizione della descrizione comando usando una proprietà PlacementRectangle.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 Nell'immagine seguente viene illustrata la posizione della descrizione comando utilizzando le proprietà Placement, PlacementRectangle e offset:
  
 ![Diagramma che mostra la posizione della descrizione comando utilizzando la proprietà offset.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 Nell'esempio seguente viene illustrato come utilizzare le <xref:System.Windows.Controls.ToolTip> proprietà per specificare la posizione di una descrizione comando il cui contenuto è un <xref:System.Windows.Controls.ToolTip> oggetto.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 Nell'esempio seguente viene illustrato come utilizzare le <xref:System.Windows.Controls.ToolTipService> proprietà per specificare la posizione di una descrizione comando il cui contenuto non è un <xref:System.Windows.Controls.ToolTip> oggetto.  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Procedure](tooltip-how-to-topics.md)
- [Panoramica sul controllo ToolTip](tooltip-overview.md)
