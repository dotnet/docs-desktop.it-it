---
title: Limitazione della superficie di disegno in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963094"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>Limitazione della superficie di disegno in GDI+
Il ritaglio comporta la limitazione del disegno a un determinato rettangolo o area. La figura seguente mostra la stringa "Hello" ritagliata in un'area a forma di cuore.  
  
 ![Superficie di disegno limitata](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>Ritaglio con aree  
 Le aree possono essere costruite da percorsi e i percorsi possono contenere le strutture delle stringhe, quindi è possibile usare il testo delineato per il ritaglio. Nella figura seguente viene illustrato un set di ellissi concentrici ritagliati all'interno di una stringa di testo.  
  
 ![Superficie di disegno limitata](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 Per disegnare con il ritaglio, creare un <xref:System.Drawing.Graphics> oggetto, impostarne la <xref:System.Drawing.Graphics.Clip%2A> proprietà e quindi chiamare i metodi di disegno dello stesso <xref:System.Drawing.Graphics> oggetto:  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Utilizzo delle regioni](using-regions.md)
