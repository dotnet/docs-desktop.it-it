---
title: 'Procedura: Applicare la correzione gamma a una sfumatura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960976"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Procedura: Applicare la correzione gamma a una sfumatura
È possibile abilitare la correzione gamma per un pennello sfumatura lineare impostando la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà del pennello su `true` . È possibile disabilitare la correzione gamma impostando la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà su `false` . Per impostazione predefinita, la correzione gamma è disabilitata.  
  
## <a name="example"></a>Esempio  

L'esempio seguente è un metodo chiamato dal gestore eventi di un controllo <xref:System.Windows.Forms.Control.Paint> . Nell'esempio viene creato un pennello sfumato lineare e tale pennello viene utilizzato per riempire due rettangoli. Il primo rettangolo viene riempito senza correzione gamma e il secondo rettangolo viene riempito con la correzione gamma.  
  
 Nella figura seguente sono illustrati i due rettangoli riempiti. Il rettangolo superiore, che non ha la correzione gamma, appare scuro al centro. Il rettangolo inferiore, con correzione gamma, sembra avere un'intensità più uniforme.  
  
 ![Due rettangoli riempiti da gradienti, con e senza correzione gamma.](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [Utilizzo di un pennello a sfumatura per il riempimento di forme](using-a-gradient-brush-to-fill-shapes.md)
