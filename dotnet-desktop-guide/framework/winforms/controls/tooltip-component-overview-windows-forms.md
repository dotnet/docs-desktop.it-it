---
title: Panoramica del componente ToolTip
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966508"
---
# <a name="tooltip-component-overview-windows-forms"></a>Cenni preliminari sul componente ToolTip (Windows Form)
Il componente <xref:System.Windows.Forms.ToolTip> di Windows Form visualizza un testo quando l'utente posiziona il puntatore sui controlli. Una descrizione comando può essere associata a qualsiasi controllo. Esempio di utilizzo di questo componente: per risparmiare spazio in un form, è possibile visualizzare un'icona di piccole dimensioni su un pulsante e utilizzare una descrizione comando per spiegare la funzione del pulsante.  
  
## <a name="working-with-the-tooltip-component"></a>Utilizzo del componente descrizione comando  
 Un <xref:System.Windows.Forms.ToolTip> componente fornisce una `ToolTip` proprietà a più controlli in un Windows Form o in un altro contenitore. Se, ad esempio, si inserisce un <xref:System.Windows.Forms.ToolTip> componente in un modulo, è possibile visualizzare "digitare il proprio nome" per un <xref:System.Windows.Forms.TextBox> controllo e "fare clic qui per salvare le modifiche" per un <xref:System.Windows.Forms.Button> controllo.  
  
 I metodi principali del <xref:System.Windows.Forms.ToolTip> componente sono <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> e <xref:System.Windows.Forms.ToolTip.GetToolTip%2A> . È possibile utilizzare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo per impostare le descrizioni comandi visualizzate per i controlli. Per altre informazioni, vedere [procedura: impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Le proprietà chiave sono <xref:System.Windows.Forms.ToolTip.Active%2A> , che devono essere impostate su `true` affinché venga visualizzata la descrizione comando e <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> , che imposta il periodo di tempo in cui viene visualizzata la stringa della descrizione comando, per quanto tempo l'utente deve puntare al controllo affinché venga visualizzata la descrizione comando e il tempo necessario per la visualizzazione delle finestre di descrizione comando successive. Per altre informazioni, vedere [How to: Change the delay of the Windows Forms ToolTip Component](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolTip>
- [Procedura: Impostare le descrizioni comando per i controlli in un Windows Form in fase di progettazione](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Procedura: Modificare il ritardo del componente ToolTip di Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
