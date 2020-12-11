---
title: "Procedura: Abilitare il tasto TAB per l'uscita da un controllo ToolStrip"
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 7fee9f685b9a9b402cbfe9c265669f7905434986
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961804"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Procedura: Abilitare il tasto TAB per l'uscita da un controllo ToolStrip
Utilizzare la procedura seguente per consentire all'utente di premere il tasto TAB per spostarsi da un <xref:System.Windows.Forms.ToolStrip> al controllo successivo nell'ordine di tabulazione.  
  
 <xref:System.Windows.Forms.ToolStrip>Accetta la prima pressione del tasto TAB e i tasti di direzione selezionano gli elementi all'interno di <xref:System.Windows.Forms.ToolStrip> . Quando l'utente preme il tasto TAB una seconda volta, porta l'utente al controllo successivo nell'ordine di tabulazione.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Per consentire all'utente di premere il tasto TAB per spostarsi da un ToolStrip al controllo successivo  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.TabStop%2A> di <xref:System.Windows.Forms.ToolStrip> su `true`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
