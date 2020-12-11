---
title: Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset
description: Informazioni su come usare i metodi ShouldSerialize e reset Property per controllare il comportamento della finestra di progettazione Windows Forms.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: b425b301a1c07030ad4cefa70e41198d08598631
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951019"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="3a839-103">Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset</span><span class="sxs-lookup"><span data-stu-id="3a839-103">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="3a839-104">`ShouldSerialize` e `Reset` sono metodi facoltativi che è possibile fornire per una proprietà, se la proprietà non dispone di un valore predefinito semplice.</span><span class="sxs-lookup"><span data-stu-id="3a839-104">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not have a simple default value.</span></span> <span data-ttu-id="3a839-105">Se la proprietà ha un valore predefinito semplice, è necessario applicare <xref:System.ComponentModel.DefaultValueAttribute> e fornire il valore predefinito al costruttore della classe Attribute.</span><span class="sxs-lookup"><span data-stu-id="3a839-105">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="3a839-106">Uno di questi meccanismi Abilita le funzionalità seguenti nella finestra di progettazione:</span><span class="sxs-lookup"><span data-stu-id="3a839-106">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="3a839-107">La proprietà fornisce un'indicazione visiva nel Visualizzatore proprietà se è stata modificata rispetto al valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3a839-107">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="3a839-108">L'utente può fare clic con il pulsante destro del mouse sulla proprietà e scegliere **Reimposta** per ripristinare il valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a839-108">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="3a839-109">La finestra di progettazione genera codice più efficiente.</span><span class="sxs-lookup"><span data-stu-id="3a839-109">The designer generates more efficient code.</span></span>

> [!NOTE]
> <span data-ttu-id="3a839-110">Applicare <xref:System.ComponentModel.DefaultValueAttribute> o fornire i metodi `Reset` *PropertyName* e `ShouldSerialize` *PropertyName* .</span><span class="sxs-lookup"><span data-stu-id="3a839-110">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="3a839-111">Non usare entrambi.</span><span class="sxs-lookup"><span data-stu-id="3a839-111">Do not use both.</span></span>

<span data-ttu-id="3a839-112">Quando si dichiara un `ShouldSerialize` `Reset` metodo o, usare il `private` modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="3a839-112">When declaring a `ShouldSerialize` or `Reset` method, use the `private` access modifier.</span></span> <span data-ttu-id="3a839-113">Questi metodi vengono in genere richiamati dalla finestra di progettazione e non dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="3a839-113">These methods are usually invoked by the designer and not by user code.</span></span>

 <span data-ttu-id="3a839-114">Il `Reset` metodo *PropertyName* imposta una proprietà sul relativo valore predefinito, come illustrato nel frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3a839-114">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

```vb
Private Sub ResetMyFont()
   MyFont = Nothing
End Sub
```

```csharp
private void ResetMyFont()
{
   MyFont = null;
}
```

> [!NOTE]
> <span data-ttu-id="3a839-115">Se una proprietà non dispone di un `Reset` metodo, non è contrassegnata con un oggetto <xref:System.ComponentModel.DefaultValueAttribute> e non dispone di un valore predefinito specificato nella relativa dichiarazione, l' `Reset` opzione per tale proprietà è disabilitata nel menu di scelta rapida della finestra **Proprietà** del progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3a839-115">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="3a839-116">Le finestre di progettazione, ad esempio Visual Studio, usano il `ShouldSerialize` metodo *PropertyName* per verificare se una proprietà è cambiata rispetto al valore predefinito e scrivere codice nel form solo se una proprietà viene modificata, consentendo così una generazione di codice più efficiente.</span><span class="sxs-lookup"><span data-stu-id="3a839-116">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="3a839-117">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3a839-117">For example:</span></span>

```vb
'Returns true if the font has changed; otherwise, returns false.
' The designer writes code to the form only if true is returned.
Private Function ShouldSerializeMyFont() As Boolean
   Return thefont IsNot Nothing
End Function
```

```csharp
// Returns true if the font has changed; otherwise, returns false.
// The designer writes code to the form only if true is returned.
private bool ShouldSerializeMyFont()
{
   return thefont != null;
}
```

> [!TIP]
> <span data-ttu-id="3a839-118">Se si desidera impedire in modo permanente la serializzazione di una proprietà da parte della finestra di progettazione, aggiungere l'attributo [DesignerSerializationVisibility](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) con il valore di `Hidden` .</span><span class="sxs-lookup"><span data-stu-id="3a839-118">If you want to permanently prevent a property from being serialized by the designer, add the [DesignerSerializationVisibility](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) attribute with the value of `Hidden`.</span></span>

 <span data-ttu-id="3a839-119">Di seguito è riportato un esempio di codice completo.</span><span class="sxs-lookup"><span data-stu-id="3a839-119">A complete code example follows.</span></span>

```vb
Option Explicit
Option Strict

Imports System.Drawing
Imports System.Windows.Forms

Public Class MyControl
   Inherits Control

   ' Declare an instance of the Font class
   ' and set its default value to Nothing.
   Private thefont As Font = Nothing

   ' The MyFont property.
   Public Property MyFont() As Font
      ' Note that the Font property never
      ' returns null.
      Get
         If Not (thefont Is Nothing) Then
            Return thefont
         End If
         If Not (Parent Is Nothing) Then
            Return Parent.Font
         End If
         Return Control.DefaultFont
      End Get
      Set
         thefont = value
      End Set
   End Property

   Private Function ShouldSerializeMyFont() As Boolean
      Return thefont IsNot Nothing
   End Function

   Private Sub ResetMyFont()
      MyFont = Nothing
   End Sub
End Class
```

```csharp
using System;
using System.Drawing;
using System.Windows.Forms;

public class MyControl : Control {
   // Declare an instance of the Font class
   // and set its default value to null.
   private Font thefont = null;

   // The MyFont property.
   public Font MyFont {
      // Note that the MyFont property never
      // returns null.
      get {
         if (thefont != null) return thefont;
         if (Parent != null) return Parent.Font;
         return Control.DefaultFont;
      }
      set {
         thefont = value;
      }
   }

   private bool ShouldSerializeMyFont()
   {
      return thefont != null;
   }

   private void ResetMyFont()
   {
      MyFont = null;
   }
}
```

 <span data-ttu-id="3a839-120">In questo caso, anche quando il valore della variabile privata a cui si accede tramite la `MyFont` proprietà è `null` , il Visualizzatore proprietà non viene visualizzato; in caso `null` contrario, Visualizza la <xref:System.Windows.Forms.Control.Font%2A> proprietà dell'elemento padre, in caso contrario `null` , o il <xref:System.Windows.Forms.Control.Font%2A> valore predefinito definito in <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="3a839-120">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="3a839-121">Pertanto, il valore predefinito di `MyFont` non può essere semplicemente impostato e <xref:System.ComponentModel.DefaultValueAttribute> non è possibile applicare un oggetto a questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a839-121">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="3a839-122">Al contrario, `ShouldSerialize` `Reset` è necessario implementare i metodi e per la `MyFont` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a839-122">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a839-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a839-123">See also</span></span>

- [<span data-ttu-id="3a839-124">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="3a839-124">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="3a839-125">Definizione di una proprietà</span><span class="sxs-lookup"><span data-stu-id="3a839-125">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="3a839-126">Eventi per proprietà modificate</span><span class="sxs-lookup"><span data-stu-id="3a839-126">Property-Changed Events</span></span>](property-changed-events.md)
- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute?displayProperty=fullName>
