---
title: 'Procedura: Creare un oggetto Solid Brush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: ed9ec1f52b41c83b3cc6e36dedf97f1c00db42e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952134"
---
# <a name="how-to-create-a-solid-brush"></a><span data-ttu-id="cc529-102">Procedura: Creare un oggetto Solid Brush</span><span class="sxs-lookup"><span data-stu-id="cc529-102">How to: Create a Solid Brush</span></span>
<span data-ttu-id="cc529-103">In questo esempio viene creato un <xref:System.Drawing.SolidBrush> oggetto che può essere utilizzato da un <xref:System.Drawing.Graphics> oggetto per il riempimento di forme.</span><span class="sxs-lookup"><span data-stu-id="cc529-103">This example creates a <xref:System.Drawing.SolidBrush> object that can be used by a <xref:System.Drawing.Graphics> object for filling shapes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc529-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc529-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="cc529-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="cc529-105">Robust Programming</span></span>  
 <span data-ttu-id="cc529-106">Al termine dell'utilizzo, è necessario chiamare <xref:System.IDisposable.Dispose%2A> sugli oggetti che utilizzano risorse di sistema, ad esempio gli oggetti pennello.</span><span class="sxs-lookup"><span data-stu-id="cc529-106">After you have finished using them, you should call <xref:System.IDisposable.Dispose%2A> on objects that consume system resources, such as brush objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc529-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc529-107">See also</span></span>

- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="cc529-108">Guida introduttiva alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="cc529-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="cc529-109">Pennelli e forme con riempimento in GDI+</span><span class="sxs-lookup"><span data-stu-id="cc529-109">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
- [<span data-ttu-id="cc529-110">Utilizzo di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="cc529-110">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
