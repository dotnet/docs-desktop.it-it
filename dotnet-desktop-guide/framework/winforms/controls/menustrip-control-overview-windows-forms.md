---
title: Panoramica del controllo MenuStrip
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965044"
---
# <a name="menustrip-control-overview-windows-forms"></a>Cenni preliminari sul controllo MenuStrip (Windows Form)
I menu espongono le funzionalità agli utenti con i comandi raggruppati in base a un tema comune.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo è stato introdotto nella versione 2,0 del .NET Framework. Con il <xref:System.Windows.Forms.MenuStrip> controllo è possibile creare facilmente menu come quelli disponibili in Microsoft Office.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo supporta l'interfaccia a documenti multipli (MDI) e l'Unione di menu, le descrizioni comandi e l'overflow. È possibile migliorare l'usabilità e la leggibilità dei menu aggiungendo chiavi di accesso, tasti di scelta rapida, segni di spunta, immagini e barre dei separatori.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo sostituisce e aggiunge funzionalità al <xref:System.Windows.Forms.MainMenu> controllo; tuttavia, il <xref:System.Windows.Forms.MainMenu> controllo viene mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se lo si sceglie.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Modalità di utilizzo del controllo MenuStrip  
 Usare il <xref:System.Windows.Forms.MenuStrip> controllo per:  
  
- Consente di creare menu facilmente personalizzati e di uso comune che supportano funzionalità avanzate di interfaccia utente e layout, ad esempio ordinamento e allineamento di testo e immagini, operazioni di trascinamento della selezione, MDI, overflow e modalità alternative di accesso ai comandi di menu.  
  
- Supportare l'aspetto e il comportamento tipici del sistema operativo.  
  
- Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo in cui si gestiscono gli eventi per altri controlli.  
  
 Nella tabella seguente vengono illustrate alcune proprietà particolarmente importanti di <xref:System.Windows.Forms.MenuStrip> e delle classi associate.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Ottiene o imposta l'oggetto <xref:System.Windows.Forms.ToolStripMenuItem> utilizzato per visualizzare un elenco di form figlio MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Ottiene o imposta il modo in cui i menu figlio vengono uniti ai menu padre nelle applicazioni MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Ottiene o imposta la posizione di un elemento unito all'interno di un menu in applicazioni MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Ottiene o imposta un valore che indica se il form è un contenitore per form figlio MDI.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Ottiene o imposta un valore che indica se vengono visualizzate le descrizioni comandi per <xref:System.Windows.Forms.MenuStrip> .|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.MenuStrip> supporta la funzionalità di overflow.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Ottiene o imposta i tasti di scelta rapida associati alla classe <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Ottiene o imposta un valore che indica se i tasti di scelta rapida associati alla classe <xref:System.Windows.Forms.ToolStripMenuItem> sono visualizzati accanto alla classe <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 Nella tabella seguente vengono illustrate le principali <xref:System.Windows.Forms.MenuStrip> classi complementari.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Rappresenta un'opzione selezionabile visualizzata in un oggetto <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Viene visualizzato un menu di scelta rapida.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco visualizzato quando l'utente fa clic su <xref:System.Windows.Forms.ToolStripDropDownButton> o su una voce di menu di livello superiore.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Fornisce la funzionalità di base per i controlli derivati da <xref:System.Windows.Forms.ToolStripItem> che visualizzano gli elementi a discesa quando vengono selezionate.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
