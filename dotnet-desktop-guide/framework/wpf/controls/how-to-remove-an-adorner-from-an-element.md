---
title: 'Procedura: rimuovere uno strumento decorativo da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966175"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="1627f-102">Procedura: rimuovere uno strumento decorativo da un elemento</span><span class="sxs-lookup"><span data-stu-id="1627f-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="1627f-103">Questo esempio Mostra come rimuovere a livello di codice uno strumento decorativo specifico da un oggetto specificato <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="1627f-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1627f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1627f-104">Example</span></span>  
 <span data-ttu-id="1627f-105">Questo esempio di codice dettagliato rimuove il primo strumento decorativo nella matrice degli Adorner restituiti da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> .</span><span class="sxs-lookup"><span data-stu-id="1627f-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="1627f-106">Questo esempio si verifica per recuperare gli strumenti decorativi in un oggetto <xref:System.Windows.UIElement> denominato *TextBox*.</span><span class="sxs-lookup"><span data-stu-id="1627f-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="1627f-107">Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di strumenti decorativi, `null` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="1627f-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="1627f-108">Questo codice verifica in modo esplicito la presenza di una matrice null ed è ideale per le applicazioni in cui è prevista una matrice null relativamente comune.</span><span class="sxs-lookup"><span data-stu-id="1627f-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="1627f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1627f-109">Example</span></span>  
 <span data-ttu-id="1627f-110">Questo esempio di codice condensato è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1627f-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="1627f-111">Questo codice non verifica in modo esplicito la presenza di una matrice null, pertanto è possibile che venga <xref:System.NullReferenceException> generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1627f-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="1627f-112">Questo codice è ideale per le applicazioni in cui è prevista una matrice di valori null.</span><span class="sxs-lookup"><span data-stu-id="1627f-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="1627f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1627f-113">See also</span></span>

- [<span data-ttu-id="1627f-114">Cenni preliminari sugli strumenti decorativi visuali</span><span class="sxs-lookup"><span data-stu-id="1627f-114">Adorners Overview</span></span>](adorners-overview.md)
