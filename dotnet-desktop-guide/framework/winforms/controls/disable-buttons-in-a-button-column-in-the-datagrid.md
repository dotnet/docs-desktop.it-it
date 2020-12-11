---
title: Disabilitare i pulsanti in una colonna di un pulsante nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96950970"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a>Procedura: Disabilitare i pulsanti in una colonna dei pulsanti nel controllo DataGridView di Windows Forms
Il controllo <xref:System.Windows.Forms.DataGridView> comprende la classe <xref:System.Windows.Forms.DataGridViewButtonCell> per la visualizzazione delle celle con un'interfaccia utente simile a un pulsante. La classe <xref:System.Windows.Forms.DataGridViewButtonCell> non fornisce tuttavia un modo per visualizzare il pulsante nella cella come disabilitato.  
  
 L'esempio di codice seguente illustra come personalizzare la classe <xref:System.Windows.Forms.DataGridViewButtonCell> per visualizzare pulsanti che possono apparire disabilitati. Nell'esempio viene definito un nuovo tipo di cella, `DataGridViewDisableButtonCell`, derivato dalla classe <xref:System.Windows.Forms.DataGridViewButtonCell>. Questo tipo di cella fornisce la nuova proprietà `Enabled`, che può essere impostata su `false` per disegnare un pulsante disabilitato nella cella. Viene inoltre definito il nuovo tipo di colonna `DataGridViewDisableButtonColumn`, in cui sono visualizzati oggetti `DataGridViewDisableButtonCell`. Per illustrare il funzionamento del nuovo tipo di cella e di colonna, il valore corrente di ciascun oggetto <xref:System.Windows.Forms.DataGridViewCheckBoxCell> nel controllo <xref:System.Windows.Forms.DataGridView> padre determina se la proprietà `Enabled` di `DataGridViewDisableButtonCell` nella stessa riga è `true` o `false`.  
  
> [!NOTE]
> Quando si deriva dalla classe <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> e si aggiungono nuove proprietà alla classe derivata, accertarsi di eseguire l'override del metodo `Clone` per copiare le nuove proprietà durante le operazioni di clonazione. È anche necessario chiamare il metodo `Clone` della classe base in modo che le proprietà della classe base vengano copiate nella nuova cella o colonna.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing, System.Windows.Forms e System.Windows.Forms.VisualStyles.  
  
## <a name="see-also"></a>Vedere anche

- [Personalizzazione del controllo DataGridView Windows Form](customizing-the-windows-forms-datagridview-control.md)
- [Architettura del controllo DataGridView](datagridview-control-architecture-windows-forms.md)
- [Tipi di colonna nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
