---
title: Panoramica dei controlli HScrollBar e VScrollBar
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965143"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Cenni preliminari sui controlli HScrollBar e VScrollBar (Windows Form)
<xref:System.Windows.Forms.ScrollBar>I controlli Windows Forms vengono usati per semplificare la navigazione attraverso un lungo elenco di elementi o una grande quantità di informazioni scorrendo orizzontalmente o verticalmente all'interno di un'applicazione o di un controllo. Le barre di scorrimento sono un elemento comune dell'interfaccia di Windows, pertanto il <xref:System.Windows.Forms.ScrollBar> controllo viene spesso usato con controlli che non derivano dalla <xref:System.Windows.Forms.ScrollableControl> classe. Allo stesso modo, molti sviluppatori scelgono di incorporare il <xref:System.Windows.Forms.ScrollBar> controllo durante la creazione dei propri controlli utente.  
  
 I <xref:System.Windows.Forms.HScrollBar> controlli (orizzontali) e <xref:System.Windows.Forms.VScrollBar> (verticali) funzionano indipendentemente da altri controlli e hanno un proprio set di eventi, proprietà e metodi. <xref:System.Windows.Forms.ScrollBar> i controlli non sono uguali alle barre di scorrimento predefinite collegate a caselle di testo, caselle di riepilogo, caselle combinate o form MDI (il <xref:System.Windows.Forms.TextBox> controllo ha una proprietà che <xref:System.Windows.Forms.TextBox.ScrollBars%2A> consente di mostrare o nascondere le barre di scorrimento associate al controllo).  
  
 I <xref:System.Windows.Forms.ScrollBar> controlli utilizzano l' <xref:System.Windows.Forms.ScrollBar.Scroll> evento per monitorare lo spostamento della casella di scorrimento (talvolta definita cursore) lungo la barra di scorrimento. L'uso dell' <xref:System.Windows.Forms.ScrollBar.Scroll> evento consente di accedere al valore della barra di scorrimento mentre viene trascinato.  
  
## <a name="value-property"></a>Proprietà Value  
 La <xref:System.Windows.Forms.ScrollBar.Value%2A> proprietà, che per impostazione predefinita è 0, è un `integer` valore corrispondente alla posizione della casella di scorrimento nella barra di scorrimento. Quando la posizione della casella di scorrimento è impostata sul valore minimo, viene spostata nella posizione più a sinistra (per le barre di scorrimento orizzontali) o nella posizione superiore (per le barre di scorrimento verticali). Quando la casella di scorrimento è impostata sul valore massimo, la casella di scorrimento viene spostata nella posizione più a destra o in basso. Analogamente, un valore a metà tra la parte inferiore e la parte superiore dell'intervallo posiziona il bordo iniziale della casella di scorrimento al centro della barra di scorrimento.  
  
 Oltre a usare i clic del mouse per modificare il valore della barra di scorrimento, un utente può anche trascinare la casella di scorrimento in un punto lungo la barra. Il valore risultante dipende dalla posizione della casella di scorrimento, ma è sempre compreso nell'intervallo tra le <xref:System.Windows.Forms.ScrollBar.Minimum%2A> <xref:System.Windows.Forms.ScrollBar.Maximum%2A> proprietà e impostate dall'utente.  
  
## <a name="largechange-and-smallchange-properties"></a>Proprietà LargeChange e SmallChange  
 Quando l'utente preme il tasto PGSU o PGGIÙ o fa clic sull'indicatore di avanzamento della barra di scorrimento su entrambi i lati della casella di scorrimento, la <xref:System.Windows.Forms.ScrollBar.Value%2A> proprietà cambia in base al valore impostato nella <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> Proprietà.  
  
 Quando l'utente preme uno dei tasti di direzione o fa clic su uno dei pulsanti della barra di scorrimento, la <xref:System.Windows.Forms.ScrollBar.Value%2A> proprietà cambia in base al valore impostato nella <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> Proprietà.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
