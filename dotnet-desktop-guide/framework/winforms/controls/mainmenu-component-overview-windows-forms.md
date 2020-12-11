---
title: Panoramica del componente MainMenu
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961534"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Cenni preliminari sul componente MainMenu (Windows Form)
> [!IMPORTANT]
> Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> controlli e delle versioni precedenti <xref:System.Windows.Forms.MainMenu> e vengono conservati per compatibilità con le versioni precedenti <xref:System.Windows.Forms.ContextMenu> e per un uso futuro, se si sceglie.  
  
 Il <xref:System.Windows.Forms.MainMenu> componente Windows Forms Visualizza un menu in fase di esecuzione. Tutti i sottomenu del menu principale e dei singoli elementi sono <xref:System.Windows.Forms.MenuItem> oggetti.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Una voce di menu può essere designata come elemento predefinito impostando la <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> proprietà su `true` . Quando si fa clic sul menu, l'elemento predefinito viene visualizzato in grassetto. La proprietà della voce di menu <xref:System.Windows.Forms.MenuItem.Checked%2A> può essere `true` o `false` e indica se la voce di menu è selezionata. La proprietà della voce <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> di menu Personalizza l'aspetto dell'elemento selezionato: se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `true` , accanto all'elemento viene visualizzato un pulsante di opzione; se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `false` , accanto all'elemento viene visualizzato un segno di spunta.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Panoramica del controllo MenuStrip](menustrip-control-overview-windows-forms.md)
