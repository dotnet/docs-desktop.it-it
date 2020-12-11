---
title: 'Procedura: impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: b8dcbec18977d46bd47b82f528deb2eeccc4e441
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965617"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="cd077-102">Procedura: impostare la proprietà di sola lettura per un oggetto Freezable</span><span class="sxs-lookup"><span data-stu-id="cd077-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="cd077-103">Questo esempio illustra come creare un oggetto <xref:System.Windows.Freezable> di sola lettura chiamando il relativo <xref:System.Windows.Freezable.Freeze%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="cd077-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="cd077-104">Non è possibile bloccare un <xref:System.Windows.Freezable> oggetto se si verifica una delle condizioni seguenti `true` per l'oggetto:</span><span class="sxs-lookup"><span data-stu-id="cd077-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="cd077-105">Dispone di proprietà animate o con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="cd077-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="cd077-106">Dispone di proprietà impostate da una risorsa dinamica.</span><span class="sxs-lookup"><span data-stu-id="cd077-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="cd077-107">Per ulteriori informazioni sulle risorse dinamiche, vedere le [risorse XAML](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span><span class="sxs-lookup"><span data-stu-id="cd077-107">For more information about dynamic resources, see the [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span></span>  
  
- <span data-ttu-id="cd077-108">Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="cd077-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="cd077-109">Se queste condizioni si riferiscono all' `false` <xref:System.Windows.Freezable> oggetto e non si intende modificarlo, provare a bloccarlo per ottenere vantaggi in termini di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="cd077-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd077-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd077-110">Example</span></span>  
 <span data-ttu-id="cd077-111">Nell'esempio seguente viene bloccato un <xref:System.Windows.Media.SolidColorBrush> oggetto, che è un tipo di <xref:System.Windows.Freezable> oggetto.</span><span class="sxs-lookup"><span data-stu-id="cd077-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="cd077-112">Per ulteriori informazioni sugli <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cd077-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd077-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd077-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="cd077-114">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="cd077-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="cd077-115">Procedure</span><span class="sxs-lookup"><span data-stu-id="cd077-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
