---
title: 'Procedura: Riempire una forma con un colore a tinta unita'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962614"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>Procedura: Riempire una forma con un colore a tinta unita
Per riempire una forma con un colore a tinta unita, creare un <xref:System.Drawing.SolidBrush> oggetto e quindi passare l' <xref:System.Drawing.SolidBrush> oggetto come argomento a uno dei metodi Fill della <xref:System.Drawing.Graphics> classe. Nell'esempio seguente viene illustrato come riempire un'ellisse con il colore rosso.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente, il <xref:System.Drawing.SolidBrush.%23ctor%2A> costruttore accetta un <xref:System.Drawing.Color> oggetto come unico argomento. I valori utilizzati dal <xref:System.Drawing.Color.FromArgb%2A> Metodo rappresentano i componenti alfa, rosso, verde e blu del colore. Ognuno di questi valori deve essere compreso tra 0 e 255. Il primo 255 indica che il colore è completamente opaco e il secondo 255 indica che il componente rosso è a intensità piena. I due zeri indicano che i componenti verde e blu hanno un'intensità pari a 0.  
  
 I quattro numeri (0, 0, 100, 60) passati al <xref:System.Drawing.Graphics.FillEllipse%2A> Metodo specificano la posizione e le dimensioni del rettangolo di delimitazione per l'ellisse. Il rettangolo ha un angolo superiore sinistro di (0,0), una larghezza di 100 e un'altezza di 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
