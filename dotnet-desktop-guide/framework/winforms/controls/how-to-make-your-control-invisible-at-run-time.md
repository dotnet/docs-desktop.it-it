---
title: 'Procedura: Rendere invisibile il controllo in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: e9af529541a40a951d6defea180dbbef04c8f3be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952103"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="6166b-102">Procedura: Rendere invisibile il controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="6166b-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="6166b-103">In alcuni casi potrebbe essere necessario creare un controllo utente invisibile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6166b-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="6166b-104">Ad esempio, un controllo che rappresenta una sveglia potrebbe essere invisibile, tranne quando l'allarme è stato emesso.</span><span class="sxs-lookup"><span data-stu-id="6166b-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="6166b-105">Questa operazione viene eseguita facilmente impostando la <xref:System.Windows.Forms.Control.Visible%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6166b-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="6166b-106">Se la <xref:System.Windows.Forms.Control.Visible%2A> proprietà è `true` , il controllo verrà visualizzato come normale.</span><span class="sxs-lookup"><span data-stu-id="6166b-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="6166b-107">Se `false` , il controllo sarà nascosto.</span><span class="sxs-lookup"><span data-stu-id="6166b-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="6166b-108">Sebbene il codice nel controllo possa essere ancora eseguito mentre è invisibile, non sarà possibile interagire con il controllo tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6166b-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="6166b-109">Se si desidera creare un controllo invisibile che ancora risponde all'input dell'utente, ad esempio clic del mouse, è necessario creare un controllo trasparente.</span><span class="sxs-lookup"><span data-stu-id="6166b-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="6166b-110">Per ulteriori informazioni, vedere [assegnazione di uno sfondo trasparente al controllo](how-to-give-your-control-a-transparent-background.md).</span><span class="sxs-lookup"><span data-stu-id="6166b-110">For more information, see [Giving Your Control a Transparent Background](how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="6166b-111">Per rendere invisibile il controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="6166b-111">To make your control invisible at run time</span></span>  
  
1. <span data-ttu-id="6166b-112">Impostare la proprietà <xref:System.Windows.Forms.Control.Visible%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="6166b-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6166b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6166b-113">See also</span></span>

- <xref:System.Windows.Forms.Control.Visible%2A>
- [<span data-ttu-id="6166b-114">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6166b-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="6166b-115">Procedura: Assegnare uno sfondo trasparente al controllo</span><span class="sxs-lookup"><span data-stu-id="6166b-115">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)
