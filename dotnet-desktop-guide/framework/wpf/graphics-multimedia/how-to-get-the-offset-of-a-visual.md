---
title: "Procedura: ottenere l'offset di un oggetto Visual"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: 4787b771c7e59a8b033b9267079c068a5845a1e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965275"
---
# <a name="how-to-get-the-offset-of-a-visual"></a>Procedura: ottenere l'offset di un oggetto Visual
In questi esempi viene illustrato come recuperare il valore di offset di un oggetto visivo relativo al padre o a qualsiasi predecessore o discendente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di markup seguente viene illustrato un oggetto <xref:System.Windows.Controls.TextBlock> definito con un <xref:System.Windows.FrameworkElement.Margin%2A> valore pari a 4.  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 Nell'esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> metodo per recuperare l'offset di <xref:System.Windows.Controls.TextBlock> . I valori di offset sono contenuti nel <xref:System.Windows.Vector> valore restituito.  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> valore. In questo caso, <xref:System.Windows.Vector.X%2A> è 4 e <xref:System.Windows.Vector.Y%2A> è 4.  
  
 Il valore di offset restituito è relativo all'elemento padre dell'oggetto <xref:System.Windows.Media.Visual> . Se si desidera restituire un valore di offset che non è relativo all'elemento padre di un oggetto <xref:System.Windows.Media.Visual> , utilizzare il <xref:System.Windows.Media.Visual.TransformToAncestor%2A> metodo.  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a>Recupero dell'offset rispetto a un predecessore  
 Nell'esempio di markup seguente viene illustrato un oggetto <xref:System.Windows.Controls.TextBlock> annidato all'interno di due <xref:System.Windows.Controls.StackPanel> oggetti.  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 Nella figura seguente vengono illustrati i risultati del markup.  
  
 ![Valori di offset degli oggetti](./media/visualoffset-01.png "VisualOffset_01")  
TextBlock annidato all'interno di due StackPanel  
  
 Nell'esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Visual.TransformToAncestor%2A> metodo per recuperare l'offset dell'oggetto <xref:System.Windows.Controls.TextBlock> rispetto all'oggetto che lo contiene <xref:System.Windows.Window> . I valori di offset sono contenuti nel <xref:System.Windows.Media.GeneralTransform> valore restituito.  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 L'offset prende in considerazione i <xref:System.Windows.FrameworkElement.Margin%2A> valori per tutti gli oggetti all'interno dell'oggetto che lo contiene <xref:System.Windows.Window> . In questo caso, <xref:System.Windows.Vector.X%2A> è 28 (16 + 8 + 4) e <xref:System.Windows.Vector.Y%2A> è 28.  
  
 Il valore di offset restituito è relativo al predecessore di <xref:System.Windows.Media.Visual> . Se si desidera restituire un valore di offset relativo al discendente di un oggetto <xref:System.Windows.Media.Visual> , utilizzare il <xref:System.Windows.Media.Visual.TransformToDescendant%2A> metodo.  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a>Recupero dell'offset rispetto a un discendente  
 Nell'esempio di markup seguente viene illustrato un <xref:System.Windows.Controls.TextBlock> oggetto contenuto all'interno di un <xref:System.Windows.Controls.StackPanel> oggetto.  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 Nell'esempio di codice riportato di seguito viene illustrato come utilizzare il <xref:System.Windows.Media.Visual.TransformToDescendant%2A> metodo per recuperare l'offset dell'oggetto <xref:System.Windows.Controls.StackPanel> rispetto al relativo elemento figlio <xref:System.Windows.Controls.TextBlock> . I valori di offset sono contenuti nel <xref:System.Windows.Media.GeneralTransform> valore restituito.  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 L'offset prende in considerazione i <xref:System.Windows.FrameworkElement.Margin%2A> valori per tutti gli oggetti. In questo caso, <xref:System.Windows.Vector.X%2A> è-4 e <xref:System.Windows.Vector.Y%2A> è-4. I valori di offset sono valori negativi, perché l'oggetto padre viene offset negativo rispetto al relativo oggetto figlio.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
