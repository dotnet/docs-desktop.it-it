---
title: 'Procedura: rimuovere tutti gli strumenti decorativi visuali da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 8504bb1ec70de188033b2b092bbb66cf9da3dc11
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969742"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="5a418-102">Procedura: rimuovere tutti gli strumenti decorativi visuali da un elemento</span><span class="sxs-lookup"><span data-stu-id="5a418-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="5a418-103">In questo esempio viene illustrato come rimuovere a livello di codice tutti gli strumenti decorativi da un oggetto specificato <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="5a418-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a418-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a418-104">Example</span></span>  
 <span data-ttu-id="5a418-105">Questo esempio di codice dettagliato consente di rimuovere tutti gli strumenti decorativi nella matrice degli Adorner restituiti da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> .</span><span class="sxs-lookup"><span data-stu-id="5a418-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="5a418-106">Questo esempio si verifica per recuperare gli strumenti decorativi in un oggetto <xref:System.Windows.UIElement> denominato *TextBox*.</span><span class="sxs-lookup"><span data-stu-id="5a418-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="5a418-107">Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di strumenti decorativi, `null` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="5a418-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="5a418-108">Questo codice verifica in modo esplicito la presenza di una matrice null ed è ideale per le applicazioni in cui è prevista una matrice null relativamente comune.</span><span class="sxs-lookup"><span data-stu-id="5a418-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="5a418-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a418-109">Example</span></span>  
 <span data-ttu-id="5a418-110">Questo esempio di codice condensato è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5a418-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="5a418-111">Questo codice non verifica in modo esplicito la presenza di una matrice null, pertanto è possibile che venga <xref:System.NullReferenceException> generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a418-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="5a418-112">Questo codice è ideale per le applicazioni in cui è prevista una matrice di valori null.</span><span class="sxs-lookup"><span data-stu-id="5a418-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="5a418-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a418-113">See also</span></span>

- [<span data-ttu-id="5a418-114">Cenni preliminari sugli strumenti decorativi visuali</span><span class="sxs-lookup"><span data-stu-id="5a418-114">Adorners Overview</span></span>](adorners-overview.md)
