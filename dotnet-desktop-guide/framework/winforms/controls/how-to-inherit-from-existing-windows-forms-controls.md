---
title: Ereditare da controlli esistenti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 7d9766c1bb1812cc5978221ccec42f5eb2c8c4ff
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957721"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Procedura: ereditare da controlli di Windows Form esistenti

Se si desidera estendere le funzionalità di un controllo esistente, è possibile creare un controllo derivato da un controllo esistente tramite l'ereditarietà. Quando si eredita da un controllo esistente, si ereditano tutte le funzionalità e le proprietà visive di tale controllo. Se, ad esempio, si crea un controllo che eredita da <xref:System.Windows.Forms.Button> , il nuovo controllo avrà un aspetto simile a quello di un <xref:System.Windows.Forms.Button> controllo standard. È quindi possibile estendere o modificare la funzionalità del nuovo controllo tramite l'implementazione di metodi e proprietà personalizzati. In alcuni controlli, è anche possibile modificare l'aspetto visivo del controllo ereditato eseguendo l'override del relativo <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.

## <a name="to-create-an-inherited-control"></a>Per creare un controllo ereditato

1. In Visual Studio creare un nuovo progetto di **applicazione Windows Form** .

1. Dal menu **Progetto**, scegliere **Aggiungi nuovo elemento**.

    Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .

1. Nella finestra di dialogo **Aggiungi nuovo elemento**, fare doppio clic su **Controllo personalizzato**.

    Un nuovo controllo personalizzato viene aggiunto al progetto.

1. Se si usa:

    - Visual Basic, nella parte superiore di **Esplora soluzioni**, fare clic su **Mostra tutti i file**. Espandere CustomControl1.vb e quindi aprire Customcontrol1 nell'Editor di codice.
    - C#, aprire CustomControl1.cs nell'editor di codice.

1. Individuare la dichiarazione della classe, che eredita da <xref:System.Windows.Forms.Control> .

1. Modificare la classe di base per il controllo da cui si desidera ereditare.

     Se ad esempio si vuole ereditare da <xref:System.Windows.Forms.Button> , modificare la dichiarazione della classe nel modo seguente:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Se si usa Visual Basic, salvare e chiudere CustomControl1.Designer.vb. Aprire Customcontrol1.vb nell'Editor di codice.

1. Implementare eventuali metodi o proprietà personalizzati da incorporare nel controllo.

1. Se si desidera modificare l'aspetto grafico del controllo, eseguire l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.

    > [!NOTE]
    > L'override <xref:System.Windows.Forms.Control.OnPaint%2A> di non consentirà di modificare l'aspetto di tutti i controlli. I controlli che dispongono di tutti i relativi disegni eseguiti da Windows, ad esempio, <xref:System.Windows.Forms.TextBox> non chiamano mai <xref:System.Windows.Forms.Control.OnPaint%2A> il metodo e pertanto non utilizzeranno mai il codice personalizzato. Per verificare se il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è disponibile, fare riferimento alla documentazione della Guida relativa al particolare controllo che si desidera modificare. Per un elenco di tutti i controlli Windows Forms vedere [Controlli da usare in Windows Forms](controls-to-use-on-windows-forms.md). Se un controllo non è <xref:System.Windows.Forms.Control.OnPaint%2A> elencato come metodo membro, non è possibile modificarne l'aspetto eseguendo l'override di questo metodo. Per altre informazioni sul disegno personalizzato, vedere [Disegno e rendering di controlli personalizzati](custom-control-painting-and-rendering.md).

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. Salvare ed eseguire il test del controllo.

## <a name="see-also"></a>Vedi anche

- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
- [Procedura: Ereditare dalla classe Control](how-to-inherit-from-the-control-class.md)
- [Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Procedura: Creare controlli per Windows Form](how-to-author-controls-for-windows-forms.md)
- [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)
- [Procedura dettagliata: eredità da un controllo Windows Form](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
