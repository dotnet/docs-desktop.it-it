---
title: 'Procedura: migliorare le prestazioni di scorrimento di un controllo ListBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966640"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="31a41-102">Procedura: migliorare le prestazioni di scorrimento di un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="31a41-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="31a41-103">Se un oggetto <xref:System.Windows.Controls.ListBox> contiene molti elementi, la risposta dell'interfaccia utente può essere lenta quando un utente scorre l'oggetto <xref:System.Windows.Controls.ListBox> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="31a41-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="31a41-104">È possibile migliorare le prestazioni di <xref:System.Windows.Controls.ListBox> quando l'utente scorre impostando la `VirtualizingStackPanel.VirtualizationMode` proprietà associata su <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="31a41-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31a41-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="31a41-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="31a41-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31a41-106">Description</span></span>  
<span data-ttu-id="31a41-107">Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.ListBox> e la `VirtualizingStackPanel.VirtualizationMode` proprietà associata viene impostata su <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per migliorare le prestazioni durante lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="31a41-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="31a41-108">Codice</span><span class="sxs-lookup"><span data-stu-id="31a41-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="31a41-109">Nell'esempio seguente vengono illustrati i dati utilizzati nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="31a41-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
