---
title: 'Procedura: Determinare quale tasto di modifica è stato premuto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 9140834b4849ecb143ac57a6f6ae20e2d870859b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951335"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Procedura: Determinare quale tasto di modifica è stato premuto

Quando si crea un'applicazione che accetta le sequenze di tasti dell'utente, può essere utile monitorare anche i tasti di modifica, ad esempio i tasti MAIUSC, ALT e CTRL. Quando si preme un tasto di modifica in combinazione con altre chiavi o con clic del mouse, l'applicazione può rispondere in modo appropriato. Se, ad esempio, si preme la lettera S, è possibile che venga visualizzato uno "s" sullo schermo, ma se vengono premuti i tasti CTRL + S, è possibile salvare il documento corrente. Se si gestisce l' <xref:System.Windows.Forms.Control.KeyDown> evento, la <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> proprietà dell'oggetto <xref:System.Windows.Forms.KeyEventArgs> ricevuto dal gestore eventi specifica i tasti di modifica che vengono premuti. In alternativa, la <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> proprietà di <xref:System.Windows.Forms.KeyEventArgs> specifica il carattere premuto e tutti i tasti di modifica combinati con un OR bit per bit. Tuttavia, se si gestisce l' <xref:System.Windows.Forms.Control.KeyPress> evento o un evento del mouse, il gestore eventi non riceve queste informazioni. In questo caso, è necessario usare la <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà della <xref:System.Windows.Forms.Control> classe. In entrambi i casi, è necessario eseguire un operatore AND bit per bit del <xref:System.Windows.Forms.Keys> valore appropriato e il valore che si sta testando. L' <xref:System.Windows.Forms.Keys> enumerazione offre varianti di ogni tasto di modifica, quindi è importante eseguire l'operatore and bit per bit con il valore corretto. Ad esempio, il tasto MAIUSC è rappresentato da <xref:System.Windows.Forms.Keys.Shift> , <xref:System.Windows.Forms.Keys.ShiftKey> <xref:System.Windows.Forms.Keys.RShiftKey> e <xref:System.Windows.Forms.Keys.LShiftKey> il valore corretto per testare lo spostamento come un tasto di modifica è <xref:System.Windows.Forms.Keys.Shift> . Analogamente, per verificare la presenza di tasti CTRL e ALT come modificatori, è necessario usare <xref:System.Windows.Forms.Keys.Control> <xref:System.Windows.Forms.Keys.Alt> rispettivamente i valori e.  
  
> [!NOTE]
> I programmatori Visual Basic possono anche accedere alle informazioni chiave tramite la <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> Proprietà  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Per determinare quale tasto di modifica è stato premuto  
  
- Usare l'operatore bit per bit `AND` con la <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà e un valore dell' <xref:System.Windows.Forms.Keys> enumerazione per determinare se viene premuto un particolare tasto di modifica. Nell'esempio di codice seguente viene illustrato come determinare se il tasto MAIUSC è premuto in un <xref:System.Windows.Forms.Control.KeyPress> gestore eventi.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [Input da tastiera in un'applicazione Windows Form](keyboard-input-in-a-windows-forms-application.md)
- [Procedura: determinare se CapsLock è on in Visual Basic](/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
