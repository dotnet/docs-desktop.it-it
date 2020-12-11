---
title: 'Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964006"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="da5bc-102">Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="da5bc-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>

<span data-ttu-id="da5bc-103">È possibile allineare ed estendere i controlli in un oggetto <xref:System.Windows.Forms.TableLayoutPanel> con le <xref:System.Windows.Forms.Control.Anchor%2A> <xref:System.Windows.Forms.Control.Dock%2A> proprietà e.</span><span class="sxs-lookup"><span data-stu-id="da5bc-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>

## <a name="align-and-stretch-a-control"></a><span data-ttu-id="da5bc-104">Allineare ed estendere un controllo</span><span class="sxs-lookup"><span data-stu-id="da5bc-104">Align and stretch a control</span></span>

1. <span data-ttu-id="da5bc-105">In Visual Studio trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo dalla **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="da5bc-105">In Visual Studio, drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="da5bc-106">Trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nella cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="da5bc-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="da5bc-107">Il <xref:System.Windows.Forms.Button> controllo viene centrato nella cella.</span><span class="sxs-lookup"><span data-stu-id="da5bc-107">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>

3. <span data-ttu-id="da5bc-108">Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su `Left,Right` .</span><span class="sxs-lookup"><span data-stu-id="da5bc-108">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="da5bc-109">Il <xref:System.Windows.Forms.Button> controllo si estende in base alla larghezza della cella.</span><span class="sxs-lookup"><span data-stu-id="da5bc-109">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>

4. <span data-ttu-id="da5bc-110">Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su `Top,Bottom` .</span><span class="sxs-lookup"><span data-stu-id="da5bc-110">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="da5bc-111">Il <xref:System.Windows.Forms.Button> controllo si estende in modo da corrispondere all'altezza della cella.</span><span class="sxs-lookup"><span data-stu-id="da5bc-111">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>

5. <span data-ttu-id="da5bc-112">Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill> .</span><span class="sxs-lookup"><span data-stu-id="da5bc-112">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="da5bc-113">Il <xref:System.Windows.Forms.Button> controllo si espande per riempire la cella.</span><span class="sxs-lookup"><span data-stu-id="da5bc-113">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>

6. <span data-ttu-id="da5bc-114">Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.None> .</span><span class="sxs-lookup"><span data-stu-id="da5bc-114">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="da5bc-115">Il <xref:System.Windows.Forms.Button> controllo torna alle dimensioni originali e passa all'angolo superiore sinistro della cella.</span><span class="sxs-lookup"><span data-stu-id="da5bc-115">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="da5bc-116">Il **Progettazione Windows Form** ha impostato la <xref:System.Windows.Forms.Control.Anchor%2A> proprietà su `Top, Left` .</span><span class="sxs-lookup"><span data-stu-id="da5bc-116">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>

7. <span data-ttu-id="da5bc-117">Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su `Bottom,Right` .</span><span class="sxs-lookup"><span data-stu-id="da5bc-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="da5bc-118">Il <xref:System.Windows.Forms.Button> controllo viene spostato nell'angolo inferiore destro della cella.</span><span class="sxs-lookup"><span data-stu-id="da5bc-118">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>

8. <span data-ttu-id="da5bc-119">Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su <xref:System.Windows.Forms.AnchorStyles.None> .</span><span class="sxs-lookup"><span data-stu-id="da5bc-119">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="da5bc-120">Il <xref:System.Windows.Forms.Button> controllo viene spostato al centro della cella.</span><span class="sxs-lookup"><span data-stu-id="da5bc-120">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>

## <a name="see-also"></a><span data-ttu-id="da5bc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da5bc-121">See also</span></span>

- [<span data-ttu-id="da5bc-122">Controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="da5bc-122">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
