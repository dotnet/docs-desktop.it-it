---
title: Sviluppare un controllo composito
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 6887de62857fc260fb53e33f462b07af80658178
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96950986"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="699e1-102">Sviluppare un controllo Windows Forms composito</span><span class="sxs-lookup"><span data-stu-id="699e1-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="699e1-103">È possibile sviluppare un controllo Windows Form composito combinando altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="699e1-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="699e1-104">I controlli compositi che derivano da <xref:System.Web.UI.UserControl> sono denominati controlli utente.</span><span class="sxs-lookup"><span data-stu-id="699e1-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="699e1-105">La classe base, <xref:System.Windows.Forms.UserControl>, fornisce il routing della tastiera per i controlli figlio, garantendo così che i controlli figlio possano ricevere lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="699e1-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="699e1-106">Per un esempio di controllo utente, vedere l' <xref:System.Windows.Forms.UserControl> esempio in [procedura: applicare attributi nei controlli Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="699e1-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="699e1-107">La finestra di progettazione Windows Forms in Visual Studio fornisce supporto avanzato in fase di progettazione per la creazione di controlli utente.</span><span class="sxs-lookup"><span data-stu-id="699e1-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- [<span data-ttu-id="699e1-108">Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="699e1-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="699e1-109">Procedura dettagliata: serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="699e1-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="699e1-110">Procedura dettagliata: eredità da un controllo di Windows Form con Visual C#</span><span class="sxs-lookup"><span data-stu-id="699e1-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="699e1-111">Procedura: Specificare una bitmap nella casella degli strumenti per un controllo</span><span class="sxs-lookup"><span data-stu-id="699e1-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="699e1-112">Procedura: Ereditare da controlli Windows Form esistenti</span><span class="sxs-lookup"><span data-stu-id="699e1-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="699e1-113">Procedura dettagliata: debug di controlli di Windows Form personalizzati in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="699e1-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="699e1-114">Procedura: Ereditare dalla classe Control</span><span class="sxs-lookup"><span data-stu-id="699e1-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="699e1-115">Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="699e1-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="699e1-116">Procedura: allineare un controllo ai bordi dei form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="699e1-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="699e1-117">Procedura: Ereditare dalla classe UserControl</span><span class="sxs-lookup"><span data-stu-id="699e1-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="699e1-118">Procedura: Creare controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="699e1-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="699e1-119">Procedura: Creare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="699e1-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="699e1-120">Procedura dettagliata: modifica di un controllo composito con Visual C #</span><span class="sxs-lookup"><span data-stu-id="699e1-120">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="699e1-121">Procedura dettagliata: creazione di un controllo Windows Forms che sfrutta le funzionalità di Visual Studio Design-Time</span><span class="sxs-lookup"><span data-stu-id="699e1-121">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="699e1-122">[Procedura: Creare un controllo Windows Form che utilizza le funzionalità di progettazione](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="699e1-122">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="699e1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="699e1-123">See also</span></span>

- [<span data-ttu-id="699e1-124">Procedura: Applicare attributi nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="699e1-124">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="699e1-125">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="699e1-125">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="699e1-126">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="699e1-126">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
