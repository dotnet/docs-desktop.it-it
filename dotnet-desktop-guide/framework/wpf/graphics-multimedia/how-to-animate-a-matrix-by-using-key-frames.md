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
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="917c6-102">Procedura: animare una matrice utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="917c6-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="917c6-103">In questo esempio viene illustrato come animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un oggetto utilizzando <xref:System.Windows.Media.MatrixTransform> fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="917c6-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="917c6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="917c6-104">Example</span></span>  
 <span data-ttu-id="917c6-105">Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un oggetto <xref:System.Windows.Media.MatrixTransform> .</span><span class="sxs-lookup"><span data-stu-id="917c6-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="917c6-106">Nell'esempio viene utilizzato l' <xref:System.Windows.Media.MatrixTransform> oggetto per trasformare l'aspetto e la posizione di un oggetto <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="917c6-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="917c6-107">Questa animazione usa la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> classe per creare due fotogrammi chiave ed esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="917c6-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="917c6-108">Anima il primo <xref:System.Windows.Media.Matrix> durante i primi 0,2 secondi.</span><span class="sxs-lookup"><span data-stu-id="917c6-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="917c6-109">Nell'esempio vengono modificate <xref:System.Windows.Media.Matrix.M11%2A> le <xref:System.Windows.Media.Matrix.M12%2A> proprietà e di <xref:System.Windows.Media.Matrix> .</span><span class="sxs-lookup"><span data-stu-id="917c6-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="917c6-110">Questa modifica determina l'estensione del pulsante e la distorsione.</span><span class="sxs-lookup"><span data-stu-id="917c6-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="917c6-111">Nell'esempio vengono anche modificate <xref:System.Windows.Media.Matrix.OffsetX%2A> le <xref:System.Windows.Media.Matrix.OffsetY%2A> proprietà e in modo che il pulsante cambi la posizione.</span><span class="sxs-lookup"><span data-stu-id="917c6-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="917c6-112">Aggiunge un'animazione alla seconda <xref:System.Windows.Media.Matrix> a 1,0 secondi.</span><span class="sxs-lookup"><span data-stu-id="917c6-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="917c6-113">Il pulsante si sposta in un'altra posizione mentre il pulsante non è più inclinato o allungato.</span><span class="sxs-lookup"><span data-stu-id="917c6-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="917c6-114">Ripete l'animazione per un periodo illimitato.</span><span class="sxs-lookup"><span data-stu-id="917c6-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="917c6-115">I fotogrammi chiave che derivano dall' <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> oggetto creano salti improvvisi tra i valori, ovvero lo spostamento dell'animazione è Jerky.</span><span class="sxs-lookup"><span data-stu-id="917c6-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="917c6-116">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="917c6-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="917c6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="917c6-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="917c6-118">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="917c6-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="917c6-119">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="917c6-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
