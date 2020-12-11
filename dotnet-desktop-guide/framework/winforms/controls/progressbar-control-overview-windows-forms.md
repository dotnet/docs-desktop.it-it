---
title: Panoramica del controllo ProgressBar
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: a0c4a0401d06614ab3ad148b932ebc64080c592c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951426"
---
# <a name="progressbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo ProgressBar (Windows Form)
> [!IMPORTANT]
> Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il <xref:System.Windows.Forms.ProgressBar> controllo Windows Forms indica lo stato di avanzamento di un processo visualizzando un numero appropriato di rettangoli disposti in una barra orizzontale. Al termine del processo, la barra viene compilata. Gli indicatori di stato vengono comunemente usati per fornire all'utente un'idea del tempo di attesa per il completamento di un processo. ad esempio, quando viene caricato un file di grandi dimensioni.  
  
> [!NOTE]
> Il <xref:System.Windows.Forms.ProgressBar> controllo può essere orientato solo orizzontalmente sul form.  
  
## <a name="key-properties-and-methods"></a>Proprietà e metodi chiave  
 Le proprietà chiave del <xref:System.Windows.Forms.ProgressBar> controllo sono <xref:System.Windows.Forms.ProgressBar.Value%2A> , <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> . Le <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> proprietà e impostano i valori massimi e minimi che possono essere visualizzati nell'indicatore di stato. La <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà rappresenta lo stato di avanzamento che è stato eseguito per completare l'operazione. Poiché la barra visualizzata nel controllo è costituita da blocchi, il valore visualizzato dal <xref:System.Windows.Forms.ProgressBar> controllo indica solo il <xref:System.Windows.Forms.ProgressBar.Value%2A> valore corrente della proprietà. In base alla dimensione del <xref:System.Windows.Forms.ProgressBar> controllo, la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà determina quando visualizzare il blocco successivo.  
  
 Il modo più comune per aggiornare il valore di stato corrente è scrivere codice per impostare la <xref:System.Windows.Forms.ProgressBar.Value%2A> Proprietà. Nell'esempio relativo al caricamento di un file di grandi dimensioni, è possibile impostare il valore massimo per le dimensioni del file, espressa in kilobyte. Se, ad esempio, la <xref:System.Windows.Forms.ProgressBar.Maximum%2A> proprietà è impostata su 100, la <xref:System.Windows.Forms.ProgressBar.Minimum%2A> proprietà è impostata su 10 e la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà è impostata su 50, verranno visualizzati 5 rettangoli. Questa è la metà del numero che è possibile visualizzare.  
  
 Tuttavia, esistono altri modi per modificare il valore visualizzato dal <xref:System.Windows.Forms.ProgressBar> controllo, oltre a impostare <xref:System.Windows.Forms.ProgressBar.Value%2A> direttamente la proprietà. La <xref:System.Windows.Forms.ProgressBar.Step%2A> proprietà può essere utilizzata per specificare un valore in base al quale incrementare la <xref:System.Windows.Forms.ProgressBar.Value%2A> Proprietà. Quindi, la chiamata al <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> Metodo incrementerà il valore. Per variare il valore di incremento, è possibile usare il <xref:System.Windows.Forms.ProgressBar.Increment%2A> metodo e specificare un valore con cui incrementare la <xref:System.Windows.Forms.ProgressBar.Value%2A> Proprietà.  
  
 Un altro controllo che informa graficamente l'utente di un'azione corrente è il <xref:System.Windows.Forms.StatusBar> controllo.  
  
> [!IMPORTANT]
> I <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> controlli e sostituiscono e aggiungono funzionalità <xref:System.Windows.Forms.StatusBar> ai <xref:System.Windows.Forms.StatusBarPanel> controlli e; tuttavia, <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> controlli e vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se si sceglie.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ProgressBar>
- [Controllo ProgressBar](progressbar-control-windows-forms.md)
