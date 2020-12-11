---
title: Eventi nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 27edaf2d895453d64d35ba6eff724df583a9b7dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962194"
---
# <a name="events-in-windows-forms-controls"></a>Eventi nei controlli di Windows Form

Un controllo Windows Forms eredita più di 60 eventi da <xref:System.Windows.Forms.Control?displayProperty=nameWithType> . Che includono l' <xref:System.Windows.Forms.Control.Paint> evento, che determina la visualizzazione di un controllo, gli eventi correlati alla visualizzazione di una finestra, ad esempio gli eventi <xref:System.Windows.Forms.Control.Resize> e e <xref:System.Windows.Forms.Control.Layout> gli eventi di mouse e tastiera di basso livello. Alcuni eventi di basso livello vengono sintetizzati <xref:System.Windows.Forms.Control> in eventi semantici, ad esempio <xref:System.Windows.Forms.Control.Click> e <xref:System.Windows.Forms.Control.DoubleClick> . Per informazioni dettagliate sugli eventi ereditati, vedere <xref:System.Windows.Forms.Control> .  
  
 Se è necessario eseguire l'override del controllo personalizzato sulle funzionalità di eventi ereditati, eseguire l'override del metodo `On`*EventName* ereditato anziché associare un delegato. Se non si ha familiarità con il modello di eventi in .NET Framework, vedere [Generazione di eventi da un componente](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
## <a name="see-also"></a>Vedere anche

- [Override del metodo OnPaint](overriding-the-onpaint-method.md)
- [Gestione dell'input dell'utente](handling-user-input.md)
- [Definizione di un evento](defining-an-event-in-windows-forms-controls.md)
- [Eventi](/dotnet/standard/events/index)
