---
title: Gestione dell'input dell'utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: a977061ab64dbecd5782645aa6929a77803b18c9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962167"
---
# <a name="handling-user-input"></a>Gestione dell'input dell'utente

In questo argomento vengono descritti gli eventi principali della tastiera e del mouse forniti da <xref:System.Windows.Forms.Control?displayProperty=nameWithType> . Quando si gestisce un evento, gli autori dei controlli devono eseguire l'override del metodo protetto `On`*EventName* anziché associare un delegato all'evento. Per una panoramica degli eventi, vedere [Generazione di eventi da un componente](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
> [!NOTE]
> Se non sono presenti dati associati a un evento, un'istanza della classe di base <xref:System.EventArgs> viene passata come argomento al `On` metodo *EventName* .  
  
## <a name="keyboard-events"></a>Eventi della tastiera  

 Gli eventi di tastiera comuni che il controllo è in grado di gestire sono <xref:System.Windows.Forms.Control.KeyDown> , <xref:System.Windows.Forms.Control.KeyPress> e <xref:System.Windows.Forms.Control.KeyUp> .  
  
|Nome evento|Metodo di cui eseguire l'override|Descrizione dell'evento|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Generato solo quando un tasto viene premuto inizialmente.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Generato ogni volta che un tasto viene premuto. Se un tasto viene mantenuto attivo, <xref:System.Windows.Forms.Control.KeyPress> viene generato un evento alla frequenza di ripetizione definita dal sistema operativo.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Viene generato quando un tasto viene rilasciato.|  
  
> [!NOTE]
> La gestione dell'input da tastiera è notevolmente più complessa dell'override degli eventi nella tabella precedente ed esula dall'ambito di questo argomento. Per altre informazioni, vedere [Input dell'utente in Windows Forms](../user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Eventi del mouse  

 Gli eventi del mouse che il controllo è in grado di gestire sono,,, <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseHover> <xref:System.Windows.Forms.Control.MouseLeave> , <xref:System.Windows.Forms.Control.MouseMove> e <xref:System.Windows.Forms.Control.MouseUp> .  
  
|Nome evento|Metodo di cui eseguire l'override|Descrizione dell'evento|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Viene generato quando il pulsante del mouse viene premuto mentre il puntatore si trova sopra il controllo.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Viene generato quando il puntatore del mouse entra nell'area del controllo.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Viene generato quando il puntatore è posizionato sul controllo.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Viene generato quando il puntatore esce dall'area del controllo.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Viene generato quando il puntatore si sposta nell'area del controllo.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Viene generato quando il pulsante del mouse viene rilasciato mentre il puntatore si trova sul controllo o il puntatore esce dall'area del controllo.|  
  
 Il frammento di codice seguente illustra un esempio di override dell' <xref:System.Windows.Forms.Control.MouseDown> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Il frammento di codice seguente illustra un esempio di override dell' <xref:System.Windows.Forms.Control.MouseMove> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Il frammento di codice seguente illustra un esempio di override dell' <xref:System.Windows.Forms.Control.MouseUp> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Per il codice sorgente completo dell'esempio `FlashTrackBar`, vedere [Procedura: Creare un controllo di Windows Forms che visualizzi lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="see-also"></a>Vedere anche

- [Eventi nei controlli di Windows Form](events-in-windows-forms-controls.md)
- [Definizione di un evento](defining-an-event-in-windows-forms-controls.md)
- [Eventi](/dotnet/standard/events/index)
- [Input dell'utente in Windows Form](../user-input-in-windows-forms.md)
