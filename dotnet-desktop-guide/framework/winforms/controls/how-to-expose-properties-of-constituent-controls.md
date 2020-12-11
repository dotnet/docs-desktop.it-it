---
title: 'Procedura: Esporre le proprietà dei controlli costitutivi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961801"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Procedura: Esporre le proprietà dei controlli costitutivi
I controlli che costituiscono un controllo composto sono denominati *controlli costitutivi*. Questi controlli sono normalmente dichiarati privati e pertanto non è possibile accedervi dallo sviluppatore. Se si desidera rendere le proprietà di questi controlli disponibili per gli utenti futuri, è necessario esporle all'utente. Una proprietà di un controllo costitutivo viene esposta creando una proprietà nel controllo utente e utilizzando le `get` `set` funzioni di accesso e di tale proprietà per applicare la modifica alla proprietà privata del controllo costitutivo.

 Si consideri un ipotetico controllo utente con un pulsante costitutivo denominato `MyButton` . In questo esempio, quando l'utente richiede la `ConstituentButtonBackColor` proprietà, <xref:System.Windows.Forms.Control.BackColor%2A> viene recapitato il valore archiviato nella proprietà di `MyButton` . Quando l'utente assegna un valore a questa proprietà, tale valore viene passato automaticamente alla <xref:System.Windows.Forms.Control.BackColor%2A> proprietà di `MyButton` e il codice viene `set` eseguito, modificando il colore di `MyButton` .

 Nell'esempio seguente viene illustrato come esporre la <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del pulsante costituente:

```vb
Public Property ButtonColor() as System.Drawing.Color
   Get
      Return MyButton.BackColor
   End Get
   Set(Value as System.Drawing.Color)
      MyButton.BackColor = Value
   End Set
End Property
```

```csharp
public Color ButtonColor
{
   get
   {
      return(myButton.BackColor);
   }
   set
   {
      myButton.BackColor = value;
   }
}
```

### <a name="to-expose-a-property-of-a-constituent-control"></a>Per esporre una proprietà di un controllo costitutivo

1. Creare una proprietà pubblica per il controllo utente.

2. Nella `get` sezione della proprietà scrivere il codice che recupera il valore della proprietà che si desidera esporre.

3. Nella `set` sezione della proprietà scrivere il codice che passa il valore della proprietà alla proprietà esposta del controllo costitutivo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
