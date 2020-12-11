---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Matrix con accumulazione offset)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967066"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>Procedura: animare un oggetto lungo un percorso (animazione Matrix con accumulazione offset)
Questo esempio illustra come usare la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> classe per animare un oggetto lungo un tracciato e fare in modo che l'animazione accumuli i valori di offset durante la ripetizione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto per aggiungere un'animazione alla <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un oggetto <xref:System.Windows.Media.MatrixTransform> applicato a un pulsante. Di conseguenza, un pulsante si sposta lungo un tracciato curvo.  
  
 Inoltre, nell'esempio la proprietà viene impostata <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> su `true` , in modo che l'offset della matrice animata si accumuli quando l'animazione si ripete. Poiché lo scostamento si accumula, il pulsante viene spostato ulteriormente sullo schermo quando l'animazione si ripete, piuttosto che tornare nella posizione iniziale.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 Si noti che, sebbene la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> Proprietà provochi l'accumulo dei valori di offset nelle ripetizioni, non causa l'accumulo dei valori di rotazione. Per aumentare l'accumulo dei valori di rotazione, impostare le <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> proprietà e dell'animazione <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> su `true` .  
  
 Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations). Per un esempio che illustra come animare un <xref:System.Windows.Media.Matrix> valore lungo un tracciato senza accumulo di offset, vedere [animare un oggetto lungo un tracciato (animazione Matrix)](how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
