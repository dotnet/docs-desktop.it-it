---
title: Panoramica del controllo ToolStrip
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966586"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Cenni preliminari sul controllo ToolStrip (Windows Form)
Il <xref:System.Windows.Forms.ToolStrip> controllo Windows Forms e le classi associate forniscono un Framework comune per combinare gli elementi dell'interfaccia utente nelle barre degli strumenti, nelle barre di stato e nei menu. <xref:System.Windows.Forms.ToolStrip> i controlli offrono un'esperienza avanzata in fase di progettazione che include l'attivazione e la modifica sul posto, il layout personalizzato e il rafting, ovvero la capacità delle barre degli strumenti di condividere lo spazio orizzontale o verticale.  
  
 Anche se <xref:System.Windows.Forms.ToolStrip> sostituisce e aggiunge funzionalità al controllo nelle versioni precedenti, viene mantenuto sia per la compatibilità con le versioni precedenti <xref:System.Windows.Forms.ToolBar> che per un uso futuro, se lo si desidera.  
  
## <a name="features-of-the-toolstrip-controls"></a>Funzionalità dei controlli ToolStrip  
 Usare il <xref:System.Windows.Forms.ToolStrip> controllo per:  
  
- Presentare un'interfaccia utente comune tra i contenitori.  
  
- Creazione di barre degli strumenti facilmente personalizzabili e di uso comune che supportano interfacce utente e funzionalità di layout avanzate, ad esempio l'ancoraggio, il raggruppamento di pulsanti, i pulsanti con testo e immagini, i pulsanti e i controlli a discesa, i pulsanti di overflow e il riordinamento degli elementi in fase di esecuzione <xref:System.Windows.Forms.ToolStrip> .  
  
- Supporto dell'overflow e riordinamento degli elementi in fase di esecuzione. La funzionalità di overflow sposta gli elementi in un menu a discesa quando lo spazio disponibile non è sufficiente per visualizzarli in un <xref:System.Windows.Forms.ToolStrip> .  
  
- Supportare l'aspetto e il comportamento tipici del sistema operativo tramite un modello di rendering comune.  
  
- Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo in cui si gestiscono gli eventi per altri controlli.  
  
- Trascinare gli elementi da un <xref:System.Windows.Forms.ToolStrip> oggetto a un altro o all'interno di un <xref:System.Windows.Forms.ToolStrip> .  
  
- Creare controlli a discesa e editor di tipi di interfaccia utente con layout avanzati in un <xref:System.Windows.Forms.ToolStripDropDown> .  
  
 Utilizzare la <xref:System.Windows.Forms.ToolStripControlHost> classe per utilizzare altri controlli in un oggetto <xref:System.Windows.Forms.ToolStrip> e ottenere le <xref:System.Windows.Forms.ToolStrip> relative funzionalità.  
  
 È possibile estendere la funzionalità e modificare l'aspetto e il comportamento usando <xref:System.Windows.Forms.ToolStripRenderer> , <xref:System.Windows.Forms.ToolStripProfessionalRenderer> e insieme alle <xref:System.Windows.Forms.ToolStripManager> <xref:System.Windows.Forms.ToolStripRenderMode> <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerazioni e.  
  
 Il <xref:System.Windows.Forms.ToolStrip> controllo è altamente configurabile ed estendibile e fornisce molte proprietà, metodi ed eventi per personalizzare l'aspetto e il comportamento. Di seguito sono riportati alcuni membri degni di Nota:  
  
### <a name="important-toolstrip-members"></a>Membri ToolStrip importanti  
  
|Name|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Ottiene o imposta il bordo del contenitore padre a <xref:System.Windows.Forms.ToolStrip> a cui è ancorato.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Ottiene o imposta un valore che indica se le operazioni di trascinamento e rilascio e ridisposizione degli elementi devono essere gestite privatamente dalla classe <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Ottiene o imposta un valore che indica il modo in <xref:System.Windows.Forms.ToolStrip> cui definisce gli elementi.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Ottiene o imposta un valore che indica se un oggetto <xref:System.Windows.Forms.ToolStripItem> è associato a <xref:System.Windows.Forms.ToolStrip> o <xref:System.Windows.Forms.ToolStripOverflowButton> oppure può spostarsi tra i due.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Ottiene un valore che indica se un oggetto <xref:System.Windows.Forms.ToolStripItem> Visualizza altri elementi in un elenco a discesa quando <xref:System.Windows.Forms.ToolStripItem> si fa clic su.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Ottiene l'oggetto <xref:System.Windows.Forms.ToolStripItem> che rappresenta il pulsante di overflow di un oggetto <xref:System.Windows.Forms.ToolStrip> con l'overflow abilitato.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Ottiene o imposta un oggetto <xref:System.Windows.Forms.ToolStripRenderer> utilizzato per personalizzare l'aspetto e il comportamento (aspetto) di un oggetto <xref:System.Windows.Forms.ToolStrip> .|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Ottiene o imposta gli stili di disegno da applicare al <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Generato quando la proprietà <xref:System.Windows.Forms.ToolStrip.Renderer%2A> viene modificata.|  
  
 La <xref:System.Windows.Forms.ToolStrip> flessibilità del controllo viene eseguita tramite l'utilizzo di una serie di classi complementari. Di seguito sono riportati alcuni dei più importanti:  
  
### <a name="important-toolstrip-companion-classes"></a>Classi complementari di ToolStrip importanti  
  
|Name|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Sostituisce e aggiunge funzionalità alla <xref:System.Windows.Forms.MainMenu> classe.|  
|<xref:System.Windows.Forms.StatusStrip>|Sostituisce e aggiunge funzionalità alla <xref:System.Windows.Forms.StatusBar> classe.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Sostituisce e aggiunge funzionalità alla <xref:System.Windows.Forms.ContextMenu> classe.|  
|<xref:System.Windows.Forms.ToolStripItem>|Classe di base astratta che gestisce gli eventi e il layout di tutti gli elementi che <xref:System.Windows.Forms.ToolStrip> possono essere contenuti in, <xref:System.Windows.Forms.ToolStripControlHost> o <xref:System.Windows.Forms.ToolStripDropDown> .|  
|<xref:System.Windows.Forms.ToolStripContainer>|Fornisce un contenitore con un pannello su ogni lato del form in cui i controlli possono essere disposti in diversi modi.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Gestisce la funzionalità di disegno per gli oggetti <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Fornisce l'aspetto di tipo Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Controlla il rendering e il raggruppamento verticale/orizzontale dei controlli <xref:System.Windows.Forms.ToolStrip> nonché l'unione degli oggetti <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> e <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Specifica lo stile di disegno (personalizzato, Windows XP o Microsoft Office Professional) applicato a più <xref:System.Windows.Forms.ToolStrip> oggetti contenuti in un modulo.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Specifica lo stile di disegno (personalizzato, Windows XP o Microsoft Office Professional) applicato a un <xref:System.Windows.Forms.ToolStrip> oggetto contenuto in un modulo.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Ospita altri controlli che non sono <xref:System.Windows.Forms.ToolStrip> controlli specifici ma per i quali si desiderano le <xref:System.Windows.Forms.ToolStrip> funzionalità.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Specifica se un oggetto deve <xref:System.Windows.Forms.ToolStripItem> essere disposto sull'oggetto Main <xref:System.Windows.Forms.ToolStrip> , sull'overflow o su <xref:System.Windows.Forms.ToolStrip> nessuno dei due.|  
  
 Per ulteriori informazioni, vedere [Panoramica della tecnologia ToolStrip](toolstrip-technology-summary.md) e [architettura del controllo ToolStrip](toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
