---
title: 'Procedura: Usare il ritaglio per definire una regione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: e62be137b36a2f369c02151466154f6b3bab090b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962464"
---
# <a name="how-to-use-clipping-with-a-region"></a>Procedura: Usare il ritaglio per definire una regione
Una delle proprietà della <xref:System.Drawing.Graphics> classe è l'area di ritaglio. Tutti i disegni eseguiti da un determinato <xref:System.Drawing.Graphics> oggetto sono limitati all'area di ritaglio dell' <xref:System.Drawing.Graphics> oggetto. È possibile impostare l'area di ritaglio chiamando il <xref:System.Drawing.Graphics.SetClip%2A> metodo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un percorso costituito da un singolo poligono. Il codice costruisce quindi un'area in base a tale percorso. L'area viene passata al <xref:System.Drawing.Graphics.SetClip%2A> metodo di un <xref:System.Drawing.Graphics> oggetto, quindi vengono disegnate due stringhe.  
  
 Nella figura seguente sono illustrate le stringhe ritagliate:  
  
 ![Screenshot che mostra le stringhe ritagliate.](./media/how-to-use-clipping-with-a-region/clipped-strings-polygon.png)  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Regioni in GDI+](regions-in-gdi.md)
- [Utilizzo delle regioni](using-regions.md)
