---
title: "Procedura: partizionare lo spazio utilizzando l'elemento DockPanel"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: 3682acc559e4e8740b97f781b6f927eac1e380d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969775"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Procedura: partizionare lo spazio utilizzando l'elemento DockPanel
Nell'esempio seguente viene creato un [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] Framework semplice utilizzando un <xref:System.Windows.Controls.DockPanel> elemento. <xref:System.Windows.Controls.DockPanel>Spazio disponibile nelle partizioni per i relativi elementi figlio.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzata la <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà, che è una proprietà associata, per ancorare due elementi identici <xref:System.Windows.Controls.Border> all'oggetto <xref:System.Windows.Controls.Dock.Top> dello spazio partizionato. Un terzo <xref:System.Windows.Controls.Border> elemento è ancorato a <xref:System.Windows.Controls.Dock.Left> , con larghezza impostata su 200 pixel. Un quarto <xref:System.Windows.Controls.Border> è ancorato all'oggetto <xref:System.Windows.Controls.Dock.Bottom> dello schermo. L'ultimo <xref:System.Windows.Controls.Border> elemento riempie automaticamente lo spazio rimanente.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> Per impostazione predefinita, l'ultimo elemento figlio di un <xref:System.Windows.Controls.DockPanel> elemento riempie lo spazio rimanente non allocato. Se non si desidera questo comportamento, impostare `LastChildFill="False"`.  
  
 L'applicazione compilata crea una nuova interfaccia utente analoga alla seguente.  
  
 ![Tipo scenario DockPanel](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DockPanel>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
