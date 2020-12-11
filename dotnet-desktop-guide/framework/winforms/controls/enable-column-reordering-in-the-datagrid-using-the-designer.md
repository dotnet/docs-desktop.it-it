---
title: Abilitare il riordinamento delle colonne nel controllo DataGridView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 14dc1081a8608c6e6add67f641c4b55825d2fc81
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962902"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione
Quando si visualizzano i dati visualizzati in un <xref:System.Windows.Forms.DataGridView> controllo Windows Forms, gli utenti talvolta desiderano confrontare i valori in colonne specifiche. Questo può risultare scomodo se le colonne sono ampiamente separate nel controllo, soprattutto se gli utenti devono scorrere orizzontalmente per visualizzare tutte le colonne di interesse. È possibile semplificare l'attività di confronto dei valori di colonna consentendo agli utenti di riordinare le colonne. Quando si Abilita il riordinamento delle colonne, gli utenti possono spostare una colonna in una nuova posizione trascinando l'intestazione di colonna con il mouse.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-enable-column-reordering"></a>Per abilitare il riordinamento delle colonne

- Fare clic sul glifo azioni della finestra di progettazione ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllo, quindi selezionare **Abilita riordinamento colonne**.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Procedura: Bloccare le colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md)
