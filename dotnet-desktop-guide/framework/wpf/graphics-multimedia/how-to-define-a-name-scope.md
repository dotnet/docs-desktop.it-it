---
title: 'Procedura: definire un ambito del nome'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: a03f477dd31909e8cb9dde9cd29da6f38d665758
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951591"
---
# <a name="how-to-define-a-name-scope"></a><span data-ttu-id="493c5-102">Procedura: definire un ambito del nome</span><span class="sxs-lookup"><span data-stu-id="493c5-102">How to: Define a Name Scope</span></span>
<span data-ttu-id="493c5-103">Per eseguire un'animazione con <xref:System.Windows.Media.Animation.Storyboard> nel codice, è necessario creare <xref:System.Windows.NameScope> e registrare i nomi degli oggetti di destinazione con l'elemento proprietario dell'ambito del nome.</span><span class="sxs-lookup"><span data-stu-id="493c5-103">To animate with <xref:System.Windows.Media.Animation.Storyboard> in code, you must create a <xref:System.Windows.NameScope> and register the target objects' names with the element that owns that name scope.</span></span> <span data-ttu-id="493c5-104">Nell'esempio seguente <xref:System.Windows.NameScope> viene creato un oggetto per `myMainPanel` .</span><span class="sxs-lookup"><span data-stu-id="493c5-104">In the following example, a <xref:System.Windows.NameScope> is created for `myMainPanel`.</span></span> <span data-ttu-id="493c5-105">Due pulsanti, `button1` e `button2` , vengono aggiunti al pannello e i relativi nomi sono registrati.</span><span class="sxs-lookup"><span data-stu-id="493c5-105">Two buttons, `button1` and `button2`, are added to the panel, and their names registered.</span></span> <span data-ttu-id="493c5-106">Vengono create diverse animazioni e una <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="493c5-106">Several animations and a <xref:System.Windows.Media.Animation.Storyboard> are created.</span></span> <span data-ttu-id="493c5-107">Il metodo dello storyboard <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> viene usato per avviare le animazioni.</span><span class="sxs-lookup"><span data-stu-id="493c5-107">The storyboard's <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method is used to start the animations.</span></span>  
  
 <span data-ttu-id="493c5-108">Poiché `button1` , `button2` e `myMainPanel` condividono tutti lo stesso ambito dei nomi, è possibile usare uno qualsiasi di essi con il <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo per avviare le animazioni.</span><span class="sxs-lookup"><span data-stu-id="493c5-108">Because `button1`, `button2`, and `myMainPanel` all share the same name scope, any one of them can be used with the <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method to start the animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="493c5-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="493c5-109">Example</span></span>  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="493c5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="493c5-110">See also</span></span>

- [<span data-ttu-id="493c5-111">Aggiungere un'animazione a una proprietà usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="493c5-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="493c5-112">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="493c5-112">Animation Overview</span></span>](animation-overview.md)
