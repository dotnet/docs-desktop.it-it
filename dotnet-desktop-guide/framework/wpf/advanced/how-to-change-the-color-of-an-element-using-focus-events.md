---
title: 'Procedura: modificare il colore di un elemento utilizzando eventi di stato attivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: c5c0520aa60f1906f2fb3f545c795ba0034a09bd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964978"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Procedura: modificare il colore di un elemento utilizzando eventi di stato attivo
In questo esempio viene illustrato come modificare il colore di un elemento quando ottiene e perde lo stato attivo tramite gli <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus> eventi e.  
  
 Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.  
  
## <a name="example"></a>Esempio  
 Il codice XAML seguente crea l'interfaccia utente, che è costituita da due <xref:System.Windows.Controls.Button> oggetti, e connette i gestori eventi per gli <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus> eventi e agli <xref:System.Windows.Controls.Button> oggetti.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Il codice sottostante seguente consente di creare i <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus> gestori eventi e.  Quando <xref:System.Windows.Controls.Button> ottiene lo stato attivo della tastiera, l'oggetto <xref:System.Windows.Controls.Control.Background%2A> di <xref:System.Windows.Controls.Button> viene modificato in rosso.  Quando <xref:System.Windows.Controls.Button> perde lo stato attivo della tastiera, l'oggetto <xref:System.Windows.Controls.Control.Background%2A> di <xref:System.Windows.Controls.Button> viene modificato di nuovo in bianco.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
