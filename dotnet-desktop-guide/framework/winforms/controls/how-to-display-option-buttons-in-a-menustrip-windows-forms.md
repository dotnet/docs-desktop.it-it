---
title: 'Procedura: Visualizzare pulsanti di opzione in un controllo MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964459"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Procedura: visualizzare pulsanti di opzione in un controllo MenuStrip (Windows Form)

I pulsanti di opzione, noti anche come pulsanti di opzione, sono simili alle caselle di controllo, ad eccezione del fatto che gli utenti possono selezionare solo uno alla volta. Anche se, per impostazione predefinita <xref:System.Windows.Forms.ToolStripMenuItem> , la classe non fornisce il comportamento del pulsante di opzione, la classe fornisce il comportamento della casella di controllo che è possibile personalizzare per implementare il comportamento del pulsante di opzione per le voci di menu in un <xref:System.Windows.Forms.MenuStrip> controllo.

Quando la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà di una voce di menu è `true` , gli utenti possono fare clic sull'elemento per abilitare o disabilitare la visualizzazione di un segno di spunta. La <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà indica lo stato corrente dell'elemento. Per implementare il comportamento di base dei pulsanti di opzione, è necessario assicurarsi che, quando si seleziona un elemento, impostare la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà per l'elemento selezionato in precedenza su `false` .

Nelle procedure seguenti viene descritto come implementare questa e funzionalità aggiuntiva in una classe che eredita la <xref:System.Windows.Forms.ToolStripMenuItem> classe. La `ToolStripRadioButtonMenuItem` classe esegue l'override dei membri, ad esempio <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> e, <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> per fornire il comportamento di selezione e l'aspetto dei pulsanti di opzione. Questa classe, inoltre, esegue l'override della <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Proprietà in modo che le opzioni di un sottomenu siano disabilitate, a meno che non sia selezionato l'elemento padre.

## <a name="to-implement-option-button-selection-behavior"></a>Per implementare il comportamento di selezione dei pulsanti di opzione

1. Inizializza la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà su `true` per abilitare la selezione dell'elemento.

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. Eseguire l'override del <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> metodo per cancellare la selezione dell'elemento selezionato in precedenza quando viene selezionato un nuovo elemento.

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. Eseguire l'override del <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> metodo per fare in modo che facendo clic su un elemento già selezionato non venga cancellata la selezione.

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>Per modificare l'aspetto degli elementi del pulsante di opzione

1. Eseguire l'override del <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> metodo per sostituire il segno di spunta predefinito con un pulsante di opzione usando la <xref:System.Windows.Forms.RadioButtonRenderer> classe.

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. Eseguire l'override dei <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A> metodi,, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> e <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> per tenere traccia dello stato del mouse e assicurarsi che il <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> Metodo disegni lo stato corretto del pulsante di opzione.

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Per disabilitare le opzioni in un sottomenu quando l'elemento padre non è selezionato

1. Eseguire l'override della <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Proprietà in modo che l'elemento venga disabilitato quando dispone di un elemento padre con un <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> valore `true` e un <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> valore `false` .

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. Eseguire l'override del <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> metodo per sottoscrivere l' <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> evento dell'elemento padre.

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. Nel gestore per l'evento padre-elemento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> , invalidare l'elemento per aggiornare la visualizzazione con il nuovo stato abilitato.

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>Esempio

Nell'esempio di codice seguente vengono fornite la `ToolStripRadioButtonMenuItem` classe completa e una <xref:System.Windows.Forms.Form> classe e una `Program` classe per illustrare il comportamento del pulsante di opzione.

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
- [Procedura: Implementare un oggetto ToolStripRenderer personalizzato](how-to-implement-a-custom-toolstriprenderer.md)
