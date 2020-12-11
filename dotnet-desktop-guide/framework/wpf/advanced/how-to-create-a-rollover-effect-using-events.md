---
title: 'Procedura: creare un effetto di attivazione utilizzando gli eventi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: d4587b7b116045af11702a99c841956434f96404
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967807"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Procedura: creare un effetto di attivazione utilizzando gli eventi
Questo esempio Mostra come modificare il colore di un elemento quando il puntatore del mouse entra e lascia l'area occupata dall'elemento.  
  
 Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.  
  
> [!NOTE]
> Questo esempio illustra come usare gli eventi, ma la modalità consigliata per ottenere questo risultato consiste nell'usare un oggetto <xref:System.Windows.Trigger> in uno stile. Per altre informazioni, vedere [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).  
  
## <a name="example"></a>Esempio  
 Il codice XAML seguente crea l'interfaccia utente, che consiste <xref:System.Windows.Controls.Border> in un oggetto <xref:System.Windows.Controls.TextBlock> , e connette i <xref:System.Windows.Input.Mouse.MouseEnter> <xref:System.Windows.UIElement.MouseLeave> gestori eventi e a <xref:System.Windows.Controls.Border> .  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Il codice sottostante seguente consente di creare i <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave> gestori eventi e.  Quando il puntatore del mouse entra <xref:System.Windows.Controls.Border> in, lo sfondo di <xref:System.Windows.Controls.Border> viene modificato in rosso.  Quando il puntatore del mouse esce dall'oggetto <xref:System.Windows.Controls.Border> , lo sfondo di <xref:System.Windows.Controls.Border> viene modificato di nuovo in bianco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
