---
title: Aggiungere e rimuovere colonne nel controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 8843b1d30f3e5f31a060e27b41b0105e6584f155
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952668"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione
Il <xref:System.Windows.Forms.DataGridView> controllo Windows Forms deve contenere colonne per visualizzare i dati. Se si prevede di popolare il controllo manualmente, è necessario aggiungere manualmente le colonne. In alternativa, è possibile associare il controllo a un'origine dati che genera e popola automaticamente le colonne. Se l'origine dati contiene più colonne di quelle che si desidera visualizzare, è possibile rimuovere le colonne indesiderate.

 Per le procedure riportate di seguito è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-add-a-column-using-the-designer"></a>Per aggiungere una colonna utilizzando la finestra di progettazione

1. Fare clic sul glifo azioni della finestra di progettazione ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllo, quindi selezionare **Aggiungi colonna**.

2. Nella finestra di dialogo **Aggiungi colonna** scegliere l'opzione **colonna con binding** a dati e selezionare una colonna dall'origine dati oppure scegliere l'opzione **colonna non associata** e definire la colonna utilizzando i campi specificati.

3. Fare clic sul pulsante **Aggiungi** per aggiungere la colonna, facendo in modo che venga visualizzata nella finestra di progettazione se le colonne esistenti non riempiono ancora l'area di visualizzazione del controllo.

    > [!NOTE]
    > È possibile modificare le proprietà delle colonne nella finestra di dialogo **modifica colonne** , a cui è possibile accedere dallo smart tag del controllo.

## <a name="to-remove-a-column-using-the-designer"></a>Per rimuovere una colonna utilizzando la finestra di progettazione

1. Scegliere **modifica colonne** dallo smart tag del controllo.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Fare clic sul pulsante **Rimuovi** per eliminare la colonna, causando la scomparsa dalla finestra di progettazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md)
