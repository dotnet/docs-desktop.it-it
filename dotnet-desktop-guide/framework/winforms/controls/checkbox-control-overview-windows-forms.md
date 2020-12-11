---
title: Panoramica del controllo CheckBox
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952583"
---
# <a name="checkbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo CheckBox (Windows Form)
Il controllo di Windows Form <xref:System.Windows.Forms.CheckBox> indica se una determinata condizione è attiva o disattivata. Viene usato comunemente per presentare all'utente la selezione di valori Sì/No o True/False. È possibile usare i controlli della casella di controllo in gruppi, per visualizzare e consentire all'utente la selezione di una o più opzioni.  
  
 Il controllo casella di controllo è simile al controllo pulsante di opzione in quanto ogni viene usato per indicare una selezione eseguita dall'utente. Si differenziano per il fatto che è possibile selezionare un solo pulsante di opzione in un gruppo alla volta. Con il controllo casella di controllo, tuttavia, è possibile selezionare qualsiasi numero di caselle di controllo.  
  
 Una casella di controllo può essere connessa agli elementi di un database utilizzando semplici data binding. È possibile raggruppare più caselle di controllo utilizzando il <xref:System.Windows.Forms.GroupBox> controllo. Questa operazione è utile per l'aspetto visivo e anche per la progettazione dell'interfaccia utente, poiché i controlli raggruppati possono essere spostati insieme nella finestra di progettazione del form. Per ulteriori informazioni, vedere [Windows Forms Data Binding](../windows-forms-data-binding.md) e il [controllo GroupBox](groupbox-control-windows-forms.md).  
  
 Il <xref:System.Windows.Forms.CheckBox> controllo dispone di due proprietà importanti, <xref:System.Windows.Forms.CheckBox.Checked%2A> e <xref:System.Windows.Forms.CheckBox.CheckState%2A> . La <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà restituisce `true` o `false` . La <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà restituisce <xref:System.Windows.Forms.CheckState.Checked> o oppure <xref:System.Windows.Forms.CheckState.Unchecked> , se la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> proprietà è impostata su `true` , <xref:System.Windows.Forms.CheckBox.CheckState%2A> può restituire anche <xref:System.Windows.Forms.CheckState.Indeterminate> . Nello stato indeterminato, la casella viene visualizzata con un aspetto attenuato per indicare che l'opzione non è disponibile.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.CheckBox>
- [Procedura: impostare opzioni con i controlli CheckBox di Windows Form](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Procedura: rispondere alla selezione di controlli CheckBox Windows Form](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox (controllo)](checkbox-control-windows-forms.md)
