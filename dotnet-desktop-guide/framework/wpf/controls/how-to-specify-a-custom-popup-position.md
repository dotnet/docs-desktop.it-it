---
title: 'Procedura: specificare una posizione personalizzata per un controllo Popup'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967708"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="cd4ea-102">Procedura: specificare una posizione personalizzata per un controllo Popup</span><span class="sxs-lookup"><span data-stu-id="cd4ea-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="cd4ea-103">Questo esempio illustra come specificare una posizione personalizzata per un <xref:System.Windows.Controls.Primitives.Popup> controllo quando la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> .</span><span class="sxs-lookup"><span data-stu-id="cd4ea-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd4ea-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd4ea-104">Example</span></span>  
 <span data-ttu-id="cd4ea-105">Quando la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> , <xref:System.Windows.Controls.Primitives.Popup> chiama un'istanza definita del <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="cd4ea-106">Questo delegato restituisce un set di punti possibili relativi all'angolo superiore sinistro dell'area di destinazione e all'angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup> .</span><span class="sxs-lookup"><span data-stu-id="cd4ea-106">This delegate returns a set of possible points that are relative to the top-left corner of the target area and the top-left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="cd4ea-107">La <xref:System.Windows.Controls.Primitives.Popup> posizione si verifica nel punto che fornisce la visibilità migliore.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="cd4ea-108">Nell'esempio seguente viene illustrato come definire la posizione di un oggetto impostando <xref:System.Windows.Controls.Primitives.Popup> la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> .</span><span class="sxs-lookup"><span data-stu-id="cd4ea-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="cd4ea-109">Viene inoltre illustrato come creare e assegnare un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato per posizionare <xref:System.Windows.Controls.Primitives.Popup> .</span><span class="sxs-lookup"><span data-stu-id="cd4ea-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="cd4ea-110">Il delegato di callback restituisce due <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="cd4ea-111">Se l'oggetto <xref:System.Windows.Controls.Primitives.Popup> è nascosto da un bordo dello schermo nella prima posizione, l'oggetto <xref:System.Windows.Controls.Primitives.Popup> viene posizionato in corrispondenza della seconda posizione.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="cd4ea-112">Per l'esempio completo, vedere [esempio di selezione host popup](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span><span class="sxs-lookup"><span data-stu-id="cd4ea-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4ea-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd4ea-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="cd4ea-114">Panoramica di popup</span><span class="sxs-lookup"><span data-stu-id="cd4ea-114">Popup overview</span></span>](popup-overview.md)
- [<span data-ttu-id="cd4ea-115">Procedure</span><span class="sxs-lookup"><span data-stu-id="cd4ea-115">How-to articles</span></span>](popup-how-to-topics.md)
