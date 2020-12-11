---
title: 'Procedura: migliorare le prestazioni di un controllo TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: de1b46da2a7c6c3db0c0c19cdbb654fcf2fbbd6c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966637"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Procedura: migliorare le prestazioni di un controllo TreeView
Se un oggetto <xref:System.Windows.Controls.TreeView> contiene molti elementi, la quantità di tempo necessaria per il caricamento può causare un ritardo significativo nell'interfaccia utente. È possibile migliorare il tempo di caricamento impostando la `VirtualizingStackPanel.IsVirtualizing` proprietà associata su `true` .  L'interfaccia utente potrebbe anche essere lenta per rispondere quando un utente scorre l'oggetto <xref:System.Windows.Controls.TreeView> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento. È possibile migliorare le prestazioni di <xref:System.Windows.Controls.TreeView> quando l'utente scorre impostando la `VirtualizingStackPanel.VirtualizationMode` proprietà associata su <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> .  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.TreeView> che imposta la `VirtualizingStackPanel.IsVirtualizing` proprietà associata su true e la `VirtualizingStackPanel.VirtualizationMode` proprietà associata su <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per ottimizzare le prestazioni.  
  
## <a name="code"></a>Codice  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 Nell'esempio seguente vengono illustrati i dati utilizzati nell'esempio precedente.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](../advanced/optimizing-performance-controls.md)
