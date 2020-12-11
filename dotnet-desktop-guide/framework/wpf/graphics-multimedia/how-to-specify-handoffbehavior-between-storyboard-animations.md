---
title: 'Procedura: specificare HandoffBehavior tra le animazioni storyboard'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: d7129d6a48bdf31dc4953bb450267ad3b38fdd17
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961285"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="189a9-102">Procedura: specificare HandoffBehavior tra le animazioni storyboard</span><span class="sxs-lookup"><span data-stu-id="189a9-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="189a9-103">Questo esempio illustra come specificare il comportamento uniforme tra le animazioni dello storyboard.</span><span class="sxs-lookup"><span data-stu-id="189a9-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="189a9-104">La <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> proprietà di <xref:System.Windows.Media.Animation.BeginStoryboard> specifica il modo in cui le nuove animazioni interagiscono con quelle esistenti già applicate a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="189a9-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="189a9-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="189a9-105">Example</span></span>  
 <span data-ttu-id="189a9-106">Nell'esempio seguente vengono creati due pulsanti che ingrandiscono quando il cursore del mouse viene spostato su di essi e diventano più piccoli quando si sposta il cursore.</span><span class="sxs-lookup"><span data-stu-id="189a9-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="189a9-107">Se si passa il mouse su un pulsante e quindi si rimuove rapidamente il cursore, la seconda animazione verrà applicata prima del completamento della prima.</span><span class="sxs-lookup"><span data-stu-id="189a9-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="189a9-108">Quando due animazioni si sovrappongono come questa, è possibile vedere la differenza tra i <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valori di <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> e <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> .</span><span class="sxs-lookup"><span data-stu-id="189a9-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="189a9-109">Il valore <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina le animazioni sovrapposte che provocano una transizione più uniforme tra le animazioni mentre un valore <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> fa sì che la nuova animazione sostituisca immediatamente l'animazione sovrapposta precedente.</span><span class="sxs-lookup"><span data-stu-id="189a9-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="189a9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="189a9-110">See also</span></span>

- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="189a9-111">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="189a9-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="189a9-112">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="189a9-112">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
