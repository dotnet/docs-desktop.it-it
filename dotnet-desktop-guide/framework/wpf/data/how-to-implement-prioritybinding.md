---
title: 'Procedura: implementare un oggetto PriorityBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 694679183f92c9737bbdb511b4ebd5a4bf2185f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969703"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="2810a-102">Procedura: implementare un oggetto PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="2810a-102">How to: Implement PriorityBinding</span></span>

<span data-ttu-id="2810a-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Works specificando un elenco di associazioni.</span><span class="sxs-lookup"><span data-stu-id="2810a-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="2810a-104">L'elenco delle associazioni viene ordinato dalla priorità più alta alla priorità più bassa.</span><span class="sxs-lookup"><span data-stu-id="2810a-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="2810a-105">Se l'associazione con la priorità più alta restituisce un valore correttamente quando viene elaborato, non è mai necessario elaborare le altre associazioni nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2810a-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="2810a-106">Il caso in cui il binding con priorità più elevata impiega molto tempo per la valutazione, la successiva priorità più alta che restituisce un valore verrà utilizzata correttamente finché un'associazione di una priorità più alta non restituirà correttamente un valore.</span><span class="sxs-lookup"><span data-stu-id="2810a-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2810a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2810a-107">Example</span></span>  

 <span data-ttu-id="2810a-108">Per illustrare <xref:System.Windows.Data.PriorityBinding> il funzionamento di, l' `AsyncDataSource` oggetto è stato creato con le tre proprietà seguenti: `FastDP` , `SlowerDP` e `SlowestDP` .</span><span class="sxs-lookup"><span data-stu-id="2810a-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="2810a-109">La funzione di accesso get di `FastDP` restituisce il valore del `_fastDP` membro dati.</span><span class="sxs-lookup"><span data-stu-id="2810a-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="2810a-110">La funzione di accesso get di `SlowerDP` attende 3 secondi prima di restituire il valore del `_slowerDP` membro dati.</span><span class="sxs-lookup"><span data-stu-id="2810a-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="2810a-111">La funzione di accesso get di `SlowestDP` attende 5 secondi prima di restituire il valore del `_slowestDP` membro dati.</span><span class="sxs-lookup"><span data-stu-id="2810a-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2810a-112">Questo esempio viene fornito solo per scopi dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="2810a-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="2810a-113">Le linee guida di .NET sconsigliano di definire proprietà che sono più lente rispetto a un set di campi.</span><span class="sxs-lookup"><span data-stu-id="2810a-113">The .NET guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="2810a-114">Per ulteriori informazioni, vedere [scelta tra proprietà e metodi](/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2810a-114">For more information, see [Choosing Between Properties and Methods](/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="2810a-115">La <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà viene associata all'oggetto precedente `AsyncDS` utilizzando <xref:System.Windows.Data.PriorityBinding> :</span><span class="sxs-lookup"><span data-stu-id="2810a-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="2810a-116">Quando il motore di binding elabora gli <xref:System.Windows.Data.Binding> oggetti, inizia con il primo <xref:System.Windows.Data.Binding> , associato alla `SlowestDP` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="2810a-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="2810a-117">Quando <xref:System.Windows.Data.Binding> viene elaborato, il valore non viene restituito correttamente perché è in sospensione per 5 secondi, quindi l' <xref:System.Windows.Data.Binding> elemento successivo viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="2810a-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="2810a-118">Il successivo <xref:System.Windows.Data.Binding> non restituisce correttamente un valore perché è in sospensione per 3 secondi.</span><span class="sxs-lookup"><span data-stu-id="2810a-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="2810a-119">Il motore di associazione viene quindi spostato sull' <xref:System.Windows.Data.Binding> elemento successivo, associato alla `FastDP` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="2810a-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="2810a-120">Viene <xref:System.Windows.Data.Binding> restituito il valore "Fast Value".</span><span class="sxs-lookup"><span data-stu-id="2810a-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="2810a-121"><xref:System.Windows.Controls.TextBlock>Ora viene visualizzato il valore "valore rapido".</span><span class="sxs-lookup"><span data-stu-id="2810a-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="2810a-122">Dopo 3 secondi trascorsi, la `SlowerDP` proprietà restituisce il valore "valore più lento".</span><span class="sxs-lookup"><span data-stu-id="2810a-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="2810a-123"><xref:System.Windows.Controls.TextBlock>Viene quindi visualizzato il valore "valore più lento".</span><span class="sxs-lookup"><span data-stu-id="2810a-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="2810a-124">Dopo 5 secondi trascorsi, la `SlowestDP` proprietà restituisce il valore "valore più lento".</span><span class="sxs-lookup"><span data-stu-id="2810a-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="2810a-125">Tale associazione ha la priorità più alta perché è elencata per prima.</span><span class="sxs-lookup"><span data-stu-id="2810a-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="2810a-126"><xref:System.Windows.Controls.TextBlock>Viene ora visualizzato il valore "valore più lento".</span><span class="sxs-lookup"><span data-stu-id="2810a-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="2810a-127"><xref:System.Windows.Data.PriorityBinding>Per informazioni su ciò che viene considerato un valore restituito correttamente da un'associazione, vedere.</span><span class="sxs-lookup"><span data-stu-id="2810a-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2810a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2810a-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2810a-129">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="2810a-129">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="2810a-130">Procedure</span><span class="sxs-lookup"><span data-stu-id="2810a-130">How-to Topics</span></span>](data-binding-how-to-topics.md)
