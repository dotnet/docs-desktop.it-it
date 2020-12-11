---
title: 'Procedura: Riempire figure aperte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: 6ecea7d3edb0c3e25fb4e69ff12b88019e530021
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962617"
---
# <a name="how-to-fill-open-figures"></a>Procedura: Riempire figure aperte
È possibile riempire un percorso passando un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto al <xref:System.Drawing.Graphics.FillPath%2A> metodo. Il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempie il percorso in base alla modalità di riempimento (alternativa o di avvolgimento) attualmente impostata per il percorso. Se il percorso contiene figure aperte, il percorso viene riempito come se tali figure fossero chiuse. GDI+ chiude una figura disegnando una linea retta dal punto finale al punto iniziale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un percorso con una figura aperta (un arco) e una figura chiusa (un'ellisse). Il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempie il percorso in base alla modalità di riempimento predefinita, ovvero <xref:System.Drawing.Drawing2D.FillMode.Alternate> .  
  
 Nella figura seguente viene illustrato l'output del codice di esempio. Si noti che il percorso viene riempito (in base a <xref:System.Drawing.Drawing2D.FillMode.Alternate> ) come se la figura aperta fosse chiusa da una linea retta dal punto finale al punto iniziale.  
  
 ![Diagramma che mostra l'output del metodo FillPath](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Percorsi di oggetti Graphics in GDI+](graphics-paths-in-gdi.md)
