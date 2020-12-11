---
title: 'Procedura: definire una penna'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
ms.openlocfilehash: 1d69a40604dbf2f7a73c17279ae946faeb6c634a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963463"
---
# <a name="how-to-define-a-pen"></a><span data-ttu-id="6338e-102">Procedura: definire una penna</span><span class="sxs-lookup"><span data-stu-id="6338e-102">How to: Define a Pen</span></span>
<span data-ttu-id="6338e-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.Pen> per delineare una forma.</span><span class="sxs-lookup"><span data-stu-id="6338e-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="6338e-104">Per creare un semplice <xref:System.Windows.Media.Pen> , è necessario specificare solo i relativi <xref:System.Windows.Media.Pen.Thickness%2A> e <xref:System.Windows.Media.Pen.Brush%2A> .</span><span class="sxs-lookup"><span data-stu-id="6338e-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="6338e-105">È possibile creare penne più complesse specificando un,, <xref:System.Windows.Media.Pen.DashStyle%2A> <xref:System.Windows.Media.Pen.DashCap%2A> <xref:System.Windows.Media.Pen.LineJoin%2A> , <xref:System.Windows.Media.Pen.StartLineCap%2A> e <xref:System.Windows.Media.Pen.EndLineCap%2A> .</span><span class="sxs-lookup"><span data-stu-id="6338e-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6338e-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6338e-106">Example</span></span>  
 <span data-ttu-id="6338e-107">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Pen> per delineare una forma definita da un oggetto <xref:System.Windows.Media.GeometryDrawing> .</span><span class="sxs-lookup"><span data-stu-id="6338e-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="6338e-108">![Strutture prodotte da un oggetto Pen](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="6338e-108">![Outlines produces by a Pen](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="6338e-109">GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="6338e-109">A GeometryDrawing</span></span>
