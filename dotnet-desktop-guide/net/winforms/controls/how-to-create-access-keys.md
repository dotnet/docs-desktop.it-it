---
title: Creare chiavi di accesso per i controlli
description: Informazioni su come impostare il tasto di scelta rapida per un controllo o un'etichetta in Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.openlocfilehash: 4d746082ffbaa749b882dcb1a769b5f9541c6fe8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969022"
---
# <a name="add-an-access-key-shortcut-to-a-control-windows-forms-net"></a>Aggiungere un collegamento alla chiave di accesso a un controllo (Windows Forms .NET)

Una *chiave di accesso* è un carattere sottolineato nel testo di un menu, di una voce di menu o dell'etichetta di un controllo, ad esempio un pulsante. Con una chiave di accesso, l'utente può fare clic su un pulsante premendo <kbd>ALT</kbd> insieme al tasto di accesso predefinito. Se, ad esempio, un pulsante esegue una procedura per stampare un form e pertanto la relativa `Text` proprietà è impostata su "stampa", l'aggiunta di una e commerciale (&) prima della lettera "p" causa la sottolineatura della lettera "p" nel testo del pulsante in fase di esecuzione. L'utente può eseguire il comando associato al pulsante premendo <kbd>ALT</kbd>.

I controlli che non possono ricevere lo stato attivo non possono avere chiavi di accesso, ad eccezione di controlli Label.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

Nella finestra **Proprietà** di Visual Studio impostare la proprietà **Text** su una stringa che include una e commerciale (&) prima della lettera che sarà il tasto di accesso. Ad esempio, per impostare la lettera "P" come chiave di accesso, immettere **&stampa**.

:::image type="content" source="media/how-to-create-access-keys/properties-text.png" alt-text="Finestra di dialogo Proprietà con proprietà testo selezionata e chiave di accesso":::

## <a name="programmatic"></a>Programmatica

Impostare la `Text` proprietà su una stringa che include una e commerciale (&) prima della lettera che sarà il collegamento.

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

## <a name="use-a-label-to-focus-a-control"></a>Usare un'etichetta per concentrare un controllo

Anche se un'etichetta non può essere concentrata, ha la possibilità di concentrare il controllo successivo nell'ordine di tabulazione del form. A ogni controllo viene assegnato un valore alla <xref:System.Windows.Forms.Control.TabIndex> proprietà, generalmente in ordine sequenziale crescente. Quando la chiave di accesso viene assegnata alla proprietà [Label. Text](xref:System.Windows.Forms.Label.Text) , il controllo successivo nell'ordine di tabulazione sequenziale è incentrato.

Utilizzando l'esempio della sezione [a livello di codice](#programmatic) , se il pulsante non dispone di un set di testo, ma presenta invece un'immagine di una stampante, è possibile utilizzare un'etichetta per concentrare il pulsante.

```vb
' Set the letter "P" as an access key.
Label1.Text = "&Print"
Label1.TabIndex = 9
Button1.TabIndex = 10
```

```csharp
// Set the letter "P" as an access key.
label1.Text = "&Print";
label1.TabIndex = 9
button1.TabIndex = 10
```

## <a name="display-an-ampersand"></a>Visualizza una e commerciale

Quando si imposta il testo o la didascalia di un controllo che interpreta una e commerciale (&) come chiave di accesso, utilizzare due e commerciali consecutive (&&) per visualizzare una singola e commerciale. Ad esempio, il testo di un pulsante impostato su `"Print && Close"` viene visualizzato nella didascalia di `Print & Close` :

```vb
' Set the letter "P" as an access key.
Button1.Text = "Print && Close"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "Print && Close";
```

:::image type="content" source="media/how-to-create-access-keys/double-ampersand.png" alt-text="visualizzazione di una e commerciale in un pulsante":::

## <a name="see-also"></a>Vedere anche

- [Procedura: impostare il testo visualizzato da un controllo Windows Forms](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.Label>
