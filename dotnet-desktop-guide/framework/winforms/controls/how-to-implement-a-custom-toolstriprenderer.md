---
title: 'Procedura: Implementare un oggetto ToolStripRenderer personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: 4a84571bf8b81cd26c864edcd4d313a4009dda16
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961765"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="8ddbe-102">Procedura: Implementare un oggetto ToolStripRenderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="8ddbe-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="8ddbe-103">È possibile personalizzare l'aspetto di un controllo <xref:System.Windows.Forms.ToolStrip> implementando una classe che deriva da <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="8ddbe-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="8ddbe-104">In questo modo è possibile creare un aspetto differente da quello fornito dalle classi <xref:System.Windows.Forms.ToolStripProfessionalRenderer> e <xref:System.Windows.Forms.ToolStripSystemRenderer>.</span><span class="sxs-lookup"><span data-stu-id="8ddbe-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ddbe-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ddbe-105">Example</span></span>  
 <span data-ttu-id="8ddbe-106">L'esempio di codice seguente illustra come implementare una classe <xref:System.Windows.Forms.ToolStripRenderer> personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8ddbe-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="8ddbe-107">In questo esempio, il controllo `GridStrip` implementa un puzzle con elementi scorrevoli, che consente all'utente di spostare gli elementi in un layout di tabella allo scopo di formare un'immagine.</span><span class="sxs-lookup"><span data-stu-id="8ddbe-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="8ddbe-108">Un controllo <xref:System.Windows.Forms.ToolStrip> personalizzato dispone i relativi controlli <xref:System.Windows.Forms.ToolStripButton> in un layout di griglia</span><span class="sxs-lookup"><span data-stu-id="8ddbe-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="8ddbe-109">contenente un'unica cella vuota, nella quale l'utente può spostare un elemento adiacente mediante una semplice operazione di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="8ddbe-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="8ddbe-110">Gli elementi che possono essere spostati vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="8ddbe-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="8ddbe-111">La classe `GridStripRenderer` consente di definire tre componenti relativi all'aspetto del controllo `GridStrip`:</span><span class="sxs-lookup"><span data-stu-id="8ddbe-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
- <span data-ttu-id="8ddbe-112">Bordo di `GridStrip`</span><span class="sxs-lookup"><span data-stu-id="8ddbe-112">`GridStrip` border</span></span>  
  
- <span data-ttu-id="8ddbe-113">Bordo di <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="8ddbe-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
- <span data-ttu-id="8ddbe-114">immagine di <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="8ddbe-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ddbe-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8ddbe-115">Compiling the Code</span></span>  
 <span data-ttu-id="8ddbe-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ddbe-116">This example requires:</span></span>  
  
- <span data-ttu-id="8ddbe-117">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8ddbe-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ddbe-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ddbe-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="8ddbe-119">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8ddbe-119">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
