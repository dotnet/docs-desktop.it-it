---
title: Panoramica del controllo Panel
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 3ea86e898e8a3e1ca90ba8e0a6240414702a1a73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963595"
---
# <a name="panel-control-overview-windows-forms"></a>Cenni preliminari sul controllo Panel (Windows Form)
<xref:System.Windows.Forms.Panel>I controlli Windows Forms vengono utilizzati per fornire un raggruppamento identificabile per gli altri controlli. In genere, si utilizzano i pannelli per suddividere un form per funzione. Ad esempio, è possibile avere un modulo di ordine che specifica le opzioni di mailing, ad esempio il gestore della notte da usare. Il raggruppamento di tutte le opzioni in un pannello offre all'utente un segnale visivo logico. In fase di progettazione tutti i controlli possono essere spostati facilmente: quando si sposta il <xref:System.Windows.Forms.Panel> controllo, vengono spostati anche tutti i controlli contenuti. È possibile accedere ai controlli raggruppati in un pannello tramite la relativa <xref:System.Windows.Forms.Control.Controls%2A> Proprietà. Questa proprietà restituisce una raccolta di <xref:System.Windows.Forms.Control> istanze di, pertanto è in genere necessario eseguire il cast di un controllo recuperato in questo modo al tipo specifico.  
  
## <a name="panel-versus-groupbox"></a>Pannello rispetto a GroupBox  
 Il <xref:System.Windows.Forms.Panel> controllo è simile al <xref:System.Windows.Forms.GroupBox> controllo; tuttavia, solo il <xref:System.Windows.Forms.Panel> controllo può avere barre di scorrimento e solo il <xref:System.Windows.Forms.GroupBox> controllo Visualizza una didascalia.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Per visualizzare le barre di scorrimento, impostare la <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> proprietà su `true` . È anche possibile personalizzare l'aspetto del pannello impostando le <xref:System.Windows.Forms.Control.BackColor%2A> proprietà, <xref:System.Windows.Forms.Control.BackgroundImage%2A> e <xref:System.Windows.Forms.Panel.BorderStyle%2A> . Per altre informazioni sulle <xref:System.Windows.Forms.Control.BackColor%2A> proprietà e <xref:System.Windows.Forms.Control.BackgroundImage%2A> , vedere [procedura: impostare lo sfondo di un pannello](how-to-set-the-background-of-a-windows-forms-panel.md). La <xref:System.Windows.Forms.Panel.BorderStyle%2A> proprietà determina se il pannello è indicato senza bordo visibile ( <xref:System.Windows.Forms.BorderStyle.None> ), una riga normale ( <xref:System.Windows.Forms.BorderStyle.FixedSingle> ) o una linea ombreggiata ( <xref:System.Windows.Forms.BorderStyle.Fixed3D> ).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Panel>
- [Controllo GroupBox](groupbox-control-windows-forms.md)
- [Procedura: Raggruppare i controlli con il controllo Panel di Windows Forms usando la finestra di progettazione](group-controls-with-wf-panel-control-using-the-designer.md)
- [Procedura: Impostare lo sfondo di un controllo Panel di Windows Forms usando la finestra di progettazione](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
