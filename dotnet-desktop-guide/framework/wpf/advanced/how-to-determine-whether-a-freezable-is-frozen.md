---
title: 'Procedura: determinare se un oggetto Freezable è bloccato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964975"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="8719e-102">Procedura: determinare se un oggetto Freezable è bloccato</span><span class="sxs-lookup"><span data-stu-id="8719e-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="8719e-103">Questo esempio illustra come determinare se un <xref:System.Windows.Freezable> oggetto è bloccato.</span><span class="sxs-lookup"><span data-stu-id="8719e-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="8719e-104">Se si tenta di modificare un <xref:System.Windows.Freezable> oggetto bloccato, viene generata un'eccezione <xref:System.InvalidOperationException> .</span><span class="sxs-lookup"><span data-stu-id="8719e-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="8719e-105">Per evitare di generare questa eccezione, utilizzare la <xref:System.Windows.Freezable.IsFrozen%2A> proprietà dell' <xref:System.Windows.Freezable> oggetto per determinare se è bloccata.</span><span class="sxs-lookup"><span data-stu-id="8719e-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8719e-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8719e-106">Example</span></span>  
 <span data-ttu-id="8719e-107">Nell'esempio seguente viene bloccato un oggetto <xref:System.Windows.Media.SolidColorBrush> , quindi viene testato utilizzando la <xref:System.Windows.Freezable.IsFrozen%2A> proprietà per determinare se è bloccato.</span><span class="sxs-lookup"><span data-stu-id="8719e-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="8719e-108">Per ulteriori informazioni sugli <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8719e-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8719e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8719e-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="8719e-110">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="8719e-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="8719e-111">Procedure</span><span class="sxs-lookup"><span data-stu-id="8719e-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
