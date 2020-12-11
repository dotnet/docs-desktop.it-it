---
title: Creare elenchi di Master-Details con il controllo DataGrid usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: a60cecf4c4344ab5aca18f76a59223c02d58a062
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951154"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Forms usando la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

 Se <xref:System.Data.DataSet> contiene una serie di tabelle correlate, è possibile usare due <xref:System.Windows.Forms.DataGrid> controlli per visualizzare i dati in un formato Master-Details. Una <xref:System.Windows.Forms.DataGrid> viene designata come griglia master e la seconda viene designata come griglia dei dettagli. Quando si seleziona una voce nell'elenco master, tutte le voci figlio correlate vengono visualizzate nell'elenco dettagli. Se, ad esempio, <xref:System.Data.DataSet> contiene una tabella Customers e una tabella Orders correlata, è necessario specificare la tabella Customers come griglia master e la tabella Orders come griglia dei dettagli. Quando un cliente viene selezionato dalla griglia master, tutti gli ordini associati a tale cliente nella tabella Orders vengono visualizzati nella griglia dei dettagli.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** (**file**  >  **nuovo**  >  **progetto**  >  **Visual C#** o **Visual Basic**  >  **desktop classico**  >  **Windows Forms applicazione**).

## <a name="to-create-a-master-details-list-in-the-designer"></a>Per creare un elenco Master-Details nella finestra di progettazione

1. Aggiungere due <xref:System.Windows.Forms.DataGrid> controlli al form. Per altre informazioni, vedere [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md). Per impostazione predefinita, in Visual Studio 2005 il <xref:System.Windows.Forms.DataGrid> controllo non è presente nella **casella degli strumenti** . Per altre informazioni, vedere [procedura: aggiungere elementi alla casella degli strumenti](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

    > [!NOTE]
    > I passaggi seguenti non sono applicabili a Visual Studio 2005, che usa la finestra **origini dati** per la data binding in fase di progettazione. Per altre informazioni, vedere [associare i controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) e [procedura: visualizzare dati correlati in un'applicazione Windows Forms](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).

2. Trascinare due o più tabelle da **Esplora server** nel form.

3. Scegliere **Genera set** di dati dal menu **dati** .

4. Impostare le relazioni tra le tabelle utilizzando la finestra di progettazione XML. Per informazioni dettagliate, vedere "procedura: creare relazioni uno-a-molti in XML Schema e set di dati" su MSDN.

5. Salvare le relazioni selezionando **Salva tutto** dal menu **file** .

6. Configurare il <xref:System.Windows.Forms.DataGrid> controllo che si desidera designare nella griglia master, come indicato di seguito:

    1. Selezionare <xref:System.Data.DataSet> dall'elenco a discesa nella <xref:System.Windows.Forms.DataGrid.DataSource%2A> Proprietà.

    2. Selezionare la tabella master, ad esempio "Customers", dall'elenco a discesa nella <xref:System.Windows.Forms.DataGrid.DataMember%2A> Proprietà.

7. Configurare il <xref:System.Windows.Forms.DataGrid> controllo che si desidera designare nella griglia dei dettagli, come indicato di seguito:

    1. Selezionare <xref:System.Data.DataSet> dall'elenco a discesa nella <xref:System.Windows.Forms.DataGrid.DataSource%2A> Proprietà.

    2. Selezionare la relazione (ad esempio "Customers. CustOrd") tra le tabelle master e dettagli nell'elenco a discesa della <xref:System.Windows.Forms.DataGrid.DataMember%2A> Proprietà. Per visualizzare la relazione, espandere il nodo facendo clic sul segno più ( **+** ) accanto alla tabella master nell'elenco a discesa.

## <a name="see-also"></a>Vedere anche

- [DataGrid (controllo)](datagrid-control-windows-forms.md)
- [Panoramica del controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Procedura: Associare il controllo DataGrid di Windows Forms a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
