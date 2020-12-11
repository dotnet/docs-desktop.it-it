---
title: 'Procedura: associare una visualizzazione struttura ad albero a dati di profondità non determinabile'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: 3d9d082b712750d66c63ae0a309afb9cd3c9b4d8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961408"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Procedura: associare una visualizzazione struttura ad albero a dati di profondità non determinabile
A volte può essere necessario associare un oggetto <xref:System.Windows.Controls.TreeView> a un'origine dati la cui profondità non è nota.  Questo problema può verificarsi quando i dati sono di natura ricorsiva, ad esempio un file system, in cui le cartelle possono contenere cartelle o la struttura organizzativa di una società, in cui i dipendenti hanno altri dipendenti come report diretti.  
  
 L'origine dati deve disporre di un modello a oggetti gerarchico. Una classe, ad esempio, `Employee` può contenere una raccolta di oggetti Employee che sono i dipendenti diretti di un dipendente. Se i dati sono rappresentati in modo non gerarchico, è necessario compilare una rappresentazione gerarchica dei dati.  
  
 Quando si imposta la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> proprietà e se <xref:System.Windows.Controls.ItemsControl> genera un <xref:System.Windows.Controls.ItemsControl> per ogni elemento figlio, l'elemento figlio <xref:System.Windows.Controls.ItemsControl> Usa lo stesso oggetto <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> padre. Se, ad esempio, si imposta la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà su un oggetto associato <xref:System.Windows.Controls.TreeView> a dati, ogni <xref:System.Windows.Controls.TreeViewItem> generato utilizza l'oggetto <xref:System.Windows.DataTemplate> assegnato alla <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà di <xref:System.Windows.Controls.TreeView> .  
  
 <xref:System.Windows.HierarchicalDataTemplate>Consente di specificare <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per un <xref:System.Windows.Controls.TreeViewItem> , o qualsiasi <xref:System.Windows.Controls.HeaderedItemsControl> , nel modello di dati. Quando si imposta la <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> proprietà, tale valore viene utilizzato quando <xref:System.Windows.HierarchicalDataTemplate> viene applicato. Utilizzando un <xref:System.Windows.HierarchicalDataTemplate> è possibile impostare in modo ricorsivo <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per ogni <xref:System.Windows.Controls.TreeViewItem> in <xref:System.Windows.Controls.TreeView> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare un oggetto <xref:System.Windows.Controls.TreeView> ai dati gerarchici e utilizzare un oggetto <xref:System.Windows.HierarchicalDataTemplate> per specificare <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per <xref:System.Windows.Controls.TreeViewItem> ogni.  Il viene <xref:System.Windows.Controls.TreeView> associato ai dati XML che rappresentano i dipendenti di una società.  Ogni `Employee` elemento può contenere altri `Employee` elementi per indicare chi segnala a chi. Poiché i dati sono ricorsivi, è <xref:System.Windows.HierarchicalDataTemplate> possibile applicarli a ogni livello.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md)
