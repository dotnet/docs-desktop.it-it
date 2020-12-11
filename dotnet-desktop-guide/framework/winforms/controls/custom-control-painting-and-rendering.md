---
title: Disegno e rendering di controlli personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 14abac5678bfffa3cdb61307fd3cb54681c82a99
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951130"
---
# <a name="custom-control-painting-and-rendering"></a>Disegno e rendering di controlli personalizzati
Il disegno personalizzato dei controlli è una delle numerose attività complesse semplificate dal .NET Framework. Quando si crea un controllo personalizzato, sono disponibili molte opzioni relative all'aspetto grafico del controllo. Se si crea un controllo che eredita da `Control` , è necessario fornire il codice che consente al controllo di eseguire il rendering della relativa rappresentazione grafica. Se si sta creando un controllo utente ereditando da `UserControl` o ereditando da uno dei controlli di Windows Forms, è possibile eseguire l'override della rappresentazione grafica standard e fornire il proprio codice grafico. Se si desidera fornire il rendering personalizzato per i controlli costitutivi di un oggetto `UserControl` che si sta creando, le opzioni diventano più limitate, ma consentono comunque un'ampia gamma di possibilità grafiche per i controlli e le applicazioni.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Rendering di un controllo Windows Form](rendering-a-windows-forms-control.md)  
 Viene illustrato come programmare la logica che visualizza un controllo.  
  
 [Controlli creati dall'utente](user-drawn-controls.md)  
 Fornisce una panoramica dei passaggi necessari per scrivere ed eseguire l'override del codice di rendering per il controllo.  
  
 [Controlli costitutivi](constituent-controls.md)  
 Viene descritto come implementare il codice di rendering personalizzato per i controlli costitutivi nei form e nei controlli utente.  
  
 [Procedura: Rendere invisibile il controllo in fase di esecuzione](how-to-make-your-control-invisible-at-run-time.md)  
 Viene illustrato come utilizzare la <xref:System.Windows.Forms.Control.Visible%2A> proprietà per nascondere e visualizzare un controllo.  
  
 [Procedura: Assegnare uno sfondo trasparente al controllo](how-to-give-your-control-a-transparent-background.md)  
 Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per creare un colore di sfondo opaco, trasparente o parzialmente trasparente.  
  
 [Rendering dei controlli con stili visivi](rendering-controls-with-visual-styles.md)  
 Viene illustrato come eseguire il rendering dei controlli utilizzando gli stili di visualizzazione nei sistemi operativi che li supportano.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Windows.Forms.Control>  
 Descrive la classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.UserControl>  
 Descrive la classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Descrive questo metodo.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Creare oggetti Graphics per disegnare](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 Introduce la funzionalità grafica GDI+ dal punto di vista di Visual Studio e fornisce collegamenti ad altre informazioni.  
  
 [Tipi di controlli personalizzati](varieties-of-custom-controls.md)  
 Descrive i tipi di controlli personalizzati che è possibile creare.
