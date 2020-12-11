---
title: 'Procedura: assicurarsi che GridSplitter sia visibile'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 2085ac5cec206d8692a1267acf132688f0aa9082
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969790"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="3db94-102">Procedura: assicurarsi che GridSplitter sia visibile</span><span class="sxs-lookup"><span data-stu-id="3db94-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="3db94-103">Questo esempio illustra come verificare che un <xref:System.Windows.Controls.GridSplitter> controllo non sia nascosto dagli altri controlli di un oggetto <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="3db94-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3db94-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3db94-104">Example</span></span>  
 <span data-ttu-id="3db94-105"><xref:System.Windows.Controls.Panel.Children%2A>Viene eseguito il rendering dell'oggetto di un <xref:System.Windows.Controls.Grid> controllo nell'ordine in cui sono definiti nel markup o nel codice.</span><span class="sxs-lookup"><span data-stu-id="3db94-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="3db94-106"><xref:System.Windows.Controls.GridSplitter> i controlli possono essere nascosti da altri controlli se non vengono definiti come ultimi elementi della <xref:System.Windows.Controls.Panel.Children%2A> raccolta o se si assegnano altri controlli a un livello superiore <xref:System.Windows.Controls.Panel.ZIndexProperty> .</span><span class="sxs-lookup"><span data-stu-id="3db94-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="3db94-107">Per evitare <xref:System.Windows.Controls.GridSplitter> i controlli nascosti, effettuare una delle operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3db94-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
- <span data-ttu-id="3db94-108">Verificare che <xref:System.Windows.Controls.GridSplitter> i controlli siano l'ultimo <xref:System.Windows.Controls.Panel.Children%2A> aggiunto a <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="3db94-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="3db94-109">Nell'esempio seguente viene illustrato <xref:System.Windows.Controls.GridSplitter> come l'ultimo elemento della <xref:System.Windows.Controls.Panel.Children%2A> raccolta di <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="3db94-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- <span data-ttu-id="3db94-110">Impostare sull'oggetto in modo che <xref:System.Windows.Controls.Panel.ZIndexProperty> <xref:System.Windows.Controls.GridSplitter> sia maggiore di un controllo che altrimenti lo nasconderebbe.</span><span class="sxs-lookup"><span data-stu-id="3db94-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="3db94-111">Nell'esempio seguente il controllo viene assegnato <xref:System.Windows.Controls.GridSplitter> a un livello superiore <xref:System.Windows.Controls.Panel.ZIndexProperty> rispetto al <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="3db94-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- <span data-ttu-id="3db94-112">Impostare i margini sul controllo che altrimenti nasconderebbe in <xref:System.Windows.Controls.GridSplitter> modo che l'oggetto <xref:System.Windows.Controls.GridSplitter> venga esposto.</span><span class="sxs-lookup"><span data-stu-id="3db94-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="3db94-113">Nell'esempio seguente vengono impostati i margini su un controllo che altrimenti verrebbe sovrapposto e nascosto <xref:System.Windows.Controls.GridSplitter> .</span><span class="sxs-lookup"><span data-stu-id="3db94-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="3db94-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3db94-114">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="3db94-115">Procedure</span><span class="sxs-lookup"><span data-stu-id="3db94-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
