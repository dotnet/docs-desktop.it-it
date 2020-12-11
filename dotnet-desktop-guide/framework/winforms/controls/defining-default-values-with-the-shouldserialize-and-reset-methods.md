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
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset
`ShouldSerialize` e `Reset` sono metodi facoltativi che è possibile fornire per una proprietà, se la proprietà non dispone di un valore predefinito semplice. Se la proprietà ha un valore predefinito semplice, è necessario applicare <xref:System.ComponentModel.DefaultValueAttribute> e fornire il valore predefinito al costruttore della classe Attribute. Uno di questi meccanismi Abilita le funzionalità seguenti nella finestra di progettazione:

- La proprietà fornisce un'indicazione visiva nel Visualizzatore proprietà se è stata modificata rispetto al valore predefinito.

- L'utente può fare clic con il pulsante destro del mouse sulla proprietà e scegliere **Reimposta** per ripristinare il valore predefinito della proprietà.

- La finestra di progettazione genera codice più efficiente.

> [!NOTE]
> Applicare <xref:System.ComponentModel.DefaultValueAttribute> o fornire i metodi `Reset` *PropertyName* e `ShouldSerialize` *PropertyName* . Non usare entrambi.

Quando si dichiara un `ShouldSerialize` `Reset` metodo o, usare il `private` modificatore di accesso. Questi metodi vengono in genere richiamati dalla finestra di progettazione e non dal codice utente.

 Il `Reset` metodo *PropertyName* imposta una proprietà sul relativo valore predefinito, come illustrato nel frammento di codice seguente.

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
> Se una proprietà non dispone di un `Reset` metodo, non è contrassegnata con un oggetto <xref:System.ComponentModel.DefaultValueAttribute> e non dispone di un valore predefinito specificato nella relativa dichiarazione, l' `Reset` opzione per tale proprietà è disabilitata nel menu di scelta rapida della finestra **Proprietà** del progettazione Windows Form in Visual Studio.

 Le finestre di progettazione, ad esempio Visual Studio, usano il `ShouldSerialize` metodo *PropertyName* per verificare se una proprietà è cambiata rispetto al valore predefinito e scrivere codice nel form solo se una proprietà viene modificata, consentendo così una generazione di codice più efficiente. Esempio:

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
> Se si desidera impedire in modo permanente la serializzazione di una proprietà da parte della finestra di progettazione, aggiungere l'attributo [DesignerSerializationVisibility](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) con il valore di `Hidden` .

 Di seguito è riportato un esempio di codice completo.

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

 In questo caso, anche quando il valore della variabile privata a cui si accede tramite la `MyFont` proprietà è `null` , il Visualizzatore proprietà non viene visualizzato; in caso `null` contrario, Visualizza la <xref:System.Windows.Forms.Control.Font%2A> proprietà dell'elemento padre, in caso contrario `null` , o il <xref:System.Windows.Forms.Control.Font%2A> valore predefinito definito in <xref:System.Windows.Forms.Control> . Pertanto, il valore predefinito di `MyFont` non può essere semplicemente impostato e <xref:System.ComponentModel.DefaultValueAttribute> non è possibile applicare un oggetto a questa proprietà. Al contrario, `ShouldSerialize` `Reset` è necessario implementare i metodi e per la `MyFont` Proprietà.

## <a name="see-also"></a>Vedere anche

- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Definizione di una proprietà](defining-a-property-in-windows-forms-controls.md)
- [Eventi per proprietà modificate](property-changed-events.md)
- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute?displayProperty=fullName>
