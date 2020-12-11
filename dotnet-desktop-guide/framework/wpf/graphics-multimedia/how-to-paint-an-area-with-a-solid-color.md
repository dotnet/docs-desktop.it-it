---
title: "Procedura: disegnare un'area con un colore a tinta unita"
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964522"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Procedura: disegnare un'area con un colore a tinta unita
Per disegnare un'area con un colore a tinta unita, è possibile usare un pennello di sistema predefinito, ad esempio <xref:System.Windows.Media.Brushes.Red%2A> o <xref:System.Windows.Media.Brushes.Blue%2A> , oppure è possibile creare un nuovo oggetto <xref:System.Windows.Media.SolidColorBrush> e descriverne il nome <xref:System.Windows.Media.SolidColorBrush.Color%2A> usando i valori alfa, rosso, verde e blu. In XAML è anche possibile disegnare un'area con un colore a tinta unita usando la notazione esadecimale.  
  
 Negli esempi seguenti vengono usate ognuna di queste tecniche per disegnare un <xref:System.Windows.Shapes.Rectangle> blu.  
  
## <a name="example"></a>Esempio  
 **Uso di un pennello predefinito**  
  
 Nell'esempio seguente viene usato il pennello predefinito <xref:System.Windows.Media.Brushes.Blue%2A> per disegnare un rettangolo blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Uso della notazione esadecimale**  
  
 L'esempio successivo usa la notazione esadecimale a 8 cifre per disegnare un rettangolo blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Uso dei valori ARGB**  
  
 Nell'esempio successivo viene creato un oggetto <xref:System.Windows.Media.SolidColorBrush> e ne viene descritto l' <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizzo dei valori ARGB per il colore blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Per altri modi di descrivere il colore, vedere la <xref:System.Windows.Media.Color> struttura.  
  
 **Argomenti correlati**  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.SolidColorBrush> ed esempi aggiuntivi, vedere Cenni preliminari sul [disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md) .  
  
 Questo esempio di codice fa parte di un esempio più ampio fornito per la <xref:System.Windows.Media.SolidColorBrush> classe. Per l'esempio completo, vedere [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Esempio di pennelli).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brushes>
