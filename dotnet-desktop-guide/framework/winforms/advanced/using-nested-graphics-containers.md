---
title: Utilizzo di contenitori di grafica annidati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: 460ebb37ee62691a1e282f756840121fd378ebd8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962392"
---
# <a name="using-nested-graphics-containers"></a>Utilizzo di contenitori di grafica annidati
GDI+ fornisce contenitori che è possibile utilizzare per sostituire temporaneamente o aumentare parte dello stato di un <xref:System.Drawing.Graphics> oggetto. Per creare un contenitore, chiamare il <xref:System.Drawing.Graphics.BeginContainer%2A> metodo di un <xref:System.Drawing.Graphics> oggetto. È possibile chiamare <xref:System.Drawing.Graphics.BeginContainer%2A> ripetutamente per creare contenitori nidificati. Ogni chiamata a <xref:System.Drawing.Graphics.BeginContainer%2A> deve essere abbinata a una chiamata a <xref:System.Drawing.Graphics.EndContainer%2A> .  
  
## <a name="transformations-in-nested-containers"></a>Trasformazioni nei contenitori annidati  
 Nell'esempio seguente vengono creati un <xref:System.Drawing.Graphics> oggetto e un contenitore all'interno di tale <xref:System.Drawing.Graphics> oggetto. La trasformazione globale dell' <xref:System.Drawing.Graphics> oggetto è una conversione di unità 100 nella direzione x e 80 unità nella direzione y. La trasformazione globale del contenitore è una rotazione di 30 gradi. Il codice effettua la chiamata `DrawRectangle(pen, -60, -30, 120, 60)` due volte. La prima chiamata a <xref:System.Drawing.Graphics.DrawRectangle%2A> si trova all'interno del contenitore, ovvero la chiamata è tra le chiamate a <xref:System.Drawing.Graphics.BeginContainer%2A> e <xref:System.Drawing.Graphics.EndContainer%2A> . La seconda chiamata a <xref:System.Drawing.Graphics.DrawRectangle%2A> è successiva alla chiamata a <xref:System.Drawing.Graphics.EndContainer%2A> .  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 Nel codice precedente, il rettangolo disegnato dall'interno del contenitore viene trasformato prima dalla trasformazione globale del contenitore (rotazione), quindi dalla trasformazione globale dell' <xref:System.Drawing.Graphics> oggetto (traduzione). Il rettangolo disegnato dall'esterno del contenitore viene trasformato solo dalla trasformazione globale dell' <xref:System.Drawing.Graphics> oggetto (traduzione). Nella figura seguente sono illustrati i due rettangoli seguenti:
  
 ![Illustrazione che mostra i contenitori nidificati.](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>Ritaglio in contenitori annidati  
 Nell'esempio seguente viene illustrato come i contenitori annidati gestiscono le aree di ritaglio. Il codice crea un <xref:System.Drawing.Graphics> oggetto e un contenitore all'interno dell' <xref:System.Drawing.Graphics> oggetto. L'area di visualizzazione dell' <xref:System.Drawing.Graphics> oggetto è un rettangolo e l'area di visualizzazione del contenitore è un'ellisse. Il codice effettua due chiamate al <xref:System.Drawing.Graphics.DrawLine%2A> metodo. La prima chiamata a <xref:System.Drawing.Graphics.DrawLine%2A> si trova all'interno del contenitore e la seconda chiamata a <xref:System.Drawing.Graphics.DrawLine%2A> è esterna al contenitore, dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A> . La prima riga viene ritagliata dall'intersezione delle due aree di ritaglio. La seconda riga viene troncata solo dall'area di ridimensionamento rettangolare dell' <xref:System.Drawing.Graphics> oggetto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 Nella figura seguente sono illustrate le due righe ritagliate:
  
 ![Illustrazione che mostra un contenitore annidato con linee ritagliate.](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 Come illustrato nei due esempi precedenti, le trasformazioni e le aree di ridimensionamento sono cumulative nei contenitori nidificati. Se si impostano le trasformazioni globali del contenitore e dell' <xref:System.Drawing.Graphics> oggetto, entrambe le trasformazioni verranno applicate agli elementi disegnati dall'interno del contenitore. La trasformazione del contenitore verrà applicata per prima e la trasformazione dell' <xref:System.Drawing.Graphics> oggetto verrà applicata secondo. Se si impostano le aree di visualizzazione del contenitore e l' <xref:System.Drawing.Graphics> oggetto, gli elementi disegnati dall'interno del contenitore verranno ritagliati dall'intersezione delle due aree di ridimensionamento.  
  
## <a name="quality-settings-in-nested-containers"></a>Impostazioni di qualità nei contenitori annidati  
 Le impostazioni di qualità ( <xref:System.Drawing.Graphics.SmoothingMode%2A> , <xref:System.Drawing.Graphics.TextRenderingHint%2A> e simili) nei contenitori annidati non sono cumulative, bensì le impostazioni di qualità del contenitore sostituiscono temporaneamente le impostazioni di qualità di un <xref:System.Drawing.Graphics> oggetto. Quando si crea un nuovo contenitore, le impostazioni di qualità per il contenitore sono impostate sui valori predefiniti. Si supponga, ad esempio, di avere un <xref:System.Drawing.Graphics> oggetto con modalità di smussatura <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> . Quando si crea un contenitore, la modalità di smussatura all'interno del contenitore è la modalità di smussatura predefinita. È possibile impostare la modalità di smussatura del contenitore e tutti gli elementi disegnati dall'interno del contenitore verranno disegnati in base alla modalità impostata. Gli elementi disegnati dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A> verranno disegnati in base alla modalità di smussatura ( <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> ) che era presente prima della chiamata a <xref:System.Drawing.Graphics.BeginContainer%2A> .  
  
## <a name="several-layers-of-nested-containers"></a>Diversi livelli di contenitori annidati  
 Non si è limitati a un contenitore in un <xref:System.Drawing.Graphics> oggetto. È possibile creare una sequenza di contenitori, ognuno nidificato nell'oggetto precedente, ed è possibile specificare la trasformazione globale, l'area di ridimensionamento e le impostazioni di qualità di ognuno di questi contenitori annidati. Se si chiama un metodo Drawing dall'interno del contenitore più interno, le trasformazioni verranno applicate in ordine, a partire dal contenitore più interno e terminando con il contenitore più esterno. Gli elementi disegnati dall'interno del contenitore più interno verranno ritagliati dall'intersezione di tutte le aree di ridimensionamento.  
  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Graphics> oggetto e ne viene impostato l'hint per il rendering del testo su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> . Il codice crea due contenitori, uno annidato all'interno dell'altro. L'hint per il rendering del testo del contenitore esterno è impostato su <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel> e l'hint per il rendering del testo del contenitore interno è impostato su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> . Il codice disegna tre stringhe: una dal contenitore interno, una dal contenitore esterno e una dall' <xref:System.Drawing.Graphics> oggetto stesso.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 Nella figura seguente sono illustrate le tre stringhe. Le stringhe tratte dal contenitore interno e dall' <xref:System.Drawing.Graphics> oggetto sono smussate dall'anti-aliasing. La stringa disegnata dal contenitore esterno non è smussata mediante l'anti-aliasing, perché la <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà è impostata su <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel> .  
  
 ![Illustrazione che mostra le stringhe tracciate dai contenitori nidificati.](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics>
- [Gestione dello stato di un oggetto Graphics](managing-the-state-of-a-graphics-object.md)
