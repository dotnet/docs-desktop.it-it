---
title: 'Procedura: Visualizzare schede allineate lateralmente con TabControl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
ms.openlocfilehash: d98c5906d99dff9371f8290e7dbc9c9011cd0c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961840"
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a>Procedura: Visualizzare schede allineate lateralmente con TabControl
La proprietà <xref:System.Windows.Forms.TabControl.Alignment%2A> di <xref:System.Windows.Forms.TabControl> supporta la visualizzazione di schede in verticale (lungo il bordo sinistro o destro del controllo) anziché in orizzontale (lungo la parte superiore o inferiore del controllo). Per impostazione predefinita, questa visualizzazione verticale comporta un'esperienza utente non soddisfacente, perché la proprietà <xref:System.Windows.Forms.TabPage.Text%2A> dell'oggetto <xref:System.Windows.Forms.TabPage> non viene visualizzata nella scheda quando sono abilitati gli stili visivi. Non esiste inoltre alcun modo diretto per controllare la direzione del testo all'interno della scheda. <xref:System.Windows.Forms.TabControl> Per migliorare questa esperienza, è possibile usare Owner Draw on.  
  
 La procedura seguente mostra come eseguire il rendering di schede allineate a destra, con il testo della scheda visualizzato da sinistra a destra, usando la funzionalità "Owner Draw".  
  
### <a name="to-display-right-aligned-tabs"></a>Per visualizzare le schede allineate a destra  
  
1. Aggiungere un oggetto <xref:System.Windows.Forms.TabControl> al form.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.TabControl.Alignment%2A> su <xref:System.Windows.Forms.TabAlignment.Right>.  
  
3. Impostare la proprietà <xref:System.Windows.Forms.TabControl.SizeMode%2A> su <xref:System.Windows.Forms.TabSizeMode.Fixed> in modo che tutte le schede siano della stessa larghezza.  
  
4. Impostare la proprietà <xref:System.Windows.Forms.TabControl.ItemSize%2A> sulle dimensioni fisse preferite per le schede. Tenere presente che la proprietà <xref:System.Windows.Forms.TabControl.ItemSize%2A> si comporta come se le schede si trovassero nella parte superiore, sebbene siano allineate a destra. Di conseguenza, per aumentare la larghezza delle schede, è necessario modificare la proprietà <xref:System.Drawing.Size.Height%2A> mentre, per aumentarne l'altezza, è necessario modificare la proprietà <xref:System.Drawing.Size.Width%2A>.  
  
     Per ottenere risultati migliori con l'esempio di codice riportato di seguito, impostare <xref:System.Drawing.Size.Width%2A> delle schede su 25 e <xref:System.Drawing.Size.Height%2A> su 100.  
  
5. Impostare la proprietà <xref:System.Windows.Forms.TabControl.DrawMode%2A> su <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.  
  
6. Definire un gestore per l'evento <xref:System.Windows.Forms.TabControl.DrawItem> di <xref:System.Windows.Forms.TabControl> che esegue il rendering del testo da sinistra a destra.  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](~/samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TabControl](tabcontrol-control-windows-forms.md)
