---
title: Disegno e rendering di controlli personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 14abac5678bfffa3cdb61307fd3cb54681c82a99
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951130"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="107ed-102">Disegno e rendering di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="107ed-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="107ed-103">Il disegno personalizzato dei controlli è una delle numerose attività complesse semplificate dal .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="107ed-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="107ed-104">Quando si crea un controllo personalizzato, sono disponibili molte opzioni relative all'aspetto grafico del controllo.</span><span class="sxs-lookup"><span data-stu-id="107ed-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="107ed-105">Se si crea un controllo che eredita da `Control` , è necessario fornire il codice che consente al controllo di eseguire il rendering della relativa rappresentazione grafica.</span><span class="sxs-lookup"><span data-stu-id="107ed-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="107ed-106">Se si sta creando un controllo utente ereditando da `UserControl` o ereditando da uno dei controlli di Windows Forms, è possibile eseguire l'override della rappresentazione grafica standard e fornire il proprio codice grafico.</span><span class="sxs-lookup"><span data-stu-id="107ed-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="107ed-107">Se si desidera fornire il rendering personalizzato per i controlli costitutivi di un oggetto `UserControl` che si sta creando, le opzioni diventano più limitate, ma consentono comunque un'ampia gamma di possibilità grafiche per i controlli e le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="107ed-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="107ed-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="107ed-108">In This Section</span></span>  
 [<span data-ttu-id="107ed-109">Rendering di un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="107ed-109">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)  
 <span data-ttu-id="107ed-110">Viene illustrato come programmare la logica che visualizza un controllo.</span><span class="sxs-lookup"><span data-stu-id="107ed-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="107ed-111">Controlli creati dall'utente</span><span class="sxs-lookup"><span data-stu-id="107ed-111">User-Drawn Controls</span></span>](user-drawn-controls.md)  
 <span data-ttu-id="107ed-112">Fornisce una panoramica dei passaggi necessari per scrivere ed eseguire l'override del codice di rendering per il controllo.</span><span class="sxs-lookup"><span data-stu-id="107ed-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="107ed-113">Controlli costitutivi</span><span class="sxs-lookup"><span data-stu-id="107ed-113">Constituent Controls</span></span>](constituent-controls.md)  
 <span data-ttu-id="107ed-114">Viene descritto come implementare il codice di rendering personalizzato per i controlli costitutivi nei form e nei controlli utente.</span><span class="sxs-lookup"><span data-stu-id="107ed-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="107ed-115">Procedura: Rendere invisibile il controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="107ed-115">How to: Make Your Control Invisible at Run Time</span></span>](how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="107ed-116">Viene illustrato come utilizzare la <xref:System.Windows.Forms.Control.Visible%2A> proprietà per nascondere e visualizzare un controllo.</span><span class="sxs-lookup"><span data-stu-id="107ed-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="107ed-117">Procedura: Assegnare uno sfondo trasparente al controllo</span><span class="sxs-lookup"><span data-stu-id="107ed-117">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="107ed-118">Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per creare un colore di sfondo opaco, trasparente o parzialmente trasparente.</span><span class="sxs-lookup"><span data-stu-id="107ed-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="107ed-119">Rendering dei controlli con stili visivi</span><span class="sxs-lookup"><span data-stu-id="107ed-119">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="107ed-120">Viene illustrato come eseguire il rendering dei controlli utilizzando gli stili di visualizzazione nei sistemi operativi che li supportano.</span><span class="sxs-lookup"><span data-stu-id="107ed-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="107ed-121">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="107ed-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="107ed-122">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="107ed-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="107ed-123">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="107ed-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="107ed-124">Descrive questo metodo.</span><span class="sxs-lookup"><span data-stu-id="107ed-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="107ed-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="107ed-125">Related Sections</span></span>  
 [<span data-ttu-id="107ed-126">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="107ed-126">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="107ed-127">Introduce la funzionalità grafica GDI+ dal punto di vista di Visual Studio e fornisce collegamenti ad altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="107ed-127">Introduces GDI+ graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="107ed-128">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="107ed-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="107ed-129">Descrive i tipi di controlli personalizzati che è possibile creare.</span><span class="sxs-lookup"><span data-stu-id="107ed-129">Describes the kinds of custom controls you can author.</span></span>
