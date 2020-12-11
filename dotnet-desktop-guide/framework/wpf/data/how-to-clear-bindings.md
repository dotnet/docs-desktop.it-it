---
title: 'Procedura: cancellare associazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: ab89c185d1b45ab49e680135ca4c1d54395fe0f4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966634"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="8f1fc-102">Procedura: cancellare associazioni</span><span class="sxs-lookup"><span data-stu-id="8f1fc-102">How to: Clear Bindings</span></span>
<span data-ttu-id="8f1fc-103">Questo esempio illustra come cancellare le associazioni da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f1fc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f1fc-104">Example</span></span>  
 <span data-ttu-id="8f1fc-105">Per cancellare un'associazione da una singola proprietà in un oggetto, chiamare <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="8f1fc-106">Nell'esempio seguente viene rimossa l'associazione dall' <xref:System.Windows.Controls.TextBlock.TextProperty> oggetto di *testo*, un <xref:System.Windows.Controls.TextBlock> oggetto.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="8f1fc-107">La cancellazione rimuove l'associazione in modo che il valore della proprietà di dipendenza venga modificato in quello avrebbe assunto senza l'associazione.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="8f1fc-108">Questo valore potrebbe essere un valore predefinito, un valore ereditato o un valore ottenuto da un'associazione di modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="8f1fc-109">Per cancellare i binding da tutte le possibili proprietà di un oggetto, usare <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A> .</span><span class="sxs-lookup"><span data-stu-id="8f1fc-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f1fc-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f1fc-110">See also</span></span>

- <xref:System.Windows.Data.BindingOperations>
- [<span data-ttu-id="8f1fc-111">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="8f1fc-111">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="8f1fc-112">Procedure</span><span class="sxs-lookup"><span data-stu-id="8f1fc-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
