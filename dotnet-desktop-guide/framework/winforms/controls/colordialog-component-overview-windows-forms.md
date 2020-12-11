---
title: Panoramica del componente ColorDialog
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951235"
---
# <a name="colordialog-component-overview-windows-forms"></a>Cenni preliminari sul componente ColorDialog (Windows Form)
Il <xref:System.Windows.Forms.ColorDialog> componente Windows Forms è una finestra di dialogo preconfigurata che consente all'utente di selezionare un colore da una tavolozza e di aggiungere colori personalizzati alla tavolozza. È la stessa finestra di dialogo visualizzata in altre applicazioni basate su Windows per selezionare i colori. e costituisce una semplice soluzione, utilizzabile nell'applicazione basata su Windows creata, per evitare di configurare una propria finestra di dialogo.  
  
 Il colore selezionato nella finestra di dialogo viene restituito nella <xref:System.Windows.Forms.ColorDialog.Color%2A> Proprietà. Se la <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> proprietà è impostata su `false` , il pulsante "Definisci colori personalizzati" è disabilitato e l'utente è limitato ai colori predefiniti della tavolozza. Se la <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> proprietà è impostata su `true` , l'utente non è in grado di selezionare i colori dimessi. Per visualizzare la finestra di dialogo, è necessario chiamare il relativo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
- [Controlli e componenti della finestra di dialogo](dialog-box-controls-and-components-windows-forms.md)
- [Procedura: Modificare l'aspetto del componente ColorDialog di Windows Forms](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
