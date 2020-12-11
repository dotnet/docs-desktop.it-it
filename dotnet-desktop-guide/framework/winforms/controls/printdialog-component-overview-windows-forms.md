---
title: Panoramica del componente PrintDialog
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961465"
---
# <a name="printdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente PrintDialog (Windows Form)

Il Windows Forms componente [PrintDialog](printdialog-component-windows-forms.md) è una finestra di dialogo preconfigurata utilizzata per selezionare una stampante, scegliere le pagine da stampare e determinare altre impostazioni relative alla stampa nelle applicazioni basate su Windows. Questo componente può essere usato come semplice soluzione per la selezione della stampante e delle impostazioni relative alla stampa anziché configurare una propria finestra di dialogo. È possibile consentire agli utenti di stampare molte parti dei documenti: stampa tutto, stampa un intervallo di pagine selezionato o stampa una selezione. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti. Il <xref:System.Windows.Forms.PrintDialog> componente eredita dalla <xref:System.Windows.Forms.CommonDialog> classe.

## <a name="working-with-the-component"></a>Utilizzo del componente

Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. Questo componente dispone di proprietà correlate a un singolo processo di stampa ( <xref:System.Drawing.Printing.PrintDocument> classe) o alle impostazioni di una singola stampante ( <xref:System.Drawing.Printing.PrinterSettings> classe). Uno di questi, a sua volta, può essere condiviso da più stampanti.

Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PrintDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PrintDialog>
- [Componente PrintDialog](printdialog-component-windows-forms.md)
