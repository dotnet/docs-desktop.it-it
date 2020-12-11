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
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="7bc2c-102">Procedura: Esporre le proprietà dei controlli costitutivi</span><span class="sxs-lookup"><span data-stu-id="7bc2c-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="7bc2c-103">I controlli che costituiscono un controllo composto sono denominati *controlli costitutivi*.</span><span class="sxs-lookup"><span data-stu-id="7bc2c-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="7bc2c-104">Questi controlli sono normalmente dichiarati privati e pertanto non è possibile accedervi dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="7bc2c-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="7bc2c-105">Se si desidera rendere le proprietà di questi controlli disponibili per gli utenti futuri, è necessario esporle all'utente.</span><span class="sxs-lookup"><span data-stu-id="7bc2c-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="7bc2c-106">Una proprietà di un controllo costitutivo viene esposta creando una proprietà nel controllo utente e utilizzando le `get` `set` funzioni di accesso e di tale proprietà per applicare la modifica alla proprietà privata del controllo costitutivo.</span><span class="sxs-lookup"><span data-stu-id="7bc2c-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>

 <span data-ttu-id="7bc2c-107">Si consideri un ipotetico controllo utente con un pulsante costitutivo denominato `MyButton` .</span><span class="sxs-lookup"><span data-stu-id="7bc2c-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="7bc2c-108">In questo esempio, quando l'utente richiede la `ConstituentButtonBackColor` proprietà, <xref:System.Windows.Forms.Control.BackColor%2A> viene recapitato il valore archiviato nella proprietà di `MyButton` .</span><span class="sxs-lookup"><span data-stu-id="7bc2c-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="7bc2c-109">Quando l'utente assegna un valore a questa proprietà, tale valore viene passato automaticamente alla <xref:System.Windows.Forms.Control.BackColor%2A> proprietà di `MyButton` e il codice viene `set` eseguito, modificando il colore di `MyButton` .</span><span class="sxs-lookup"><span data-stu-id="7bc2c-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>

 <span data-ttu-id="7bc2c-110">Nell'esempio seguente viene illustrato come esporre la <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del pulsante costituente:</span><span class="sxs-lookup"><span data-stu-id="7bc2c-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>

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

### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="7bc2c-111">Per esporre una proprietà di un controllo costitutivo</span><span class="sxs-lookup"><span data-stu-id="7bc2c-111">To expose a property of a constituent control</span></span>

1. <span data-ttu-id="7bc2c-112">Creare una proprietà pubblica per il controllo utente.</span><span class="sxs-lookup"><span data-stu-id="7bc2c-112">Create a public property for your user control.</span></span>

2. <span data-ttu-id="7bc2c-113">Nella `get` sezione della proprietà scrivere il codice che recupera il valore della proprietà che si desidera esporre.</span><span class="sxs-lookup"><span data-stu-id="7bc2c-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>

3. <span data-ttu-id="7bc2c-114">Nella `set` sezione della proprietà scrivere il codice che passa il valore della proprietà alla proprietà esposta del controllo costitutivo.</span><span class="sxs-lookup"><span data-stu-id="7bc2c-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bc2c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bc2c-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="7bc2c-116">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="7bc2c-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="7bc2c-117">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="7bc2c-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
