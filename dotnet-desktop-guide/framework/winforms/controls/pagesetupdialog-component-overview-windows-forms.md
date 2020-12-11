---
title: Panoramica del componente PageSetupDialog
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964984"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente PageSetupDialog (Windows Form)

Il <xref:System.Windows.Forms.PageSetupDialog> componente Windows Forms è una finestra di dialogo preconfigurata utilizzata per impostare i dettagli della pagina per la stampa in applicazioni basate su Windows. Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice per consentire agli utenti di impostare le preferenze di pagina anziché configurare la propria finestra di dialogo. È possibile consentire agli utenti di impostare le regolazioni del bordo e del margine, le intestazioni e i piè di pagina e l'orientamento verticale o orizzontale. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.

## <a name="key-properties-and-methods"></a>Proprietà e metodi chiave

Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. Questo componente dispone di proprietà che è possibile impostare correlate a una singola pagina ( <xref:System.Drawing.Printing.PrintDocument> classe) o a qualsiasi documento ( <xref:System.Drawing.Printing.PageSettings> classe). Inoltre, il <xref:System.Windows.Forms.PageSetupDialog> componente può essere utilizzato per determinare impostazioni della stampante specifiche, che vengono archiviate nella <xref:System.Drawing.Printing.PrinterSettings> classe.

Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PageSetupDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PageSetupDialog>
- [Componente PageSetupDialog](pagesetupdialog-component-windows-forms.md)
