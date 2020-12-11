---
title: "Procedura: creare uno stile per un'intestazione di colonna GridView trascinata"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968128"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="fbb5e-102">Procedura: creare uno stile per un'intestazione di colonna GridView trascinata</span><span class="sxs-lookup"><span data-stu-id="fbb5e-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="fbb5e-103">In questo esempio viene illustrato come modificare l'aspetto di un oggetto trascinato <xref:System.Windows.Controls.GridViewColumnHeader> quando l'utente modifica la posizione di una colonna.</span><span class="sxs-lookup"><span data-stu-id="fbb5e-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbb5e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbb5e-104">Example</span></span>  
 <span data-ttu-id="fbb5e-105">Quando si trascina un'intestazione di colonna in un'altra posizione in un oggetto <xref:System.Windows.Controls.ListView> che utilizza <xref:System.Windows.Controls.GridView> per la modalità di visualizzazione, la colonna viene spostata nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="fbb5e-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="fbb5e-106">Quando si trascina l'intestazione di colonna, viene visualizzata una copia mobile dell'intestazione, oltre all'intestazione originale.</span><span class="sxs-lookup"><span data-stu-id="fbb5e-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="fbb5e-107">Un'intestazione di colonna in un <xref:System.Windows.Controls.GridView> è rappresentata da un <xref:System.Windows.Controls.GridViewColumnHeader> oggetto.</span><span class="sxs-lookup"><span data-stu-id="fbb5e-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="fbb5e-108">Per personalizzare l'aspetto delle intestazioni mobili e originali, è possibile impostare <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> per modificare l'oggetto <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="fbb5e-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="fbb5e-109">Queste <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> vengono applicate quando il <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> valore della proprietà è `true` e il <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> valore della proprietà è <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> .</span><span class="sxs-lookup"><span data-stu-id="fbb5e-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="fbb5e-110">Quando l'utente preme il pulsante del mouse e lo tiene premuto mentre il mouse si posiziona su <xref:System.Windows.Controls.GridViewColumnHeader> , il <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> valore della proprietà viene modificato in `true` .</span><span class="sxs-lookup"><span data-stu-id="fbb5e-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="fbb5e-111">Analogamente, quando l'utente inizia l'operazione di trascinamento, la <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> proprietà viene modificata in <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> .</span><span class="sxs-lookup"><span data-stu-id="fbb5e-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="fbb5e-112">Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> per modificare i <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.Background%2A> colori e delle intestazioni originali e mobili quando l'utente trascina una colonna in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="fbb5e-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="fbb5e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbb5e-113">See also</span></span>

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="fbb5e-114">Procedure</span><span class="sxs-lookup"><span data-stu-id="fbb5e-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="fbb5e-115">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="fbb5e-115">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="fbb5e-116">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="fbb5e-116">GridView Overview</span></span>](gridview-overview.md)
