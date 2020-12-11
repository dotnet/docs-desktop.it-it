---
title: Modificare il tipo di una colonna DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 470f350a4791a3db39d08ab7992d86eb7b2e270a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962962"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Procedura: Modificare il tipo di una colonna DataGridView di Windows Forms usando la finestra di progettazione
In alcuni casi è necessario modificare il tipo di una colonna che è già stata aggiunta a un <xref:System.Windows.Forms.DataGridView> controllo Windows Forms. È ad esempio possibile che si desideri modificare i tipi di alcune colonne generate automaticamente quando si associa il controllo a un'origine dati. Questa operazione è utile quando nella tabella visualizzata sono presenti colonne contenenti chiavi esterne alle righe di una tabella correlata. In questo caso, è possibile sostituire le colonne della casella di testo in cui vengono visualizzate le chiavi esterne con le colonne della casella combinata che visualizzano valori più significativi della tabella correlata.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>Per modificare il tipo di una colonna utilizzando la finestra di progettazione

1. Fare clic sul glifo azioni della finestra di progettazione ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllo, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Nella griglia **Proprietà colonna** impostare la proprietà sul `ColumnType` nuovo tipo di colonna.

    > [!NOTE]
    > La `ColumnType` proprietà è una proprietà solo in fase di progettazione che indica la classe che rappresenta il tipo di colonna. Non si tratta di una proprietà effettiva definita in una classe Column.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md)
