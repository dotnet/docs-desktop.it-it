---
title: 'Procedura: Specificare voci di menu standard per un modulo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: a95476ff3d182bf2a56e6527c9ee83c8c56af246
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961705"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="5b549-102">Procedura: Specificare voci di menu standard per un modulo</span><span class="sxs-lookup"><span data-stu-id="5b549-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="5b549-103">È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="5b549-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="5b549-104">In Visual Studio è disponibile un supporto completo per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5b549-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="5b549-105">Vedere anche [Procedura dettagliata: Inserimento di voci di menu standard in un modulo](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="5b549-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b549-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b549-106">Example</span></span>  
 <span data-ttu-id="5b549-107">L'esempio di codice seguente illustra come usare un controllo <xref:System.Windows.Forms.MenuStrip> per creare un form con un menu standard.</span><span class="sxs-lookup"><span data-stu-id="5b549-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="5b549-108">Le selezioni delle voci di menu vengono visualizzate in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="5b549-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b549-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5b549-109">Compiling the Code</span></span>  
 <span data-ttu-id="5b549-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b549-110">This example requires:</span></span>  
  
- <span data-ttu-id="5b549-111">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5b549-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b549-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b549-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="5b549-113">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="5b549-113">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
