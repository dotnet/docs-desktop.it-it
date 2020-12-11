---
title: Puntatori del mouse
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: 4e8349effcd9b59045e39b763b4cb8b7d2fceb91
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965842"
---
# <a name="mouse-pointers-in-windows-forms"></a>Puntatori del mouse in Windows Form
Il *puntatore* del mouse, a volte indicato come cursore, è una bitmap che specifica un punto di interesse sullo schermo per l'input dell'utente con il mouse. In questo argomento viene fornita una panoramica del puntatore del mouse in Windows Forms e vengono descritti alcuni dei modi per modificare e controllare il puntatore del mouse.  
  
## <a name="accessing-the-mouse-pointer"></a>Accesso al puntatore del mouse  
 Il puntatore del mouse è rappresentato dalla <xref:System.Windows.Forms.Cursor> classe e ognuno <xref:System.Windows.Forms.Control> presenta una <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> proprietà che specifica il puntatore per il controllo. La <xref:System.Windows.Forms.Cursor> classe contiene proprietà che descrivono il puntatore, ad esempio <xref:System.Windows.Forms.Cursor.Position%2A> le <xref:System.Windows.Forms.Cursor.HotSpot%2A> proprietà e e i metodi che possono modificare l'aspetto del puntatore, ad esempio i <xref:System.Windows.Forms.Cursor.Show%2A> <xref:System.Windows.Forms.Cursor.Hide%2A> metodi, e <xref:System.Windows.Forms.Cursor.DrawStretched%2A> .  
  
## <a name="controlling-the-mouse-pointer"></a>Controllo del puntatore del mouse  
 In alcuni casi può essere opportuno limitare l'area in cui è possibile utilizzare il puntatore del mouse o modificare la posizione del mouse. È possibile ottenere o impostare la posizione corrente del mouse utilizzando la <xref:System.Windows.Forms.Cursor.Position%2A> proprietà dell'oggetto <xref:System.Windows.Forms.Cursor> . Inoltre, è possibile limitare l'area in cui è possibile utilizzare il puntatore del mouse per impostare la <xref:System.Windows.Forms.Cursor.Clip%2A> Proprietà. Per impostazione predefinita, l'area di ritaglio è l'intera schermata.  
  
## <a name="changing-the-mouse-pointer"></a>Modifica del puntatore del mouse  
 La modifica del puntatore del mouse è un modo importante per fornire commenti e suggerimenti all'utente. Il puntatore del mouse, ad esempio, può essere modificato nei gestori degli <xref:System.Windows.Forms.Control.MouseEnter> eventi e <xref:System.Windows.Forms.Control.MouseLeave> per indicare all'utente che i calcoli sono in corso e per limitare l'interazione dell'utente nel controllo. In alcuni casi, il puntatore del mouse verrà modificato a causa di eventi di sistema, ad esempio quando l'applicazione è in esecuzione in un'operazione di trascinamento della selezione.  
  
 Il modo principale per modificare il puntatore del mouse consiste nell'impostare <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> la <xref:System.Windows.Forms.Control.DefaultCursor%2A> proprietà o di un controllo su un nuovo oggetto <xref:System.Windows.Forms.Cursor> . Per esempi relativi alla modifica del puntatore del mouse, vedere l'esempio di codice nella <xref:System.Windows.Forms.Cursor> classe. Inoltre, la <xref:System.Windows.Forms.Cursors> classe espone un set di <xref:System.Windows.Forms.Cursor> oggetti per molti tipi diversi di puntatori, ad esempio un puntatore simile a una mano. Per visualizzare il puntatore di attesa, simile a una clessidra, ogni volta che il puntatore del mouse si trova sul controllo, utilizzare la <xref:System.Windows.Forms.Control.UseWaitCursor%2A> proprietà della <xref:System.Windows.Forms.Control> classe.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Cursor>
- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Funzionalità di trascinamento della selezione in Windows Form](drag-and-drop-functionality-in-windows-forms.md)
