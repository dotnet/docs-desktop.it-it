---
title: 'Procedura: gestire un evento caricato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 7ca95e195792f8fb4789c481e84dda51f2910434
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963763"
---
# <a name="how-to-handle-a-loaded-event"></a>Procedura: gestire un evento caricato
Questo esempio illustra come gestire l' <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> evento e uno scenario appropriato per la gestione dell'evento. Il gestore crea un oggetto <xref:System.Windows.Controls.Button> quando viene caricata la pagina.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] insieme a un file code-behind.  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement>
- [Eventi di durata degli oggetti](object-lifetime-events.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Procedure](base-elements-how-to-topics.md)
