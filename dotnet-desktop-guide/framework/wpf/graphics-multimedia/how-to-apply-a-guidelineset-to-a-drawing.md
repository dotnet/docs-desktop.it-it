---
title: 'Procedura: applicare un GuidelineSet a un disegno'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 134236c5beca806b747d45f20764cc82ddd8a4e8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968476"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Procedura: applicare un GuidelineSet a un disegno
Questo esempio illustra come applicare un oggetto <xref:System.Windows.Media.GuidelineSet> a un oggetto <xref:System.Windows.Media.DrawingGroup> .  
  
 La <xref:System.Windows.Media.DrawingGroup> classe è l'unico tipo di <xref:System.Windows.Media.Drawing> che dispone di una <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> Proprietà. Per applicare un oggetto <xref:System.Windows.Media.GuidelineSet> a un altro tipo di <xref:System.Windows.Media.Drawing> , aggiungerlo a un oggetto <xref:System.Windows.Media.DrawingGroup> e quindi applicare al <xref:System.Windows.Media.GuidelineSet> <xref:System.Windows.Media.DrawingGroup> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati due <xref:System.Windows.Media.DrawingGroup> oggetti che sono quasi identici. l'unica differenza è: il secondo <xref:System.Windows.Media.DrawingGroup> ha un oggetto <xref:System.Windows.Media.GuidelineSet> e il primo non lo è.  
  
 L'immagine seguente illustra l'output dell'esempio. Poiché la differenza di rendering tra i due <xref:System.Windows.Media.DrawingGroup> oggetti è così sottile, le parti dei disegni vengono ingrandite.  
  
 ![DrawingGroup con e senza GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
