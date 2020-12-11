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
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a>Procedura: migliorare le prestazioni di scorrimento di un controllo ListBox
Se un oggetto <xref:System.Windows.Controls.ListBox> contiene molti elementi, la risposta dell'interfaccia utente può essere lenta quando un utente scorre l'oggetto <xref:System.Windows.Controls.ListBox> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento. È possibile migliorare le prestazioni di <xref:System.Windows.Controls.ListBox> quando l'utente scorre impostando la `VirtualizingStackPanel.VirtualizationMode` proprietà associata su <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> .  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.ListBox> e la `VirtualizingStackPanel.VirtualizationMode` proprietà associata viene impostata su <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per migliorare le prestazioni durante lo scorrimento.  
  
## <a name="code"></a>Codice  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 Nell'esempio seguente vengono illustrati i dati utilizzati nell'esempio precedente.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
