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
# <a name="providing-accessibility-information-for-controls-windows-forms-net"></a><span data-ttu-id="02e2b-104">Fornire informazioni sull'accessibilità per i controlli (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="02e2b-104">Providing Accessibility Information for Controls (Windows Forms .NET)</span></span>

<span data-ttu-id="02e2b-105">Gli strumenti per l'accessibilità sono dispositivi e programmi specializzati che consentono agli utenti con disabilità di usare i computer in modo più efficace.</span><span class="sxs-lookup"><span data-stu-id="02e2b-105">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="02e2b-106">Sono incluse, ad esempio, le utilità per la lettura dello schermo per gli utenti non vedenti e le utilità di input vocale per le persone che usano i comandi vocali anziché il mouse o la tastiera.</span><span class="sxs-lookup"><span data-stu-id="02e2b-106">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="02e2b-107">Gli strumenti per l'accessibilità interagiscono con le proprietà di accessibilità esposte dai controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="02e2b-107">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="02e2b-108">Le proprietà sono riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="02e2b-108">These properties are:</span></span>

- <xref:System.Windows.Forms.AccessibleObject?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=fullName>
- <xref:System.Windows.Forms.AccessibleRole?displayProperty=fullName>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessibilityobject-property"></a><span data-ttu-id="02e2b-109">Proprietà AccessibilityObject</span><span class="sxs-lookup"><span data-stu-id="02e2b-109">AccessibilityObject Property</span></span>

<span data-ttu-id="02e2b-110">Questa proprietà di sola lettura contiene un'istanza della <xref:System.Windows.Forms.AccessibleObject> .</span><span class="sxs-lookup"><span data-stu-id="02e2b-110">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="02e2b-111">`AccessibleObject`Implementa l' <xref:Accessibility.IAccessible> interfaccia, che fornisce informazioni sulla descrizione del controllo, la posizione dello schermo, le funzionalità di spostamento e il valore.</span><span class="sxs-lookup"><span data-stu-id="02e2b-111">The `AccessibleObject` implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="02e2b-112">La finestra di progettazione imposta questo valore quando il controllo viene aggiunto al form.</span><span class="sxs-lookup"><span data-stu-id="02e2b-112">The designer sets this value when the control is added to the form.</span></span>

## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="02e2b-113">Proprietà AccessibleDefaultActionDescription</span><span class="sxs-lookup"><span data-stu-id="02e2b-113">AccessibleDefaultActionDescription Property</span></span>

<span data-ttu-id="02e2b-114">Questa stringa descrive l'azione del controllo.</span><span class="sxs-lookup"><span data-stu-id="02e2b-114">This string describes the action of the control.</span></span> <span data-ttu-id="02e2b-115">Non è visualizzata nella finestra Proprietà e può essere impostata solo nel codice.</span><span class="sxs-lookup"><span data-stu-id="02e2b-115">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="02e2b-116">Nell'esempio seguente viene impostata la <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> proprietà per un controllo Button:</span><span class="sxs-lookup"><span data-stu-id="02e2b-116">The following example sets the <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> property for a button control:</span></span>

```vb
Button1.AccessibleDefaultActionDescription = "Closes the application."
```

```csharp
button1.AccessibleDefaultActionDescription = "Closes the application.";
```

## <a name="accessibledescription-property"></a><span data-ttu-id="02e2b-117">Proprietà AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="02e2b-117">AccessibleDescription Property</span></span>

<span data-ttu-id="02e2b-118">Questa stringa descrive il controllo.</span><span class="sxs-lookup"><span data-stu-id="02e2b-118">This string describes the control.</span></span> <span data-ttu-id="02e2b-119">La <xref:System.Windows.Forms.Control.AccessibleDescription> proprietà può essere impostata nell'finestra proprietà o nel codice come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="02e2b-119">The <xref:System.Windows.Forms.Control.AccessibleDescription> property may be set in the Properties window, or in code as follows:</span></span>

```vb
Button1.AccessibleDescription = "A button with text 'Exit'."
```

```csharp
button1.AccessibleDescription = "A button with text 'Exit'";
```

## <a name="accessiblename-property"></a><span data-ttu-id="02e2b-120">Proprietà AccessibleName</span><span class="sxs-lookup"><span data-stu-id="02e2b-120">AccessibleName Property</span></span>

<span data-ttu-id="02e2b-121">Questa stringa rappresenta il nome di un controllo segnalato agli strumenti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="02e2b-121">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="02e2b-122">La <xref:System.Windows.Forms.Control.AccessibleName> proprietà può essere impostata nell'finestra proprietà o nel codice come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="02e2b-122">The <xref:System.Windows.Forms.Control.AccessibleName> property may be set in the Properties window, or in code as follows:</span></span>

```vb
Button1.AccessibleName = "Order"
```

```csharp
button1.AccessibleName = "Order";
```

## <a name="accessiblerole-property"></a><span data-ttu-id="02e2b-123">Proprietà AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="02e2b-123">AccessibleRole Property</span></span>

<span data-ttu-id="02e2b-124">Questa proprietà, che contiene una <xref:System.Windows.Forms.AccessibleRole> descrive il ruolo di interfaccia utente del controllo.</span><span class="sxs-lookup"><span data-stu-id="02e2b-124">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="02e2b-125">Per un nuovo controllo il valore è impostato su `Default`.</span><span class="sxs-lookup"><span data-stu-id="02e2b-125">A new control has the value set to `Default`.</span></span> <span data-ttu-id="02e2b-126">Ciò significa che, per impostazione predefinita, un `Button` controllo funge da `Button` .</span><span class="sxs-lookup"><span data-stu-id="02e2b-126">This would mean that by default, a `Button` control acts as a `Button`.</span></span> <span data-ttu-id="02e2b-127">È consigliabile reimpostare questa proprietà se il controllo ha un altro ruolo.</span><span class="sxs-lookup"><span data-stu-id="02e2b-127">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="02e2b-128">Ad esempio, è possibile usare un `PictureBox` controllo come `Chart` ed è possibile che gli strumenti di accessibilità segnalino il ruolo come `Chart` , non come `PictureBox` .</span><span class="sxs-lookup"><span data-stu-id="02e2b-128">For example, you may be using a `PictureBox` control as a `Chart`, and you may want accessibility aids to report the role as a `Chart`, not as a `PictureBox`.</span></span> <span data-ttu-id="02e2b-129">È anche consigliabile specificare questa proprietà per eventuali controlli personalizzati sviluppati.</span><span class="sxs-lookup"><span data-stu-id="02e2b-129">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="02e2b-130">La proprietà può essere impostata nella finestra Proprietà o nel codice, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="02e2b-130">This property may be set in the Properties window, or in code as follows:</span></span>

```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart
```

```csharp
pictureBox1.AccessibleRole = AccessibleRole.Chart;
```

## <a name="see-also"></a><span data-ttu-id="02e2b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02e2b-131">See also</span></span>

- [<span data-ttu-id="02e2b-132">Cenni preliminari sul controllo Label (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="02e2b-132">Label control overview (Windows Forms .NET)</span></span>](labels.md)
- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
