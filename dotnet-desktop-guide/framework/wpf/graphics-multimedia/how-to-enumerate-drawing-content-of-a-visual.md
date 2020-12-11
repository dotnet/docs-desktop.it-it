---
title: 'Procedura: enumerare il contenuto del disegno di un oggetto Visual'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968746"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>Procedura: enumerare il contenuto del disegno di un oggetto Visual
L' <xref:System.Windows.Media.Drawing> oggetto fornisce un modello a oggetti per l'enumerazione del contenuto di un oggetto <xref:System.Windows.Media.Visual> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metodo per recuperare il <xref:System.Windows.Media.DrawingGroup> valore di un oggetto <xref:System.Windows.Media.Visual> ed enumerarlo.  
  
> [!NOTE]
> Quando si enumera il contenuto dell'oggetto visivo, si recuperano <xref:System.Windows.Media.Drawing> gli oggetti e non la rappresentazione sottostante dei dati di rendering come elenco di istruzioni di grafica vettoriale. Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
