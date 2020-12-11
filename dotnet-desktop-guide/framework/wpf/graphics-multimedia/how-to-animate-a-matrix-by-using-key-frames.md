---
title: 'Procedura: animare una matrice utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967021"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Procedura: animare una matrice utilizzando fotogrammi chiave
In questo esempio viene illustrato come animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un oggetto utilizzando <xref:System.Windows.Media.MatrixTransform> fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un oggetto <xref:System.Windows.Media.MatrixTransform> . Nell'esempio viene utilizzato l' <xref:System.Windows.Media.MatrixTransform> oggetto per trasformare l'aspetto e la posizione di un oggetto <xref:System.Windows.Controls.Button> .  
  
 Questa animazione usa la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> classe per creare due fotogrammi chiave ed esegue le operazioni seguenti:  
  
1. Anima il primo <xref:System.Windows.Media.Matrix> durante i primi 0,2 secondi. Nell'esempio vengono modificate <xref:System.Windows.Media.Matrix.M11%2A> le <xref:System.Windows.Media.Matrix.M12%2A> proprietà e di <xref:System.Windows.Media.Matrix> . Questa modifica determina l'estensione del pulsante e la distorsione. Nell'esempio vengono anche modificate <xref:System.Windows.Media.Matrix.OffsetX%2A> le <xref:System.Windows.Media.Matrix.OffsetY%2A> proprietà e in modo che il pulsante cambi la posizione.  
  
2. Aggiunge un'animazione alla seconda <xref:System.Windows.Media.Matrix> a 1,0 secondi. Il pulsante si sposta in un'altra posizione mentre il pulsante non è più inclinato o allungato.  
  
3. Ripete l'animazione per un periodo illimitato.  
  
> [!NOTE]
> I fotogrammi chiave che derivano dall' <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> oggetto creano salti improvvisi tra i valori, ovvero lo spostamento dell'animazione è Jerky.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
