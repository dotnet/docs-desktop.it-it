---
title: Panoramica del controllo LinkLabel
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965092"
---
# <a name="linklabel-control-overview-windows-forms"></a>Cenni preliminari sul controllo LinkLabel (Windows Form)
Il <xref:System.Windows.Forms.LinkLabel> controllo Windows Forms consente di aggiungere collegamenti di tipo Web alle applicazioni Windows Forms. È possibile utilizzare il <xref:System.Windows.Forms.LinkLabel> controllo per tutti gli elementi per cui è possibile utilizzare il <xref:System.Windows.Forms.Label> controllo. è inoltre possibile impostare parte del testo come collegamento a un file, a una cartella o a una pagina Web.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Operazioni possibili con il controllo LinkLabel  
 Oltre a tutte le proprietà, i metodi e gli eventi del <xref:System.Windows.Forms.Label> controllo, il <xref:System.Windows.Forms.LinkLabel> controllo dispone di proprietà per i collegamenti ipertestuali e i colori dei collegamenti. La <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà consente di impostare l'area del testo che attiva il collegamento. Le <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> proprietà, e <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> impostano i colori del collegamento. L' <xref:System.Windows.Forms.LinkLabel.LinkClicked> evento determina cosa accade quando viene selezionato il testo del collegamento.  
  
 L'uso più semplice del <xref:System.Windows.Forms.LinkLabel> controllo consiste nel visualizzare un singolo collegamento usando la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà, ma è anche possibile visualizzare più collegamenti ipertestuali usando la <xref:System.Windows.Forms.LinkLabel.Links%2A> Proprietà. La <xref:System.Windows.Forms.LinkLabel.Links%2A> proprietà consente di accedere a una raccolta di collegamenti. È anche possibile specificare i dati nella <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> proprietà di ogni singolo <xref:System.Windows.Forms.LinkLabel.Link> oggetto. Il valore della <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> proprietà può essere utilizzato per archiviare il percorso di un file da visualizzare o l'indirizzo di un sito Web.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.LinkLabel>
- [Panoramica del controllo Label](label-control-overview-windows-forms.md)
- [Procedura: Eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Procedura: Modificare l'aspetto del controllo LinkLabel di Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
