---
title: Eventi per proprietà modificate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: 939972713ad95e9302c436268f4a6288a659ca6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965854"
---
# <a name="property-changed-events"></a>Eventi per proprietà modificate

Se si desidera che il controllo invii notifiche quando una proprietà denominata *PropertyName* viene modificata, definire un evento denominato *PropertyName* `Changed` e un metodo denominato `On` *PropertyName* `Changed` che genera l'evento. La convenzione di denominazione in Windows Forms consiste nell'accodare la parola *modificata* al nome della proprietà. Il tipo delegato di evento associato per gli eventi di modifica della proprietà è <xref:System.EventHandler> e il tipo di dati dell'evento è <xref:System.EventArgs> . La classe base <xref:System.Windows.Forms.Control> definisce molti eventi di modifica delle proprietà, ad esempio <xref:System.Windows.Forms.Control.BackColorChanged> ,, <xref:System.Windows.Forms.Control.BackgroundImageChanged> <xref:System.Windows.Forms.Control.FontChanged> , <xref:System.Windows.Forms.Control.LocationChanged> e altri. Per informazioni generali sugli eventi, vedere [eventi](/dotnet/standard/events/index) ed [eventi in controlli Windows Forms](events-in-windows-forms-controls.md).  
  
 Gli eventi di modifica delle proprietà sono utili perché consentono ai consumer di un controllo di alleghi gestori eventi che rispondono alla modifica. Se il controllo deve rispondere a un evento di modifica della proprietà che genera, eseguire l'override del `On` metodo *PropertyName* corrispondente `Changed` invece di allegare un delegato all'evento. Un controllo in genere risponde a un evento di modifica della proprietà aggiornando altre proprietà o ridisegnando parte o tutta la relativa superficie di disegno.  
  
 Nell'esempio seguente viene illustrato il modo in cui il `FlashTrackBar` controllo personalizzato risponde ad alcuni eventi di modifica della proprietà da cui eredita <xref:System.Windows.Forms.Control> . Per l'esempio completo, vedere [procedura: creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](/dotnet/standard/events/index)
- [Eventi nei controlli di Windows Form](events-in-windows-forms-controls.md)
- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
