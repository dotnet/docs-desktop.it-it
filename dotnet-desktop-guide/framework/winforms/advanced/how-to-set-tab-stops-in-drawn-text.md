---
title: 'Procedura: Impostare tabulazioni nel testo disegnato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962530"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Procedura: Impostare tabulazioni nel testo disegnato
È possibile impostare le tabulazioni per il testo chiamando il <xref:System.Drawing.StringFormat.SetTabStops%2A> metodo di un <xref:System.Drawing.StringFormat> oggetto e passando <xref:System.Drawing.StringFormat> l'oggetto al <xref:System.Drawing.Graphics.DrawString%2A> metodo della <xref:System.Drawing.Graphics> classe.  
  
> [!NOTE]
> Non <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> supporta l'aggiunta di tabulazioni al testo disegnato, sebbene sia possibile espandere le tabulazioni esistenti utilizzando il <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono impostate le tabulazioni a 150, 250 e 350. Quindi, il codice visualizza un elenco a schede di nomi e punteggi dei test.  
  
 La figura seguente mostra il testo a schede:  
  
 ![Screenshot che mostra un elenco a schede di nomi e punteggi.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 Il codice seguente passa due argomenti al <xref:System.Drawing.StringFormat.SetTabStops%2A> metodo. Il secondo argomento è una matrice che contiene offset di tabulazione. Il primo argomento passato a <xref:System.Drawing.StringFormat.SetTabStops%2A> è 0, che indica che il primo offset nella matrice viene misurato dalla posizione 0, dal bordo sinistro del rettangolo di delimitazione.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
- [Procedura: Disegnare testo con GDI](how-to-draw-text-with-gdi.md)
