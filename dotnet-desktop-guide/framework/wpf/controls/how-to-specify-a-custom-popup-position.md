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
# <a name="how-to-specify-a-custom-popup-position"></a>Procedura: specificare una posizione personalizzata per un controllo Popup
Questo esempio illustra come specificare una posizione personalizzata per un <xref:System.Windows.Controls.Primitives.Popup> controllo quando la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> .  
  
## <a name="example"></a>Esempio  
 Quando la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> , <xref:System.Windows.Controls.Primitives.Popup> chiama un'istanza definita del <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato. Questo delegato restituisce un set di punti possibili relativi all'angolo superiore sinistro dell'area di destinazione e all'angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup> . La <xref:System.Windows.Controls.Primitives.Popup> posizione si verifica nel punto che fornisce la visibilità migliore.  
  
 Nell'esempio seguente viene illustrato come definire la posizione di un oggetto impostando <xref:System.Windows.Controls.Primitives.Popup> la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> . Viene inoltre illustrato come creare e assegnare un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato per posizionare <xref:System.Windows.Controls.Primitives.Popup> .  Il delegato di callback restituisce due <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> oggetti.  Se l'oggetto <xref:System.Windows.Controls.Primitives.Popup> è nascosto da un bordo dello schermo nella prima posizione, l'oggetto <xref:System.Windows.Controls.Primitives.Popup> viene posizionato in corrispondenza della seconda posizione.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Per l'esempio completo, vedere [esempio di selezione host popup](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Popup>
- [Panoramica di popup](popup-overview.md)
- [Procedure](popup-how-to-topics.md)
