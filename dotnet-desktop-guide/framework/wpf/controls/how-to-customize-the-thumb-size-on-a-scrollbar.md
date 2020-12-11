---
title: 'Procedura: personalizzare le dimensioni del cursore in una barra di scorrimento'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968629"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="27502-102">Procedura: personalizzare le dimensioni del cursore in una barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="27502-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="27502-103">In questo argomento viene illustrato come impostare l'oggetto <xref:System.Windows.Controls.Primitives.Thumb> di un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> su una dimensione fissa e come specificare una dimensione minima per l'oggetto <xref:System.Windows.Controls.Primitives.Thumb> di un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> .</span><span class="sxs-lookup"><span data-stu-id="27502-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27502-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="27502-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="27502-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27502-105">Description</span></span>  
 <span data-ttu-id="27502-106">Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> con una dimensione fissa.</span><span class="sxs-lookup"><span data-stu-id="27502-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="27502-107">Nell'esempio viene impostata la <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> proprietà di <xref:System.Windows.Controls.Primitives.Thumb> su <xref:System.Double.NaN> e viene impostata l'altezza di <xref:System.Windows.Controls.Primitives.Thumb> .</span><span class="sxs-lookup"><span data-stu-id="27502-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="27502-108">Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con una <xref:System.Windows.Controls.Primitives.Thumb> larghezza fissa, impostare la larghezza di <xref:System.Windows.Controls.Primitives.Thumb> .</span><span class="sxs-lookup"><span data-stu-id="27502-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="27502-109">Codice</span><span class="sxs-lookup"><span data-stu-id="27502-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="27502-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27502-110">Description</span></span>  
 <span data-ttu-id="27502-111">Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> con una dimensione minima.</span><span class="sxs-lookup"><span data-stu-id="27502-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="27502-112">Nell'esempio viene impostato il valore di <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A> .</span><span class="sxs-lookup"><span data-stu-id="27502-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="27502-113">Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con una <xref:System.Windows.Controls.Primitives.Thumb> larghezza minima, impostare la <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A> .</span><span class="sxs-lookup"><span data-stu-id="27502-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="27502-114">Codice</span><span class="sxs-lookup"><span data-stu-id="27502-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="27502-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27502-115">See also</span></span>

- [<span data-ttu-id="27502-116">Stili e modelli di ScrollBar</span><span class="sxs-lookup"><span data-stu-id="27502-116">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
