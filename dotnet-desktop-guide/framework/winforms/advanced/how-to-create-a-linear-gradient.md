---
title: 'Procedura: Creare una sfumatura lineare'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e55d27b454579268658192ae56daa52e0b28bb83
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952397"
---
# <a name="how-to-create-a-linear-gradient"></a>Procedura: Creare una sfumatura lineare
GDI+ fornisce gradienti lineari orizzontali, verticali e diagonali. Per impostazione predefinita, il colore in una sfumatura lineare cambia in modo uniforme. Tuttavia, è possibile personalizzare una sfumatura lineare in modo che il colore cambi in modo non uniforme.  

> [!NOTE]
> Gli esempi in questo articolo sono metodi che vengono chiamati dal gestore eventi di un controllo <xref:System.Windows.Forms.Control.Paint> .  

Nell'esempio seguente vengono riempite una riga, un'ellisse e un rettangolo con un pennello sfumato lineare orizzontale.  
  
Il <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore riceve quattro argomenti: due punti e due colori. Il primo punto (0, 10) è associato al primo colore (rosso) e il secondo punto (200, 10) viene associato al secondo colore (blu). Come ci si aspetterebbe, la linea disegnata da (0, 10) a (200, 10) cambia gradualmente da rosso a blu.  
  
 I 10s nei punti (0, 10) e (200, 10) non sono importanti. Ciò che è importante è che i due punti hanno la stessa seconda coordinata, ovvero la linea che la connette è orizzontale. Anche l'ellisse e il rettangolo cambiano gradualmente da rosso a blu, perché la coordinata orizzontale va da 0 a 200.  
  
 La figura seguente mostra la riga, l'ellisse e il rettangolo. Si noti che la sfumatura di colore si ripete quando la coordinata orizzontale aumenta oltre 200.  
  
 ![Una linea, un'ellisse e un rettangolo riempiti con una sfumatura di colore.](./media/how-to-create-a-linear-gradient/gradient-line-ellipse-rectangle.png)  
  
## <a name="to-use-horizontal-linear-gradients"></a>Per utilizzare sfumature lineari orizzontali  
  
- Passare rispettivamente il rosso opaco e il blu opaco come terzo e quarto argomento.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 Nell'esempio precedente, i componenti dei colori cambiano in modo lineare quando si passa da una coordinata orizzontale di 0 a una coordinata orizzontale di 200. Ad esempio, un punto la cui prima coordinata è a metà tra 0 e 200 avrà un componente blu a metà tra 0 e 255.  
  
 GDI+ consente di modificare il modo in cui un colore varia da un bordo di una sfumatura all'altro. Si supponga di voler creare un pennello sfumato che cambi da nero a rosso in base alla tabella seguente.  
  
|Coordinata orizzontale|Componenti RGB|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 Si noti che il componente rosso è a metà intensità quando la coordinata orizzontale è solo il 20% della strada da 0 a 200.  
  
 Nell'esempio seguente viene impostata la <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> proprietà per associare tre intensità relative con tre posizioni relative. Come nella tabella precedente, un'intensità relativa di 0,5 è associata a una posizione relativa di 0,2. Il codice riempie un'ellisse e un rettangolo con il pennello sfumatura.  
  
 Nella figura seguente vengono illustrati l'ellisse e il rettangolo risultanti.  
  
 ![Ellisse e rettangolo riempiti con una sfumatura di colore orizzontale.](./media/how-to-create-a-linear-gradient/gradient-ellipse-rectangle.png)  

## <a name="to-customize-linear-gradients"></a>Per personalizzare le sfumature lineari  
  
- Passare rispettivamente il nero opaco e il rosso opaco come terzo e quarto argomento.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Le sfumature degli esempi precedenti sono state orizzontali; ovvero il colore cambia gradualmente man mano che si sposta lungo una linea orizzontale. È anche possibile definire sfumature verticali e sfumature diagonali.  
  
 Nell'esempio seguente vengono passati i punti (0, 0) e (200, 100) a un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore. Il colore blu è associato a (0, 0) e il colore verde è associato a (200, 100). Una linea (con larghezza della penna 10) e un'ellisse vengono riempite con il pennello sfumatura lineare.  
  
 La figura seguente mostra la riga e l'ellisse. Si noti che il colore nell'ellisse cambia gradualmente man mano che si sposta lungo ogni riga che è parallela alla riga che attraversa (0,0) e (200, 100).  
  
 ![Una linea e un'ellisse riempite con una sfumatura di colore diagonale.](./media/how-to-create-a-linear-gradient/gradient-line-ellipse.png)  
  
## <a name="to-create-diagonal-linear-gradients"></a>Per creare sfumature lineari diagonali  
  
- Passare rispettivamente il blu opaco e il verde opaco come terzo e quarto argomento.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di un pennello a sfumatura per il riempimento di forme](using-a-gradient-brush-to-fill-shapes.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
