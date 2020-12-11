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
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Procedura: utilizzare un MatrixTransform per creare trasformazioni personalizzate
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.MatrixTransform> per tradurre (spostare) la posizione, l'estensione e l'inclinazione di un oggetto <xref:System.Windows.Controls.Button> .  
  
> [!NOTE]
> Utilizzare la <xref:System.Windows.Media.MatrixTransform> classe per creare trasformazioni personalizzate che non sono fornite dalle <xref:System.Windows.Media.RotateTransform> classi, <xref:System.Windows.Media.SkewTransform> , <xref:System.Windows.Media.ScaleTransform> o <xref:System.Windows.Media.TranslateTransform> .  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure](transformations-how-to-topics.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
