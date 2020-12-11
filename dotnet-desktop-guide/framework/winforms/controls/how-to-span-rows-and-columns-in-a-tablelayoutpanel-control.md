---
title: 'Procedura: Estendere un controllo su righe e colonne in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965164"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="e6b0f-102">Procedura: Estendere un controllo su righe e colonne in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="e6b0f-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="e6b0f-103">I controlli in un controllo possono estendersi su <xref:System.Windows.Forms.TableLayoutPanel> righe e colonne adiacenti.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>

## <a name="to-span-columns-and-rows"></a><span data-ttu-id="e6b0f-104">Per estendere le colonne e le righe</span><span class="sxs-lookup"><span data-stu-id="e6b0f-104">To span columns and rows</span></span>

1. <span data-ttu-id="e6b0f-105">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-105">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="e6b0f-106">Trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nella cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="e6b0f-107">Impostare la <xref:System.Windows.Forms.Button> proprietà **ColumnSpan** del controllo su **2**.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-107">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="e6b0f-108">Si noti che il <xref:System.Windows.Forms.Button> controllo si estende sulla prima e sulla seconda colonna.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-108">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>

4. <span data-ttu-id="e6b0f-109">Impostare la <xref:System.Windows.Forms.Button> proprietà **RowSpan** del controllo su **2**.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-109">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="e6b0f-110">Si noti che il <xref:System.Windows.Forms.Button> controllo si estende sulla prima e sulla seconda riga.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-110">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>

5. <span data-ttu-id="e6b0f-111">Impostare la <xref:System.Windows.Forms.Button> proprietà **ColumnSpan** del controllo su **1**.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-111">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="e6b0f-112">Si noti che il <xref:System.Windows.Forms.Button> controllo viene spostato nella prima colonna e si estende alla prima e alla seconda riga.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-112">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6b0f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6b0f-113">See also</span></span>

- [<span data-ttu-id="e6b0f-114">Controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="e6b0f-114">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
