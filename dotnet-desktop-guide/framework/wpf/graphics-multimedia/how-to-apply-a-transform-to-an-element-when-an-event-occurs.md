---
title: 'Procedura: applicare una trasformazione a un elemento quando si verifica un evento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 8f04db274432c0e89c6839bef825976c8a2f853c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960817"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>Procedura: applicare una trasformazione a un elemento quando si verifica un evento
Questo esempio illustra come applicare un oggetto <xref:System.Windows.Media.ScaleTransform> quando si verifica un evento. Il concetto illustrato è identico a quello usato per applicare altri tipi di trasformazioni. Per ulteriori informazioni sui tipi di trasformazioni disponibili, vedere <xref:System.Windows.Media.Transform> Cenni preliminari sulla classe o sulle [trasformazioni](transforms-overview.md).  
  
 È possibile applicare una trasformazione a un elemento in uno dei due modi seguenti:  
  
- Se *non* si desidera che la trasformazione influisca sul layout, utilizzare la <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.  
  
- Se si desidera che la trasformazione influisca sul layout, utilizzare la <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà dell'elemento.  
  
 Nell'esempio seguente viene applicato un oggetto <xref:System.Windows.Media.ScaleTransform> alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un pulsante. Quando il mouse viene spostato sul pulsante, le <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà e di <xref:System.Windows.Media.ScaleTransform> sono impostate su `2` , che determina un aumento delle dimensioni del pulsante. Quando il mouse viene spostato fuori dal pulsante <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> viene impostato su `1` , che fa sì che il pulsante ritorni alle dimensioni originali.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure](transformations-how-to-topics.md)
- [Cenni preliminari sugli eventi indirizzati](../advanced/routed-events-overview.md)
