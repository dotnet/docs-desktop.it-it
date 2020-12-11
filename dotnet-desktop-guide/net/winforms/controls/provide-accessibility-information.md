---
title: Aggiunta di informazioni per l'Accesso facilitato ai controlli in un Windows Form
description: Informazioni su come aggiungere informazioni di accessibilità a un controllo. Windows Forms consente di aggiungere le impostazioni di accessibilità a un controllo per aiutare gli utenti con particolari esigenze.
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
ms.openlocfilehash: 27c06a7d01cb98ecb2f7216c09dc292d2fe68a6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968791"
---
# <a name="providing-accessibility-information-for-controls-windows-forms-net"></a>Fornire informazioni sull'accessibilità per i controlli (Windows Forms .NET)

Gli strumenti per l'accessibilità sono dispositivi e programmi specializzati che consentono agli utenti con disabilità di usare i computer in modo più efficace. Sono incluse, ad esempio, le utilità per la lettura dello schermo per gli utenti non vedenti e le utilità di input vocale per le persone che usano i comandi vocali anziché il mouse o la tastiera. Gli strumenti per l'accessibilità interagiscono con le proprietà di accessibilità esposte dai controlli Windows Form. Le proprietà sono riportate di seguito:

- <xref:System.Windows.Forms.AccessibleObject?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=fullName>
- <xref:System.Windows.Forms.AccessibleRole?displayProperty=fullName>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessibilityobject-property"></a>Proprietà AccessibilityObject

Questa proprietà di sola lettura contiene un'istanza della <xref:System.Windows.Forms.AccessibleObject> . `AccessibleObject`Implementa l' <xref:Accessibility.IAccessible> interfaccia, che fornisce informazioni sulla descrizione del controllo, la posizione dello schermo, le funzionalità di spostamento e il valore. La finestra di progettazione imposta questo valore quando il controllo viene aggiunto al form.

## <a name="accessibledefaultactiondescription-property"></a>Proprietà AccessibleDefaultActionDescription

Questa stringa descrive l'azione del controllo. Non è visualizzata nella finestra Proprietà e può essere impostata solo nel codice. Nell'esempio seguente viene impostata la <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> proprietà per un controllo Button:

```vb
Button1.AccessibleDefaultActionDescription = "Closes the application."
```

```csharp
button1.AccessibleDefaultActionDescription = "Closes the application.";
```

## <a name="accessibledescription-property"></a>Proprietà AccessibleDescription

Questa stringa descrive il controllo. La <xref:System.Windows.Forms.Control.AccessibleDescription> proprietà può essere impostata nell'finestra proprietà o nel codice come indicato di seguito:

```vb
Button1.AccessibleDescription = "A button with text 'Exit'."
```

```csharp
button1.AccessibleDescription = "A button with text 'Exit'";
```

## <a name="accessiblename-property"></a>Proprietà AccessibleName

Questa stringa rappresenta il nome di un controllo segnalato agli strumenti di accessibilità. La <xref:System.Windows.Forms.Control.AccessibleName> proprietà può essere impostata nell'finestra proprietà o nel codice come indicato di seguito:

```vb
Button1.AccessibleName = "Order"
```

```csharp
button1.AccessibleName = "Order";
```

## <a name="accessiblerole-property"></a>Proprietà AccessibleRole

Questa proprietà, che contiene una <xref:System.Windows.Forms.AccessibleRole> descrive il ruolo di interfaccia utente del controllo. Per un nuovo controllo il valore è impostato su `Default`. Ciò significa che, per impostazione predefinita, un `Button` controllo funge da `Button` . È consigliabile reimpostare questa proprietà se il controllo ha un altro ruolo. Ad esempio, è possibile usare un `PictureBox` controllo come `Chart` ed è possibile che gli strumenti di accessibilità segnalino il ruolo come `Chart` , non come `PictureBox` . È anche consigliabile specificare questa proprietà per eventuali controlli personalizzati sviluppati. La proprietà può essere impostata nella finestra Proprietà o nel codice, come illustrato di seguito:

```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart
```

```csharp
pictureBox1.AccessibleRole = AccessibleRole.Chart;
```

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul controllo Label (Windows Forms .NET)](labels.md)
- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
