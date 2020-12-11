---
title: 'Procedura: individuare un elemento in base al nome'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: d8f5e9077400d460e2e42638a534bacc656db22f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967867"
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="c372b-102">Procedura: individuare un elemento in base al nome</span><span class="sxs-lookup"><span data-stu-id="c372b-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="c372b-103">Questo esempio descrive come usare il <xref:System.Windows.FrameworkElement.FindName%2A> metodo per trovare un elemento in base al relativo <xref:System.Windows.FrameworkElement.Name%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="c372b-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c372b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c372b-104">Example</span></span>  
 <span data-ttu-id="c372b-105">In questo esempio, il metodo per trovare un determinato elemento in base al nome viene scritto come gestore eventi di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="c372b-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="c372b-106">`stackPanel` oggetto <xref:System.Windows.FrameworkElement.Name%2A> della radice in cui <xref:System.Windows.FrameworkElement> viene eseguita la ricerca e il metodo di esempio indica visivamente l'elemento trovato eseguendone il cast come <xref:System.Windows.Controls.TextBlock> e modificando una delle <xref:System.Windows.Controls.TextBlock> [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] proprietà visibili.</span><span class="sxs-lookup"><span data-stu-id="c372b-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
