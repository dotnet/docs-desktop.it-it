---
title: Imposta il testo visualizzato da un controllo
description: Informazioni su come impostare il testo visualizzato da un controllo Windows Forms. Impostare o restituire il testo utilizzando la proprietà Text oppure modificare il tipo di carattere utilizzando la proprietà font.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.openlocfilehash: 2fd5a62310ae5e7d6e0528c7f12f37ed40f8a626
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964792"
---
# <a name="how-to-set-the-text-displayed-by-a-control-windows-forms-net"></a>Procedura: impostare il testo visualizzato da un controllo (Windows Forms .NET)

I controlli Windows Forms in genere visualizzano testo correlato alla funzione primaria del controllo. Un controllo, ad esempio, <xref:System.Windows.Forms.Button> Visualizza in genere una didascalia che indica l'azione che verrà eseguita se si fa clic sul pulsante. Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>. È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.

È anche possibile impostare il testo usando la [finestra di progettazione](#designer).

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

01. Nella finestra **Proprietà** di Visual Studio impostare la proprietà **Text** del controllo su una stringa appropriata.

    Per creare un tasto di scelta rapida sottolineato, includere una e commerciale (&) prima della lettera che costituirà il tasto di scelta rapida.

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-text.png" alt-text="Riquadro proprietà di Visual Studio per .NET Windows Forms con proprietà testo visualizzata.":::

01. Nella finestra **Proprietà** selezionare il pulsante con i puntini di sospensione ( ![ pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio ](../media/visual-studio-ellipsis-button.png) ) accanto alla proprietà **font** .

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-font.png" alt-text="Riquadro delle proprietà di Visual Studio per .NET Windows Forms con la proprietà font mostrata.":::

    Nella finestra di dialogo tipo di carattere standard modificare il tipo di carattere con impostazioni quali tipo, dimensioni e stile.

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/font-window.png" alt-text="Riquadro delle proprietà di Visual Studio per .NET Windows Forms con la finestra impostazioni carattere.":::

## <a name="programmatic"></a>Programmatica

01. Impostare la proprietà <xref:System.Windows.Forms.Control.Text%2A> su una stringa.

    Per creare una chiave di accesso sottolineata, includere una e commerciale (&) prima della lettera che sarà il tasto di accesso.

01. Impostare la proprietà <xref:System.Windows.Forms.Control.Font%2A> su un oggetto di tipo <xref:System.Drawing.Font>.

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    > [!NOTE]
    > È possibile usare un carattere di escape per visualizzare un carattere speciale in elementi dell'interfaccia utente in cui tale carattere verrebbe in genere interpretato in modo diverso, ad esempio nelle voci di menu. La riga di codice seguente, ad esempio, imposta il testo della voce di menu in modo da leggere "& ora per qualcosa di completamente diverso":

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Procedura: creare tasti di scelta per i controlli Windows Form](how-to-create-access-keys.md)
