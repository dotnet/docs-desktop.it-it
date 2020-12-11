---
title: 'Procedura: utilizzare un MatrixTransform per creare trasformazioni personalizzate'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967669"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="cf1a7-102">Procedura: utilizzare un MatrixTransform per creare trasformazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="cf1a7-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="cf1a7-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.MatrixTransform> per tradurre (spostare) la posizione, l'estensione e l'inclinazione di un oggetto <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="cf1a7-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf1a7-104">Utilizzare la <xref:System.Windows.Media.MatrixTransform> classe per creare trasformazioni personalizzate che non sono fornite dalle <xref:System.Windows.Media.RotateTransform> classi, <xref:System.Windows.Media.SkewTransform> , <xref:System.Windows.Media.ScaleTransform> o <xref:System.Windows.Media.TranslateTransform> .</span><span class="sxs-lookup"><span data-stu-id="cf1a7-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf1a7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf1a7-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="cf1a7-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf1a7-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="cf1a7-107">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="cf1a7-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="cf1a7-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="cf1a7-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="cf1a7-109">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="cf1a7-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
