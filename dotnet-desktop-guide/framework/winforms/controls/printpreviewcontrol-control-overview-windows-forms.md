---
title: Panoramica del controllo PrintPreviewControl
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965635"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Cenni preliminari sul controllo PrintPreviewControl (Windows Form)
Il Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> viene usato per visualizzare un [PrintDocument](printdocument-component-windows-forms.md) come verrà visualizzato quando viene stampato. Il controllo non dispone di alcun pulsante o altri elementi dell'interfaccia utente, pertanto, in genere <xref:System.Windows.Forms.PrintPreviewControl> viene usato solo se si vuole creare un'interfaccia utente di anteprima di stampa personalizzata. Se si desidera l'interfaccia utente standard, utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> controllo; vedere [Cenni preliminari sul controllo PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md) per una panoramica.  
  
## <a name="key-properties"></a>Proprietà chiave  
 La proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> , che imposta il documento da visualizzare in anteprima. Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto. Per una panoramica della creazione di documenti per la stampa, vedere [Cenni preliminari sul componente PrintDocument](printdocument-component-overview-windows-forms.md) e supporto per la [stampa Windows Forms](../advanced/windows-forms-print-support.md). Le <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> proprietà e determinano il numero di pagine visualizzate orizzontalmente e verticalmente sul controllo. L'anti-aliasing può rendere il testo più semplice, ma può anche rendere più lenta la visualizzazione. per usarlo, impostare la <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> proprietà su `true` .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PrintPreviewControl>
- [Panoramica del controllo PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md)
- [Controllo PrintPreviewControl](printpreviewcontrol-control-windows-forms.md)
- [Controlli e componenti della finestra di dialogo](dialog-box-controls-and-components-windows-forms.md)
