---
title: "Procedura: ruotare l'input penna"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], rotating
- rotating ink [WPF]
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
ms.openlocfilehash: 041147b7d5938d7d28d57169da1f1e880d69fe2b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951840"
---
# <a name="how-to-rotate-ink"></a>Procedura: ruotare l'input penna
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene copiato l'input penna da un oggetto <xref:System.Windows.Controls.InkCanvas> a un oggetto <xref:System.Windows.Controls.Canvas> che contiene un oggetto <xref:System.Windows.Controls.InkPresenter> .  Quando l'applicazione copia l'input penna, ruota anche l'input penna 90 gradi in senso orario.  
  
 [!code-xaml[HowToRotateInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un oggetto personalizzato <xref:System.Windows.Documents.Adorner> che ruota i tratti di un oggetto <xref:System.Windows.Controls.InkPresenter> .  
  
 [!code-csharp[AdornerForStrokes#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 L'esempio seguente è un [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file che definisce un oggetto <xref:System.Windows.Controls.InkPresenter> e lo popola con l'input penna. Il `Window_Loaded` gestore eventi aggiunge lo strumento decorativo personalizzato a <xref:System.Windows.Controls.InkPresenter> .  
  
 [!code-xaml[AdornerForStrokes#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]
