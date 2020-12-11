---
title: 'Procedura: implementare strumenti decorativi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965707"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="7f6ce-102">Procedura: implementare strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="7f6ce-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="7f6ce-103">In questo esempio viene illustrata un'implementazione di Adorner minima.</span><span class="sxs-lookup"><span data-stu-id="7f6ce-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="7f6ce-104">Note per gli implementatori</span><span class="sxs-lookup"><span data-stu-id="7f6ce-104">Notes for Implementers</span></span>  
 <span data-ttu-id="7f6ce-105">È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale.</span><span class="sxs-lookup"><span data-stu-id="7f6ce-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="7f6ce-106">Un modo comune per implementare il comportamento di rendering consiste nell'eseguire l'override del <xref:System.Windows.UIElement.OnRender%2A> metodo e usare uno o più <xref:System.Windows.Media.DrawingContext> oggetti per eseguire il rendering degli oggetti visivi dello strumento decorativo in base alle esigenze, come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="7f6ce-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f6ce-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f6ce-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7f6ce-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f6ce-108">Description</span></span>  
 <span data-ttu-id="7f6ce-109">Uno strumento decorativo personalizzato viene creato implementando una classe che eredita dalla <xref:System.Windows.Documents.Adorner> classe astratta.</span><span class="sxs-lookup"><span data-stu-id="7f6ce-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="7f6ce-110">Lo strumento decorativo di esempio decora semplicemente gli angoli di un oggetto <xref:System.Windows.UIElement> con i cerchi eseguendo l'override del <xref:System.Windows.UIElement.OnRender%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="7f6ce-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7f6ce-111">Codice</span><span class="sxs-lookup"><span data-stu-id="7f6ce-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="7f6ce-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f6ce-112">See also</span></span>

- [<span data-ttu-id="7f6ce-113">Cenni preliminari sugli strumenti decorativi visuali</span><span class="sxs-lookup"><span data-stu-id="7f6ce-113">Adorners Overview</span></span>](adorners-overview.md)
