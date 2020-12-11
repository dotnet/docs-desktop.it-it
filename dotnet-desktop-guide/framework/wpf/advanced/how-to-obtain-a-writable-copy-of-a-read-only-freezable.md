---
title: 'Procedura: ottenere una copia scrivibile di un oggetto Freezable di sola lettura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968419"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="32209-102">Procedura: ottenere una copia scrivibile di un oggetto Freezable di sola lettura</span><span class="sxs-lookup"><span data-stu-id="32209-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="32209-103">Questo esempio illustra come usare il <xref:System.Windows.Freezable.Clone%2A> metodo per creare una copia scrivibile di un oggetto di sola lettura <xref:System.Windows.Freezable> .</span><span class="sxs-lookup"><span data-stu-id="32209-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="32209-104">Dopo che un <xref:System.Windows.Freezable> oggetto è stato contrassegnato come di sola lettura ("bloccato"), non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="32209-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="32209-105">Tuttavia, è possibile usare il <xref:System.Windows.Freezable.Clone%2A> metodo per creare un clone modificabile dell'oggetto bloccato.</span><span class="sxs-lookup"><span data-stu-id="32209-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32209-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="32209-106">Example</span></span>  
 <span data-ttu-id="32209-107">Nell'esempio seguente viene creato un clone modificabile di un <xref:System.Windows.Media.SolidColorBrush> oggetto bloccato.</span><span class="sxs-lookup"><span data-stu-id="32209-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="32209-108">Per ulteriori informazioni sugli <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="32209-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32209-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32209-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="32209-110">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="32209-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="32209-111">Procedure</span><span class="sxs-lookup"><span data-stu-id="32209-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
