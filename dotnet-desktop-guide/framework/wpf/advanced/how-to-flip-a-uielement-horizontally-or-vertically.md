---
title: 'Procedura: capovolgere un oggetto UIElement orizzontalmente o verticalmente'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967852"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>Procedura: capovolgere un oggetto UIElement orizzontalmente o verticalmente
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.ScaleTransform> per capovolgere <xref:System.Windows.UIElement> orizzontalmente o verticalmente. In questo esempio un <xref:System.Windows.Controls.Button> controllo (un tipo di <xref:System.Windows.UIElement> ) viene capovolto applicando un oggetto <xref:System.Windows.Media.ScaleTransform> alla relativa <xref:System.Windows.UIElement.RenderTransform%2A> Proprietà.  
  
## <a name="example"></a>Esempio  
 Nella figura seguente viene illustrato il pulsante da capovolgere.  
  
 ![Pulsante senza trasformazioni](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")  
UIElement da capovolgere  
  
 Di seguito viene illustrato il codice che crea il pulsante.  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>Esempio  
 Per capovolgere il pulsante orizzontalmente, creare un oggetto <xref:System.Windows.Media.ScaleTransform> e impostare la relativa <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> proprietà su-1. Applicare l'oggetto <xref:System.Windows.Media.ScaleTransform> alla proprietà del pulsante <xref:System.Windows.UIElement.RenderTransform%2A> .  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Pulsante capovolto orizzontalmente intorno &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")  
Pulsante dopo l'applicazione di ScaleTransform  
  
## <a name="example"></a>Esempio  
 Come si può notare dalla figura precedente, il pulsante è stato capovolto, ma è stato spostato. Questo perché il pulsante è stato capovolto dall'angolo superiore sinistro. Per capovolgere il pulsante sul posto, è necessario applicare al <xref:System.Windows.Media.ScaleTransform> centro, non all'angolo. Un modo semplice per applicare al <xref:System.Windows.Media.ScaleTransform> Centro pulsanti consiste nell'impostare la proprietà del pulsante <xref:System.Windows.UIElement.RenderTransformOrigin%2A> su 0,5, 0,5.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Pulsante capovolto orizzontalmente rispetto al proprio centro](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")  
Pulsante con RenderTransformOrigin 0,5, 0,5  
  
## <a name="example"></a>Esempio  
 Per capovolgere il pulsante verticalmente, impostare la <xref:System.Windows.Media.ScaleTransform> proprietà dell'oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> invece della relativa <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Proprietà.  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Pulsante capovolto verticalmente rispetto al proprio centro](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")  
Pulsante capovolto verticalmente  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle trasformazioni](../graphics-multimedia/transforms-overview.md)
